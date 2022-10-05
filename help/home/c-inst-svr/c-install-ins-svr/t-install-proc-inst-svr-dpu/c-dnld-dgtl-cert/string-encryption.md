---
description: Crittografa le password e altre stringhe durante la comunicazione tra il client e il server.
title: Crittografia della stringa
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
exl-id: 43696ff1-3153-4d85-b9a9-c2752dd2c29a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 1%

---

# Crittografia della stringa{#string-encryption}

{{eol}}

Crittografa le password e altre stringhe durante la comunicazione tra il client e il server.

Quando comunichi tra il client Data Workbench (workstation) e il server, puoi salvare un parametro Value (come una password) con il tipo di *EncryptedString*. Questo nasconde il parametro e salva la stringa nel *Archivio credenziali Windows* sul server con la chiave corrispondente restituita. Memorizza principalmente le credenziali utilizzate nelle esportazioni, ma può essere utilizzato per crittografare qualsiasi parametro.

* È stata aggiunta una nuova cartella al server\**EncryptStrings**

   In questo punto è possibile impostare il file di configurazione per crittografare le stringhe.

* Nuovo file di configurazione aggiunto in Server\Component\**EncryptedStrings.cfg**

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   Questo file esegue il polling del *Server* Cartella \*EncryptStrings* per i file di configurazione della crittografia.

**Per crittografare una stringa**:

1. Crea un **EncryptedStrings.cfg** file di configurazione per una stringa con questi campi impostati:

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

   * *Valore* - Questo campo contiene la stringa di testo normale che deve essere crittografata.

      Solo crittografia lato server. La *Valore* è crittografata solo nel computer server.

   * *Nome* - Questo campo contiene un valore che identifica la stringa crittografata.
   * *EncryptValue* - Questo campo viene lasciato vuoto nel file di configurazione di input. Il valore crittografato verrà restituito in questo campo.

   È possibile aggiungere più **NameEncryptValuePair** valori per campi diversi per la crittografia.

   >[!NOTE]
   >
   >Tutti i campi Valore vuoti verranno rimossi.

1. Salva il **EncryptedStrings.cfg** sul server\**EncryptStrings** cartella.

**File di output**

Verrà generato un file di output con lo stesso nome del file di input con un &lt;*nomefile*>*cifrato* estensione. Ad esempio, se il file di input è denominato *sample.cfg* quindi il file di output verrà denominato *sample.cfg.encryption*.
