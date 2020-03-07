---
description: Ora puoi usare CSV, TSV, Esportazione segmenti ed Esportazione segmenti con intestazione tramite protocolli FTP e SFTP per esportare i file dei segmenti dal client (workstation) al server.
title: Esportazione di un segmento mediante la distribuzione S/FTP
uuid: 4d654368-cbf7-4e7f-8ab9-82f4e0261ac6
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Esportazione di un segmento mediante la distribuzione S/FTP{#export-a-segment-using-s-ftp-delivery}

Ora puoi usare CSV, TSV, Esportazione segmenti ed Esportazione segmenti con intestazione tramite protocolli FTP e SFTP per esportare i file dei segmenti dal client (workstation) al server.

**Impostazione dei file di configurazione di esportazione S/FTP**

Per impostare la configurazione di esportazione, sono stati aggiunti due nuovi file di configurazione di esportazione per impostare una connessione FTP o SFTP, consentendo di scegliere i dettagli Server dal file *FTPServerInfo.cfg* e di scegliere le credenziali dalla cartella *FTPUserCredentials* (corrispondente al Nome Server fornito negli argomenti dei comandi).

* Impostate il file **FTPServerInfo.cfg** .

   Immettere le informazioni sul server FTP e impostare i tentativi di connessione consentiti dalla workstation. Modificate dalla workstation o dal server nel file [!DNL Server\Addresses\Export\] **[!DNL FTPServerInfo.cfg]** .

   ```
   FTP Servers = vector: 1 items 
     0 = ftpServerInfo:  
       Address = string:  
       Name = string:  
       Port = int: 21 
   Connect Retries = vector: 1 items 
     0 = connectServerRetries:  
       Retries = int: 0 
       Server Name = string:
   ```

* Impostate il file **FTPUserCredentials.cfg** .

   Immettere le credenziali utente per connettersi ai server utilizzando il file [!DNL Server\Admin\Export\] **[!DNL FTPUserCredentials.cfg]** . Questo file contiene le credenziali utente necessarie per connettersi ai server e può essere modificato solo dal server e non dalla workstation (client).

   ```
   FTP User Credentials = vector: 1 items 
     0 = ftpUserCredInfo: 
       User Name = string:  
       User Password = EncryptedString:  
       Server Name = string:  
       Public Key Path = string:  
       Private Key Path = string:  
       Passphrase = EncryptedString:
   ```

   >[!NOTE]
   >
   >Assicurarsi che le chiavi SSH generate per l&#39;autenticazione siano nel formato identico a quelle generate quando si utilizza il comando SSH Keygen.
   >
   >Esempio di generazione di chiavi SSH tramite keygen:
   >
   >
   ```
   >ssh-keygen -t rsa -b 4096 -C "<label>"
   >```

   Il file **FTPUserCredentials.cfg** contiene sei parametri necessari per diversi trasferimenti FTP o SFTP.

   1. *Nome utente*
   1. *Password utente*
   1. *Nome server*
   1. *Percorso chiave pubblica*
   1. *Percorso chiave privata*
   1. *Passphrase*
   <table id="table_4EB416DC770D4D1AA4FAD9676C0D680C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Protocollo </th> 
      <th colname="col2" class="entry"> Parametri </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>FTP </p> </td> 
      <td colname="col2"> <p>Impostate i parametri 1, 2, 3. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP mediante autenticazione tramite password </p> </td> 
      <td colname="col2"> <p>Impostate i parametri 1, 2, 3 quando il trasferimento utilizza l'autenticazione tramite password (-p negli argomenti del comando). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>SFTP tramite autenticazione chiave </p> </td> 
      <td colname="col2"> <p>Impostate i parametri 1, 2, 3, 4, 5, 6 quando il trasferimento utilizza l'autenticazione chiave (-k negli argomenti dei comandi). </p> </td> 
      </tr> 
    </tbody> 
    </table>

**Impostazione dei comandi di esportazione FTP e SFTP**

1. Aprire una tabella di esportazione.

   Nella workstation, fate clic con il pulsante destro del mouse su una tabella *di* dettaglio e scegliete uno dei tipi di esportazione: CSV, TSV, Esportazione segmento o Esportazione segmento con intestazione. In alternativa, aprite il [!DNL .export] file da un prompt dei comandi e modificatelo (consultate [Configurazione dei segmenti per l’esportazione](../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372)).

1. Nel campo *Comando* , impostatelo in modo che punti all’eseguibile di esportazione:

   ```
   ExportIntegration.exe
   ```

1. Impostate i campi *Argomenti* comando come illustrato di seguito per il protocollo e l&#39;autenticazione richiesti:

   **FTP**

   ```
   <Command Arguments> set to  
   <ftp "%file%" ServerName ServerDestinationPath>
   ```

   ![](assets/FTP_Command_arguments.png)

   **SFTP** (se si utilizza la password per l&#39;autenticazione)

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -p>
   ```

   **SFTP** (se si utilizzano le chiavi per l&#39;autenticazione)

   ```
   <Command Arguments> set to  
   <sftp "%file%" ServerName ServerDestinationPath -k>
   ```

   ![](assets/SFTP_command_arguments.png)

Tutti gli argomenti dei comandi sono obbligatori e devono essere immessi come mostrato.

## Esportazione S/FTP con chiavi private/pubbliche {#section-0534424d79a54a47b82594cfa7b3c17f}

Per implementare l’esportazione FTP e SFTP utilizzando chiavi private e pubbliche, inserite i file di configurazione nelle seguenti cartelle:

* Inserite **FTPServerInfo.cfg** nella [!DNL Server/Addresses/Export/] cartella.
* Inserite **FTPUserCredentials.cfg** nella [!DNL Server/Admin/Export/] cartella.

Sei parametri sono inclusi nel file **FTPServerInfo.cfg** :

1. *Nome utente*
1. *Password utente*
1. *Nome server*
1. *Percorso chiave pubblica*
1. *Percorso chiave privata —* Inserisci il percorso della chiave privata nel file di configurazione senza l&#39;estensione, ad esempio:

[!DNL Private Key Path = string: E:\\Server\\campaign\\campaignprivatekey]

1. *Passphrase*

L&#39;FTP utilizza i parametri 1, 2 e 3.

SFTP utilizza i parametri 1, 2 e 3 quando il trasferimento utilizza l&#39;autenticazione tramite password.

SFTP utilizza tutti e sei i parametri quando il trasferimento viene eseguito utilizzando l&#39;autenticazione chiave. Ad esempio, se utilizzate le chiavi per l&#39;autenticazione:

[!DNL 'Command Arguments' = sftp "%file%" ServerName ServerDestinationPath -k]

I file di configurazione devono trovarsi nella posizione corretta.

>[!NOTE]
>
>Le chiavi pubbliche devono puntare a un file **.pem** e non a un percorso di cartella. È possibile creare chiavi utilizzando una funzione di generazione di chiavi SSH da applicazioni come Cygwin. (Le chiavi vengono generate automaticamente in un formato .ppk non supportato.)
