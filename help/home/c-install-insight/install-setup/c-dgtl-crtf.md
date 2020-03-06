---
description: Dopo aver installato i file del programma Insight, è necessario scaricare e installare il certificato digitale fornito da Adobe.
title: Download e installazione del certificato digitale
uuid: 93ab2222-a977-4279-9e1e-71038b1d1cfa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Download e installazione del certificato digitale{#downloading-and-installing-the-digital-certificate}

Dopo aver installato i file del programma Insight, è necessario scaricare e installare il certificato digitale fornito da Adobe.

## Download e installazione del certificato digitale {#topic-fed3b44e472c4e4ca6dd5852af14cdb9}

Dopo aver installato i file del programma Insight, è necessario scaricare e installare il certificato digitale fornito da Adobe.

## Informazioni sui certificati digitali {#concept-9eed01c8d95440cda6ce29d68e65098c}

Adobe utilizza i certificati digitali X.509 per identificare e autenticare i componenti client e server che costituiscono un&#39;implementazione.

<!--
c_undst_dgtl_crtf.xml
-->

Quando installate Insight, è necessario installare il certificato digitale che autorizza un individuo denominato (ad esempio, Jane Smith) a utilizzare l&#39;applicazione client installata.

>[!NOTE]
>
>Se è necessario migrare Insight in un altro computer o in un altro utente denominato, è necessario ottenere un nuovo certificato da Adobe. Per farlo, contatta l’Assistenza clienti Adobe.

Insight presenta questo certificato digitale per accedere a un componente server. L’amministratore di un componente server può limitare l’accesso alle risorse del server in base al nome comune o ai valori delle unità organizzative visualizzati nel certificato dell’utente.

I certificati digitali X.509 installati con le applicazioni Adobe consentono inoltre ai componenti client e server di scambiarsi informazioni tramite SSL (Secure Sockets Layer). SSL assicura le trasmissioni via HTTP utilizzando un sistema di crittografia a chiave pubblica e privata. L’implementazione di SSL da parte di Adobe supporta le chiavi RSA a 1024 bit e utilizza un algoritmo di cifratura RC4 a 128 bit.

Oltre alla protezione, il certificato digitale installato funziona anche come chiave di licenza che consente di eseguire Insight. Per funzionare correttamente, un certificato digitale deve essere bloccato e corrente oppure l&#39;applicazione non verrà avviata.

## Certificati bloccati dal nodo {#section-984aa8f2f5a1448cadc4afea978aedc9}

Un certificato bloccato ai nodi è un certificato digitale registrato nel computer in cui è installato. Il blocco dei nodi associa in modo permanente un certificato a un identificatore di nodo specifico (un valore che identifica in modo univoco un particolare computer). Per bloccare il certificato in un nodo, il computer deve disporre dell&#39;accesso a Internet al server delle licenze Adobe o a un server proxy con accesso al server delle licenze.

Se si esegue l&#39;installazione su un computer che non può accedere a Internet, è necessario ottenere e installare uno speciale certificato pre-bloccato come descritto in [Utilizzo di certificati digitali su computer senza accesso](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#section-d3c060131d7f45cda27f68848b704fa1)a Internet.

Se si esegue l&#39;installazione su un computer in grado di accedere a Internet, il certificato digitale verrà bloccato automaticamente al primo avvio di Insight. Dopo il blocco dei nodi, il certificato non può essere utilizzato su nessun altro computer. Se è necessario migrare Insight in un altro computer, è necessario ottenere un nuovo certificato sbloccato da Adobe.

## Certificati correnti {#section-0816b031df3e415ab3f0205b720c723e}

Oltre a essere bloccati, il certificato digitale deve essere corrente. Per restare aggiornati, il certificato deve essere convalidato regolarmente (generalmente ogni 30 giorni, ma può variare a seconda del contratto con Adobe). Se il computer dispone di accesso a Internet, il processo di riconvalidazione è completamente trasparente. Insight si connette automaticamente al server licenze e riconvalida il certificato quando necessario. Se il computer non dispone dell&#39;accesso a Internet, è necessario installare manualmente un certificato aggiornato come descritto nella sezione seguente.

## Utilizzo di certificati digitali su computer senza accesso a Internet {#section-d3c060131d7f45cda27f68848b704fa1}

Se state installando un computer che non può accedere a Internet, dovete richiedere un certificato pre-bloccato per l&#39;installazione di Insight. Un certificato pre-bloccato è un certificato digitale che Adobe blocca manualmente all&#39;identificatore del nodo del computer.

Per richiedere un certificato pre-bloccato, devi inviare l&#39;identificatore del nodo e il numero del certificato all&#39;Assistenza clienti Adobe. Per ottenere l&#39;identificatore del nodo del computer, contattate l&#39;Assistenza clienti Adobe per richiedere l&#39; [!DNL Node Identifier] utility Adobe. È inoltre possibile ottenere l’identificatore del nodo dall’avviso che Insight genera quando tenta di connettersi al server licenze e non può. Quando ricevete il certificato pre-bloccato, installatelo come descritto nelle ultime due fasi dell&#39; [installazione dei certificati](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#task-1dad1e1d86d04100a7bcf87f26303c38)digitali.

Quando il certificato deve essere convalidato, è necessario scaricare un nuovo certificato convalidato dal server licenze e reinstallarlo nel computer (a meno che il contratto con Adobe non preveda diversamente).

## Installazione di certificati digitali {#task-1dad1e1d86d04100a7bcf87f26303c38}

<!--
t_install_dgtl_crtf.xml
-->

**Per scaricare e installare il certificato digitale**

1. Aprite il browser Web su [!DNL http:\\license.visualsciences.com].

   >[!NOTE]
   >
   >Il browser potrebbe richiedere la presentazione di un certificato digitale. In caso contrario, fare clic **[!UICONTROL Cancel]** per chiudere la finestra di dialogo.

1. Nella schermata di accesso, immettete [!DNL Account Name] e il [!DNL Password] contenuto ricevuto da Adobe, quindi fate clic su **[!UICONTROL login]**.
1. Individuate il certificato rilasciato per l&#39;istanza di Insight ( *Your Name*.pem) e fate clic sull&#39; ![](assets/btn_save_certificatedownload.PNG) icona associata a tale certificato.
1. Quando viene richiesto di salvare il certificato, fate clic su **[!UICONTROL Save]**.
1. Scaricate il file nella [!DNL Certificates] cartella nella directory in cui avete installato Insight.

   Questa cartella contiene un file di certificato denominato [!DNL trust_ca_cert.pem]. Entrambi i file di certificato devono sempre essere presenti affinché Insight funzioni.

## Archivio certificati di Windows {#concept-4acb13b7de9340ea8cde8ad84b93358d}

L&#39;archivio certificati di Windows consente di memorizzare il certificato del client e la chiave privata nell&#39;archivio certificati di Windows per la comunicazione SSL con i server.

<!--
crypto-api.xml
-->

L&#39;archivio certificati di Windows per il client è una nuova funzione che consente di memorizzare il certificato di comunicazione SSL e la chiave privata nell&#39;archivio certificati di Windows anziché nel `Insight/Certificates/<CertName>.pem` file. L&#39;utilizzo dell&#39;archivio certificati di Windows potrebbe essere preferibile se si utilizza l&#39;archivio certificati per altre applicazioni e si desidera eseguire la gestione certificati in un&#39;unica posizione, oppure per gli utenti che dispongono dell&#39;accesso al controllo di Windows aggiuntivo fornito dall&#39;archivio certificati di Windows.

>[!NOTE]
>
>La licenza con il server licenze viene mantenuta utilizzando il `<Common Name>.pem` file esistente e il certificato ottenuto dall&#39;archivio certificati verrà utilizzato solo per la comunicazione ai server specificati.

## Prerequisiti {#section-69b18600052145ff8e5299b7123e69c5}

1. È necessario avere accesso al [!DNL certmgr.msc] file con la possibilità di importare un certificato e una chiave nello store **Personale** . (Deve essere vero per impostazione predefinita per la maggior parte degli utenti Windows).

1. L&#39;utente che esegue la configurazione deve disporre di una copia dello strumento della riga di comando **OpenSSL** .
1. Il server e il client devono già essere configurati per utilizzare un certificato SSL personalizzato, fornendo le istruzioni per memorizzare il certificato client nell&#39;archivio certificati di Windows anziché memorizzarlo nella directory **Certificati** .

## Configurazione dell&#39;archivio certificati di Windows {#section-3629802122e947d4b4f63e8b732cfe27}

L&#39;archivio certificati di Windows per i client è attivato seguendo la procedura seguente:

**Passaggio 1: Importa il certificato SSL dell&#39;utente e la chiave privata nell&#39;archivio certificati di Windows.**

In [Utilizzo di certificati personalizzati in Workbench](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) dati si è invitati a inserire il certificato SSL e la chiave nella seguente directory:

```
< 
<filepath>
  DWB Install folder 
</filepath>>\Certificates\
```

Il nome del certificato è `<Common Name>.pem` come Analytics Server 1.pem (non il file trust_ca_cert.pem).

Prima di importare il certificato e la chiave privata, è necessario convertirli da . [!DNL pem] in un [!DNL .pfx] formato, ad esempio [!DNL pkcs12.pfx] ).

1. Aprite un prompt dei comandi o un terminale e andate alla directory:

   ```
   <CommonName>.pem c: cd \<filepath>DWB Install folder</filepath>>\Certificates
   ```

1. Eseguire [!DNL openssl] con i seguenti argomenti (con il nome effettivo del [!DNL .pem] file):

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   Se richiesto, fate clic su **Invio** per saltare l’immissione di una password di esportazione.

1. Eseguire [!DNL certmgr.msc] dalla riga di comando, dal menu Start o dal prompt di esecuzione.
1. Aprite l&#39;archivio certificati **personali** per l&#39;utente corrente.

   ![](assets/6_5_crypto_api_0.png)

1. Fare clic con il pulsante destro del mouse su **Certificati** e scegliere **Tutte le attività** > **Importa**.

   Accertatevi che l&#39;opzione Utente **** corrente sia selezionata, quindi fate clic su **Avanti**.

   ![](assets/6_5_crypto_api_4.png)

1. Fate clic su **Sfoglia** e selezionate il `<CommonName>.pfx` file creato in precedenza. Per visualizzarlo dovrete modificare la casella a discesa dell&#39;estensione del file da un certificato X.509 a **Personal Information Exchange** o a **Tutti i file** .

   Selezionate il file e fate clic su **Apri**, quindi su **Avanti**.

1. Non inserite una password e accertatevi che siano selezionate solo le opzioni **Contrassegna la chiave come esportabile** e **Includi tutte le proprietà** estese.

   ![](assets/6_5_crypto_api_3.png)

   Fai clic su **Successivo**.

1. Accertatevi che **Posizionate tutti i certificati nel seguente archivio** sia selezionato e che l&#39;archivio certificati elencato sia **Personale**. Se siete un utente avanzato, potete selezionare un altro store a questo punto, ma dovrete cambiare la configurazione in un secondo momento.

1. Fare clic su **Avanti** , quindi su **Fine**. Viene visualizzata una finestra di dialogo in cui viene indicato che l&#39;importazione è avvenuta correttamente e il certificato viene visualizzato nella cartella Certificati dello store.

   >[!NOTE]
   >
   >Prestare particolare attenzione ai **campi Rilasciati** e **Rilasciati da** . Ne avrete bisogno nel prossimo passo.

**Passaggio 2: Modificate il file Insight.cfg.**

È necessario modificare il [!DNL Insight.cfg] file per indirizzare Workbench dati all&#39;utilizzo della funzione Archivio certificati di Windows. Ogni voce del server in questo file deve avere alcuni parametri aggiuntivi specificati. Se i parametri vengono omessi, per impostazione predefinita la workstation utilizzerà la configurazione del certificato esistente. Se i parametri sono specificati ma hanno valori errati, la workstation immetterà uno stato di errore e dovrete fare riferimento al file di registro per le informazioni di errore.

1. Aprite il file **Insight.cfg** (che si trova nella directory di installazione di **Insight** ).

1. Scorrete verso il basso fino alla voce del server che desiderate configurare. Se si desidera utilizzare l&#39;archivio certificati di Windows per ogni server, è necessario apportare queste modifiche a ogni voce nel vettore di [!DNL serverInfo] oggetti.
1. Aggiungete questi parametri al [!DNL Insight.cfg] file. È possibile eseguire questa operazione dalla workstation o manualmente aggiungendo i seguenti parametri all&#39; [!DNL serverInfo] oggetto. Assicuratevi di utilizzare gli spazi invece dei caratteri di tabulazione e di non eseguire altri errori tipografici o di sintassi in questo file. )

   ```
   SSL Use CryptoAPI = bool: true  
   SSL CryptoAPI Cert Name = string: <Common Name>  
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC  
   SSL CryptoAPI Cert Store Name = string: My 
   ```

   Il valore booleano abilita o disabilita la funzione. Il nome del certificato corrisponde a **Emittente** nel gestore certificati. Il nome dell&#39;emittente del certificato corrisponde a **Emesso da** e il nome **** archivio deve corrispondere al nome dell&#39;archivio certificati.

   >[!NOTE]
   >
   >Il nome &quot;Personale&quot; nel Gestore dei certificati (certmgr.msc) in realtà fa riferimento all&#39;archivio certificati denominato **My.** Di conseguenza, se importate il certificato di comunicazione SSL e la chiave (.PFX) nell&#39;archivio certificati **personale** come consigliato, dovete impostare la stringa **SSL CryptoAPI Cert Name** su &quot;My&quot;. L&#39;impostazione di questo parametro su &quot;Personale&quot; non funzionerà. Questa è una particolarità dell&#39;archivio certificati di Windows.

   Un elenco completo degli store di sistema predefiniti può essere ottenuto qui: [https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx). Nel sistema potrebbero essere presenti ulteriori archivi di certificati. Se si desidera utilizzare uno store diverso da &quot;Personale&quot; (ad esempio **My**), è necessario ottenere il nome canonico dell&#39;archivio certificati e fornirlo nel [!DNL Insight.cfg] file. (Il nome dell&#39;archivio di sistema &quot;My&quot; viene spesso indicato come &quot;My&quot; e &quot;MY&quot; dalla documentazione di Windows. Il parametro non fa distinzione tra maiuscole e minuscole.

1. Dopo aver aggiunto questi parametri e verificato che i valori corrispondano all&#39;elenco in Gestione certificati di Windows, salvare il [!DNL Insight.cfg] file.

È ora possibile avviare la workstation (oppure disconnettersi/riconnettersi al server). Workbench dati deve caricare il certificato e la chiave dall&#39;archivio certificati e connettersi normalmente.

## Uscita log {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

Se un certificato non viene trovato o non è valido, il messaggio di errore viene inviato al [!DNL HTTP.log] file.

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>Il framework di registrazione L4 può essere attivato configurando il [!DNL L4.cfg] file (consultate il vostro account manager per configurare questa impostazione).

## Uso di certificati personalizzati in Workbench dati {#concept-ee6a9b5015f84a0ba64a11428b0a72dd}

Istruzioni per l&#39;uso dei certificati personalizzati.

<!--
using-custom-certificates-DWB.xml
-->

Un certificato utilizzato dal client o dal server di Workbench dati deve essere firmato da un&#39;autorità di certificazione (Certificate Authority) affidabile. I clienti di Workbench dati ricevono i certificati firmati da Visual Sciences CA. Questi certificati sono affidabili dal software Workbench dati, dal momento che [!DNL trust_ca_cert.pem] (fornito insieme al software Insight e memorizzato nella directory **Certificates** di server e client) contiene un certificato *CA* Root per Visual Sciences CA. Questi certificati vengono utilizzati sia per la licenza del software che per l&#39;autenticazione quando client e server comunicano tra loro utilizzando SSL. Solo i certificati rilasciati dalla CA di Visual Sciences possono essere utilizzati per la licenza, ma altri certificati possono essere utilizzati per la comunicazione e l&#39;autenticazione. I certificati rilasciati da CA diverse da Visual Sciences sono indicati di seguito come certificati *personalizzati.*

**Nota importante:** Per server e client, il software Workbench dati utilizza i file di certificato installati nella directory **Certificati** del client o del server o i certificati esplicitamente identificati nella relativa configurazione. Tuttavia, potete anche utilizzare l&#39;archivio certificati di Windows per i client.

Le istruzioni seguenti descrivono le procedure da seguire per utilizzare i certificati personalizzati per la comunicazione tra client e server di Workbench dati. Non ogni dettaglio è un requisito difficile e si possono utilizzare diverse variazioni nel processo. Tuttavia, le procedure riportate di seguito sono state collaudate per funzionare.

## Configurazione di certificati client personalizzati {#section-2083fd41973e451fa404e7a4ae4da591}

1. Aggiungere il certificato della CA emittente al [!DNL trust_cert_ca.pem], che viene installato nella directory **Certificati** del client e di ogni server in ogni cluster a cui si accede utilizzando questo certificato personalizzato.

1. Ottenete un certificato personalizzato per ciascun server del cluster, alle seguenti condizioni:

   1. Il certificato è formattato come [!DNL .pem] certificato.
   1. Il certificato contiene la sua chiave e non è crittografato (ovvero non ha una password/frase di autorizzazione).

      Un certificato contiene la chiave con una delle seguenti righe:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Un modo per rimuovere la frase della password da un [!DNL .pem] certificato:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Il certificato ha la NC, O, OU, ecc. come richiesto per questo client nel [!DNL Access Control.cfg] file dei server.
   1. Il certificato è stato rilasciato con uno *scopo **** di *client* (o sia *server* che **** *client*).

      Per verificare che un certificato disponga di un codice scopo di server e/o client, è possibile utilizzare i comandi seguenti:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Per i certificati server, entrambi i comandi devono restituire:

      ```
      custom_communications_cert.pem: OK
      ```

      Per un certificato client, è necessario solo il secondo comando per ottenere [!DNL OK].

1. Posizionare il certificato nella directory **Certificati** del client.
1. In [!DNL Insight.cfg]*serverInfo* per ciascun cluster che desideri utilizzare questo certificato, accertati che il certificato client *personalizzato* sia denominato, ad esempio:

   ```
   Servers = vector: 1 items 
     0 = serverInfo: 
       SSL Client Certificate = string:  
     <my_custom_client_cert.pem>
   ```

## Configurazione di certificati server personalizzati {#setting-up-custom-server-certificates}

Questa sezione presuppone che sia installato e in esecuzione un cluster che utilizza certificati rilasciati da Visual Sciences e che la configurazione segua le pratiche comuni (come la directory *Components for Processing Servers* nel master viene sincronizzata con le directory *Components* di tutti i DPU).

1. Aggiungete il certificato della CA emittente al [!DNL trust_cert_ca.pem] quale viene installato su ogni server del cluster e su ogni client che deve comunicare con questo cluster.
1. Ottenete un certificato personalizzato per ciascun server del cluster, con i seguenti requisiti:

   1. Il certificato personalizzato è formattato come [!DNL .pem] certificato.
   1. Il certificato contiene la sua chiave e non è crittografato (ovvero non ha una password/frase di autorizzazione).

      Un certificato contiene la sua chiave se contiene una riga come:

      ```
      BEGIN PRIVATE KEY 
      BEGIN RSA PRIVATE KEY
      ```

      Un modo per rimuovere la frase della password da un [!DNL .pem] certificato:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem 
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Il certificato ha lo stesso CN [!DNL server_cert.pem] attualmente installato sul server.
   1. Il certificato è stato rilasciato con uno scopo di *server* e *client*.

      Per verificare che un certificato disponga di un codice scopo di server e/o client, è possibile utilizzare i comandi seguenti:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem 
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Per i certificati server, entrambi i comandi devono restituire:

      ```
      custom_communications_cert.pem: OK
      ```

      Per un certificato client, è necessario solo il secondo comando per ottenere [!DNL OK].

1. Installate il certificato personalizzato di ciascun server nella directory **Certificati** del server come [!DNL custom_communications_cert.pem].

1. Utilizzando un editor di testo, aggiungi la riga seguente al file **Communications.cfg** sia in directory *Components* che *Components for Processing Servers* , direttamente sotto la prima riga ( [!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Riavviate tutti i server.

**Avviso di errore certificato**

Quando il server o il client Insight sta cercando un certificato di **licenza** nella directory **Certificates** , tenta di convalidare tutti i certificati (tranne [!DNL trust_ca_cert.pem]), rispetto a una copia hardcoded del certificato Insight CA, che non riesce su qualsiasi certificato personalizzato presente nella directory. Il server visualizza questo avviso:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Questo avviso può essere ignorato in tutta sicurezza.

## Cifratura stringa {#concept-35da0b53650a4d7e82b240ad27f6d45a}

Crittografare le password e altre stringhe durante la comunicazione tra il client e il server.

<!--
string_encryption.xml
-->

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
