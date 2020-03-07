---
description: Il file JSON DeviceAtlas verrà ora distribuito in un file .bundle (un file .tar.gz rinominato) insieme ai file DeviceAtlas.dll e DeviceAtlas64.dll.
solution: Analytics
title: Distribuzione DeviceAtlas
topic: Data workbench
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Distribuzione DeviceAtlas{#deviceatlas-distribution}

Il file JSON DeviceAtlas verrà ora distribuito in un file .bundle (un file .tar.gz rinominato) insieme ai file DeviceAtlas.dll e DeviceAtlas64.dll.

Quando l&#39;amministratore aggiorna Insight Server alla versione 6.0, il file DeviceAtlas.bundle è incluso con il pacchetto di aggiornamento nel profilo Software e Docs (profilo softdocs) che si trova in:

[!DNL Server Packages > v6.00 > Server_6.00.zip]

Il file DeviceAtlas.bundle viene estratto in [!DNL Server\Lookups\DeviceAtlas].

Il file DeviceAtlas.bundle deve essere inserito in una directory sincronizzata con i DPU, e il file DeviceAtlas.cfg corrispondente al nuovo DeviceAtlasComponent deve essere inserito nella directory &quot;Components for Processing Servers&quot; del master di sincronizzazione. Quando il file DeviceAtlas.bundle viene modificato, la prossima chiamata di ricerca DeviceAtlas darà risultati in base all&#39;API e/o al file JSON aggiornati.

## Modificare il file Transformation.cfg {#section-394823348f5740028666e62e2bd42754}

Le trasformazioni DeviceAtlas non dovranno più specificare il percorso del file JSON. Qualsiasi DeviceAtlasTransformation precedente definito nel file transformation.cfg non deve più includere il parametro File che punta al file JSON offuscato.

Questo file di esempio Transformation.cfg mostra l&#39;argomento File che deve essere eliminato per evitare confusione. (Lasciarlo lì non causerà danni, ma solo potenziali confusione perché sarà ignorato.)

```
6 = DeviceAtlasTransformation:  
  Comments = Comment: 0 items  
  Condition = AndCondition: 0 items

<b></b> 
<filepath>
  File = string: Lookups\\DeviceAtlas\\20110106_private.json.obfuscated 
</filepath> 
  ^^ DELETE THE ABOVE LINE FROM ALL PREVIOUS TRANSFORMATIONS ^^  
 
  Name = string: DeviceAtlas Lookup  
  Outputs = vector: 4 items  
    0 = Column:  
      Column Name = string: vendor  
      Field Name = string: x-vendor  
    1 = Column:  
      Column Name = string: model  
      Field Name = string: x-model  
    2 = Column:  
      Column Name = string: isBrowser  
      Field Name = string: x-isbrowser  
    3 = Column:  
      Column Name = string:usableDisplayHeight  
      Field Name = string: x-usable-display-height 
User Agent = string: x-ua  
```

## Modificare il file DeviceAtlas.cfg {#section-10b43705a6c846fd9ec54ea6be249f88}

Questo è un esempio dell&#39; [!DNL component] argomento richiesto nel file DeviceAtlas.cfg.

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

Questo file DeviceAtlas.bundle verrà trattato come un file di configurazione dal punto di vista della funzione di sincronizzazione dei profili. Inoltre, i dati JSON e la DLL saranno utilizzati a livello di componente piuttosto che a livello di singola trasformazione.

All&#39;avvio, un nuovo DeviceAtlasComponent trova il conglomerato .bundle, deconfonde il file JSON in memoria, estrae i file in una directory temporanea e carica la DLL appropriata per la piattaforma in esecuzione. Questo componente controlla anche le modifiche al file del bundle e ricarica automaticamente la DLL e il file .cfg se cambia.

## Esecuzione di DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

Una corretta configurazione fa una grande differenza nel tempo necessario per la trasformazione. La trasformazione può essere configurata in modo da essere eseguita una sola volta per ogni visitatore per sessione per consentire a DeviceAtlas di velocizzare il processo.

**Se distribuito utilizzando Log Processing.cfg**:

Eseguire le trasformazioni due volte.

1. Cerca solo il [!DNL mobile id] campo, quindi
1. Creare le condizioni per ignorare i campi [!DNL mobile id] e quindi cercare gli altri campi.

**Se distribuito utilizzando Transformation.cfg**:

Distribuire come nel passaggio 1 nell&#39;elaborazione dei log sopra, oppure utilizzare righe incrociate per supportare un&#39;impostazione condizionale.

* Righe incrociate (Cross-Rows) - Ottenete la chiave di sessione precedente. Quindi identificate se la chiave di sessione corrente è diversa da quella trovata con righe incrociate. In tal caso, la trasformazione DeviceAtlas verrà eseguita solo su un record per sessione.

