---
description: Il file JSON DeviceAtlas verrà ora distribuito in un file .bundle (a rinominato .tar.gz) insieme ai file DeviceAtlas.dll e DeviceAtlas64.dll.
title: Distribuzione DeviceAtlas
uuid: 1eb76c61-6696-4e6c-a3fd-61c00cc17b0a
exl-id: e9671810-d32c-4ec4-a1cb-54b71c6f101c,333507bb-3e8b-4da1-8218-b35fcf8d5f80,aa811c7b-ef80-4f23-b395-0cbb7d2677a9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# Distribuzione DeviceAtlas{#deviceatlas-distribution}

Il file JSON DeviceAtlas verrà ora distribuito in un file .bundle (a rinominato .tar.gz) insieme ai file DeviceAtlas.dll e DeviceAtlas64.dll.

Quando l&#39;amministratore aggiorna Insight Server alla versione 6.0, il file DeviceAtlas.bundle viene incluso con il pacchetto di aggiornamento nel profilo Software e Documenti (profilo softdocs) che si trova in:

[!DNL Server Packages > v6.00 > Server_6.00.zip]

Il file DeviceAtlas.bundle viene estratto in [!DNL Server\Lookups\DeviceAtlas].

Il file DeviceAtlas.bundle deve essere posizionato in una directory sincronizzata con le DPU e il file DeviceAtlas.cfg corrispondente al nuovo DeviceAtlasComponent deve essere posizionato nella directory &quot;Components for Processing Servers&quot; sul master di sincronizzazione. Quando il file DeviceAtlas.bundle viene modificato, la successiva chiamata di ricerca DeviceAtlas otterrà risultati in base al file API e/o JSON aggiornato.

## Modifica il file Transformation.cfg {#section-394823348f5740028666e62e2bd42754}

Le trasformazioni DeviceAtlas non dovranno più specificare il percorso del file JSON. Qualsiasi DeviceAtlasTransformation precedente definito nel file conversion.cfg non deve più includere il parametro File che punta al file JSON offuscato.

Questo file di esempio Transformation.cfg mostra l&#39;argomento File che deve essere eliminato per evitare confusione. (Lasciarlo lì non causerà danni, ma solo confusione potenziale perché verrà ignorato.)

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

## Modifica il file DeviceAtlas.cfg {#section-10b43705a6c846fd9ec54ea6be249f88}

Questo è un esempio dell&#39;argomento [!DNL component] richiesto nel file DeviceAtlas.cfg.

```
component = DeviceAtlasComponent: 
  DeviceAtlas Bundle File = string:Lookups\\DeviceAtlas\\DeviceAtlas.bundle 
  Unsynchronized Bundle Extraction Path = string: Temp\\DeviceAtlas\\
```

Questo file DeviceAtlas.bundle verrà trattato come un file di configurazione dal punto di vista della funzione di sincronizzazione del profilo. Inoltre, i dati JSON e la DLL saranno utilizzati a livello di componente anziché a livello di singola trasformazione.

All&#39;avvio, un nuovo DeviceAtlasComponent trova il conglomerato .bundle, deconfonde il file JSON in memoria, estrae i file in una directory temporanea e carica la DLL appropriata per la piattaforma in esecuzione. Questo componente controlla anche le modifiche al file del bundle e ricarica automaticamente il file DLL e il file .cfg se cambia.

## Esecuzione di DeviceAtlas {#section-6ed37b39199d4ffd95d30b49a7ee9666}

Una corretta configurazione fa una grande differenza nel tempo necessario per la trasformazione. La trasformazione può essere configurata in modo da essere eseguita una sola volta per visitatore per sessione per consentire a DeviceAtlas di velocizzare il processo.

**Se distribuito utilizzando Log Processing.cfg**:

Esegui le trasformazioni due volte.

1. Cerca solo il campo [!DNL mobile id], quindi
1. Crea le condizioni per ignorare il [!DNL mobile id] e quindi cerca il resto dei campi.

**Se distribuito utilizzando Transformation.cfg**:

Distribuisci come nel passaggio 1 nell’elaborazione del registro di cui sopra o utilizza le righe incrociate per supportare un’impostazione condizionale.

* Cross-Rows (Righe incrociate) - Prendi la chiave di sessione precedente. Quindi identifica se la chiave di sessione corrente è diversa da quella trovata con righe incrociate. In tal caso, la trasformazione DeviceAtlas verrà eseguita su un solo record per sessione.
