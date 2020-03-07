---
description: Crittografare le password e altre stringhe durante la comunicazione tra il client e il server.
title: Cifratura stringa
uuid: b2ec6a10-136c-4694-a425-04dbb41d43d1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Cifratura stringa{#string-encryption}

Crittografare le password e altre stringhe durante la comunicazione tra il client e il server.

Durante la comunicazione tra il client Workbench dati (workstation) e il server, è possibile salvare un parametro Value (ad esempio una password) con il tipo di *EncryptedString*. Questo nasconde il parametro e salva la stringa in *Windows Credential Store* sul server con la chiave corrispondente restituita. Questo memorizza principalmente le credenziali utilizzate nelle esportazioni, ma può essere utilizzato per cifrare qualsiasi parametro.

* Una nuova cartella è stata aggiunta in Server\**EncryptStrings**.

   In questa area è possibile impostare il file di configurazione per la cifratura delle stringhe.

* Un nuovo file di configurazione è stato aggiunto in Server\Component\**EncryptedStrings.cfg**.

   ```
   component = EncryptionComponent:
     Path = Path: EncryptStrings\\*.cfg
   ```

   Questo file controlla la cartella *Server*\*EncryptStrings* per i file di configurazione della crittografia.

**Per crittografare una stringa**:

1. Creare un file di configurazione **EncryptedStrings.cfg** per una stringa con i campi impostati:

   ```
   Names = vector: 1 items
    0 = NameEncryptValuePair:
     EncryptValue = EncryptedString: // left empty as input then output will be filled by server
     Name = string: // Name for identifier 
     Value = string: // Value to be encrypted
   ```

   * *Valore* - Questo campo contiene la stringa di testo normale che deve essere crittografata.

      Si tratta solo della cifratura sul lato server. L&#39;impostazione *Valore* è cifrata solo nel computer server.

   * *Nome* - Questo campo contiene un valore che identifica la stringa crittografata.
   * *EncryptValue* - Questo campo viene lasciato vuoto nel file di configurazione di input. Il valore crittografato verrà restituito in questo campo.
   È possibile aggiungere più valori **NameEncryptValuePair** per campi diversi per la cifratura.

   >[!NOTE]
   >
   >Tutti i campi Valore vuoti verranno rimossi.

1. Salvate il file **EncryptedStrings.cfg** nella cartella Server\**EncryptStrings**.

**File di output**

Viene generato un file di output con lo stesso nome del file di input con un &lt;*nomefile*>.*estensione crittografata* . Ad esempio, se il file di input è denominato *sample.cfg* , il file di output sarà denominato *sample.cfg.encrypt*.
