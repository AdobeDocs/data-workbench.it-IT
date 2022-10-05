---
description: Dopo aver installato i file del programma Insight, è necessario scaricare e installare il certificato digitale fornito dall’Adobe.
title: Download e installazione del certificato digitale (Insight)
uuid: 93ab2222-a977-4279-9e1e-71038b1d1cfa
exl-id: 0dff95ae-880b-45d5-96df-4eb6bea58891
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2744'
ht-degree: 39%

---

# Download e installazione del certificato digitale{#downloading-and-installing-the-digital-certificate}

{{eol}}

Dopo aver installato i file del programma Insight, è necessario scaricare e installare il certificato digitale fornito dall’Adobe.

## Download e installazione del certificato digitale {#topic-fed3b44e472c4e4ca6dd5852af14cdb9}

Dopo aver installato i file del programma Insight, è necessario scaricare e installare il certificato digitale fornito dall’Adobe.

## Informazioni sui certificati digitali {#concept-9eed01c8d95440cda6ce29d68e65098c}

 Adobe utilizza certificati digitali X.509 per identificare e autenticare i componenti client e server che costituiscono un’implementazione.

<!--
c_undst_dgtl_crtf.xml
-->

Quando installi Insight, devi installare il certificato digitale che autorizza un individuo con nome (ad esempio, Jane Smith) a utilizzare l’applicazione client installata.

>[!NOTE]
>
>Se è necessario eseguire la migrazione di Insight a un altro computer o a un altro utente con nome, è necessario ottenere un nuovo certificato da Adobe. Per farlo, contatta l’Assistenza clienti di Adobe.

Insight presenta questo certificato digitale per ottenere l’accesso a un componente server. L’amministratore di un componente server può limitare l’accesso alle risorse del server in base al nome comune o ai valori delle unità organizzative visualizzati nel certificato dell’utente.

I certificati digitali X.509 installati con applicazioni Adobe consentono inoltre ai componenti client e server di scambiare informazioni tramite Secure Sockets Layer (SSL). SSL protegge le trasmissioni via HTTP utilizzando un sistema di crittografia a chiave pubblica e privata. L’implementazione di SSL da parte di Adobe supporta le chiavi RSA a 1024 bit e utilizza un algoritmo di crittografia RC4 a 128 bit.

Oltre alla protezione, il certificato digitale installato funziona anche come chiave di licenza che consente di eseguire Insight. Per funzionare correttamente, un certificato digitale deve essere bloccato sul nodo e corrente, altrimenti l&#39;applicazione non verrà avviata.

## Certificati bloccati sul nodo {#section-984aa8f2f5a1448cadc4afea978aedc9}

Un certificato bloccato sul nodo è un certificato digitale registrato nel computer in cui è installato. Il blocco del nodo associa in modo permanente un certificato a un identificatore di nodo specifico (un valore che identifica in modo univoco un particolare computer). Per bloccare il certificato sul nodo, il computer deve disporre dell’accesso a Internet al server licenze Adobe o a un server proxy con accesso al server licenze.

Se stai effettuando l’installazione su un computer che non ha accesso a Internet, devi ottenere e installare uno speciale certificato pre-bloccato come descritto in [Utilizzo di certificati digitali su computer senza accesso a Internet](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#section-d3c060131d7f45cda27f68848b704fa1).

Se stai effettuando l’installazione su un computer che può accedere a Internet, il certificato digitale verrà bloccato automaticamente al primo avvio di Insight. Dopo il blocco sul nodo, il certificato non può essere utilizzato su nessun altro computer. Se è necessario eseguire la migrazione di Insight a un altro computer, è necessario ottenere un nuovo certificato sbloccato da Adobe.

## Certificati correnti {#section-0816b031df3e415ab3f0205b720c723e}

Oltre a essere bloccato sul nodo, il certificato digitale deve essere corrente. Per restare corrente, il certificato deve essere convalidato regolarmente (generalmente ogni 30 giorni, ma può variare a seconda del contratto con Adobe). Se il computer dispone di accesso a Internet, il processo di riconvalida è completamente trasparente. Insight si connette automaticamente al server licenze e, se necessario, riconvalida il certificato. Se il computer non dispone di accesso a Internet, è necessario installare manualmente un certificato aggiornato come descritto nella sezione seguente.

## Utilizzo di certificati digitali su computer senza accesso a Internet {#section-d3c060131d7f45cda27f68848b704fa1}

Se stai effettuando l’installazione su un computer che non ha accesso a Internet, devi richiedere un certificato pre-bloccato per l’installazione di Insight. Un certificato pre-bloccato è un certificato digitale che, ad Adobe, si blocca manualmente all’identificatore del nodo del computer.

Per richiedere un certificato pre-bloccato, devi inviare l’identificatore del nodo e il numero del certificato all’Assistenza clienti di Adobe. Per ottenere l’identificatore del nodo del computer, contatta l’Assistenza clienti Adobe per richiedere l’Adobe [!DNL Node Identifier] utilità. È inoltre possibile ottenere l’identificatore del nodo dall’avviso che Insight genera quando tenta di connettersi al server licenze e non può. Quando ricevi il certificato pre-bloccato, installalo come descritto negli ultimi due passaggi di [Installazione di certificati digitali](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#task-1dad1e1d86d04100a7bcf87f26303c38).

Quando è necessario riconvalidare il certificato, è necessario scaricare un nuovo certificato convalidato dal server licenze e reinstallarlo nel computer (a meno che non sia stato previsto un accordo con Adobe).

## Installazione di certificati digitali {#task-1dad1e1d86d04100a7bcf87f26303c38}

<!--
t_install_dgtl_crtf.xml
-->

**Per scaricare e installare il certificato digitale**

1. Apri il browser Web in [!DNL https:\\license.visualsciences.com].

   >[!NOTE]
   >
   >Il browser potrebbe richiedere la presentazione di un certificato digitale. Se lo fa, fai clic su **[!UICONTROL Cancel]** per chiudere la finestra di dialogo.

1. Nella schermata di accesso, immetti [!DNL Account Name] e [!DNL Password] ricevuti da Adobe, quindi fai clic su **[!UICONTROL login]**.
1. Individua il certificato rilasciato per la tua istanza di Insight ( *Nome*.pem) e fai clic sul pulsante ![](assets/btn_save_certificatedownload.PNG) icona associata al certificato.
1. Quando viene richiesto di salvare il certificato, fai clic su **[!UICONTROL Save]**.
1. Scarica il file nel [!DNL Certificates] nella directory in cui è stato installato Insight.

   Questa cartella contiene un file di certificato denominato [!DNL trust_ca_cert.pem]. Entrambi i file di certificato devono essere sempre presenti perché Insight funzioni.

## Archivio certificati di Windows {#concept-4acb13b7de9340ea8cde8ad84b93358d}

L’archivio certificati di Windows consente di memorizzare il certificato e la chiave privata del client nell’archivio certificati di Windows per la comunicazione SSL con i server.

<!--
crypto-api.xml
-->

L’archivio certificati di Windows per il client è una nuova funzione che consente di memorizzare il certificato e la chiave privata di comunicazione SSL nell’archivio certificati di Windows anziché nel file `Insight/Certificates/<CertName>.pem`. L’utilizzo dell’archivio certificati di Windows potrebbe essere preferibile se si utilizza l’archivio certificati per altre applicazioni e si desidera eseguire la gestione certificati in un’unica posizione oppure per gli utenti che apprezzano la registrazione di controllo di Windows aggiuntiva fornita dall’archivio certificati di Windows.

>[!NOTE]
>
>La concessione di licenze con il server licenze viene comunque mantenuta utilizzando il file esistente `<Common Name>.pem` e il certificato ottenuto dall’archivio certificati verrà utilizzato solo per la comunicazione ai server specificati.

## Prerequisiti {#section-69b18600052145ff8e5299b7123e69c5}

1. È necessario avere accesso al file [!DNL certmgr.msc] con la possibilità di importare un certificato e una chiave nell’archivio **Personali**. (dovrebbe essere così per impostazione predefinita per la maggior parte degli utenti Windows).

1. L’utente che esegue la configurazione deve disporre di una copia dello strumento della riga di comando **OpenSSL**.
1. Il server e il client devono già essere configurati per utilizzare un certificato SSL personalizzato, fornendo istruzioni per memorizzare il certificato client nell’archivio certificati di Windows anziché nel **Certificati** directory.

## Configurazione dell’archivio certificati di Windows {#section-3629802122e947d4b4f63e8b732cfe27}

L’archivio certificati di Windows per i client si attiva con la procedura seguente:

**Passaggio 1: importa il certificato SSL e la chiave privata dell’utente nell’archivio certificati di Windows.**

In [Utilizzo di certificati personalizzati nella Data Workbench](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-ee6a9b5015f84a0ba64a11428b0a72dd) ti viene indicato di inserire il certificato SSL e la chiave nella seguente directory:

```
<
<filepath>
  DWB Install folder
</filepath>>\Certificates\
```

Il nome del certificato è `<Common Name>.pem` come Analytics Server 1.pem (non il file trust_ca_cert.pem).

Prima di importare il certificato e la chiave privata, è necessario convertirli dal formato . [!DNL pem] in un formato [!DNL .pfx], ad esempio [!DNL pkcs12.pfx].

1. Apri un prompt dei comandi o un terminale e vai alla directory:

   ```
   <CommonName>.pem c: cd \<filepath>DWB Install folder</filepath>>\Certificates
   ```

1. Esegui [!DNL openssl] con i seguenti argomenti (con il nome effettivo del file [!DNL .pem]):

   ```
   openssl pkcs12 -in "<Common Name>.pem" -export -out "<Common Name>.pfx"
   ```

   Se richiesto, fai clic su **Invio** per saltare l’immissione di una password di esportazione.

1. Esegui [!DNL certmgr.msc] dal prompt di esecuzione, dal menu Start o dalla riga di comando.
1. Apri l’archivio certificati **Personali** per l’utente corrente.

   ![](assets/6_5_crypto_api_0.png)

1. Fai clic con il pulsante destro del mouse su **Certificati** e scegli **Tutte le attività** > **Importa**.

   Accertati che l’opzione **Utente corrente** sia selezionata, quindi fai clic su **Avanti**.

   ![](assets/6_5_crypto_api_4.png)

1. Fai clic su **Sfoglia** e seleziona il file `<CommonName>.pfx` creato in precedenza. Per visualizzarlo dovrai modificare la casella a discesa dell’estensione del file da un certificato X.509 a **Personal Information Exchange** o a **Tutti i file**.

   Seleziona il file e fai clic su **Apri**, quindi su **Avanti**.

1. Non inserire una password e accertati che siano selezionate solo le opzioni **Contrassegna la chiave come esportabile** e **Includi tutte le proprietà estese**.

   ![](assets/6_5_crypto_api_3.png)

   Fai clic su **Avanti**.

1. Assicurati che l’opzione **Colloca tutti i certificati nel seguente archivio** sia selezionata e che l’archivio certificati elencato sia **Personali**. Se sei un utente avanzato, a questo punto puoi selezionare un altro archivio, ma dovrai cambiare la configurazione in un secondo momento.

1. Fai clic su **Avanti**, quindi su **Fine**. Dovresti visualizzare una finestra di dialogo in cui viene indicato che l’importazione è avvenuta correttamente e vedere il certificato nella cartella Certificati dell’archivio.

   >[!NOTE]
   >
   >Presta particolare attenzione ai campi **Rilasciati a** e **Rilasciati da**. Ne avrai bisogno nel prossimo passaggio.

**Passaggio 2: modifica il file Insight.cfg.**

È necessario modificare il file [!DNL Insight.cfg] per indirizzare Data Workbench all’utilizzo della funzione archivio certificati di Windows. Per ogni voce del server in questo file devono essere specificati alcuni parametri aggiuntivi. Se i parametri vengono omessi, per impostazione predefinita la workstation utilizzerà la configurazione del certificato esistente. Se i parametri sono specificati ma hanno valori errati, la workstation entrerà in uno stato di errore e dovrai fare riferimento al file di registro per le informazioni relative all’errore.

1. Apri il file **Insight.cfg** (che si trova nella directory di installazione di **Insight**).

1. Scorri verso il basso fino alla voce del server che desideri configurare. Se desideri utilizzare l’archivio certificati di Windows per ogni server, è necessario apportare queste modifiche a ogni voce nel vettore degli oggetti [!DNL serverInfo].
1. Aggiungi questi parametri al loro file [!DNL Insight.cfg]. È possibile eseguire questa operazione dalla workstation o manualmente aggiungendo i seguenti parametri all’oggetto [!DNL serverInfo]. Assicurati di utilizzare gli spazi invece dei caratteri di tabulazione e di non commettere altri errori tipografici o di sintassi in questo file.

   ```
   SSL Use CryptoAPI = bool: true
   SSL CryptoAPI Cert Name = string: <Common Name>
   SSL CryptoAPI Cert Issuer Name = string: Visual Sciences,LLC
   SSL CryptoAPI Cert Store Name = string: My
   ```

   Il valore booleano abilita o disabilita la funzione. Il nome del certificato corrisponde a **Rilasciato a** nel gestore certificati. Il nome dell’autorità di certificazione corrisponde a **Rilasciato da** e il **Nome archivio** deve corrispondere al nome dell’archivio certificati.

   >[!NOTE]
   >
   >Il nome “Personali” nel gestore certificati (certmgr.msc) in realtà fa riferimento all’archivio certificati denominato **My.** Di conseguenza, se importi il certificato di comunicazione e la chiave SSL (.PFX) nell’archivio certificati **Personali** come consigliato, devi impostare la stringa **SSL CryptoAPI Cert Store Name** su “My”. L’impostazione di questo parametro su “Personale” non funzionerà. Questa è una particolarità dell’archivio certificati di Windows.

   Un elenco completo degli archivi di sistema predefiniti è disponibile qui: [https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136(v=vs.85).aspx](https://msdn.microsoft.com/en-us/library/windows/desktop/aa388136%28v=vs.85%29.aspx). Nel sistema potrebbero essere presenti ulteriori archivi di certificati. Se desideri utilizzare un archivio diverso da “Personali” (ad esempio **My**), è necessario ottenere il nome canonico dell’archivio certificati e fornirlo nel file [!DNL Insight.cfg]. Il nome dell’archivio di sistema “My” viene spesso indicato come “My” e “MY” nella documentazione di Windows. Il parametro sembra non fare distinzione tra maiuscole e minuscole.

1. Dopo aver aggiunto questi parametri e verificato che i valori corrispondano all’elenco nel gestore certificati di Windows, salva il file [!DNL Insight.cfg].

Ora puoi avviare la workstation (oppure disconnetterti/riconnetterti al server). Data Workbench dovrebbe caricare il certificato e la chiave dall’archivio certificati e connettersi normalmente.

## Output del registro {#section-a7ef8c9e90ef4bbabaa3cd51a2aca3ab}

Se un certificato non viene trovato o non è valido, il messaggio di errore viene inviato al file [!DNL HTTP.log].

```
ERROR Fatal error: the cert could not be found!
```

>[!NOTE]
>
>Il framework di registrazione L4 può essere attivato configurando il file [!DNL L4.cfg] (consulta il tuo account manager per configurarlo).

## Utilizzo di certificati personalizzati in Data Workbench {#concept-ee6a9b5015f84a0ba64a11428b0a72dd}

Istruzioni per l’utilizzo di certificati personalizzati.

<!--
using-custom-certificates-DWB.xml
-->

Un certificato utilizzato dal client o dal server di Data Workbench deve essere firmato da una CA attendibile (Certificate Authority). Data Workbench ai clienti di ricevere certificati firmati da Visual Sciences CA. Questi certificati sono considerati attendibili dal software Data Workbench, in quanto [!DNL trust_ca_cert.pem] (fornito insieme al software Insight e memorizzato nel **Certificati** directory sia dei server che dei client) contiene un *Certificato CA radice* per Visual Sciences CA. Questi certificati vengono utilizzati sia per la concessione di licenze del software che per l’autenticazione quando client e server comunicano tra loro utilizzando SSL. È possibile utilizzare solo i certificati rilasciati da Visual Sciences CA per le licenze, ma altri certificati possono essere utilizzati per la comunicazione e l’autenticazione. I certificati rilasciati da CA diverse da Visual Sciences sono indicati di seguito come *certificati personalizzati.*

**Nota importante:** Per server e client, il software Data Workbench utilizza i file di certificato installati nel client o nel server **Certificati** directory o certificati esplicitamente identificati nella relativa configurazione. Tuttavia, puoi anche utilizzare l’archivio certificati di Windows per i client.

Le istruzioni seguenti descrivono le procedure da seguire per utilizzare certificati personalizzati per la comunicazione tra client e server Data Workbench. Non tutti i dettagli sono un requisito difficile e possono essere utilizzate diverse variazioni nel processo. Tuttavia, le procedure seguenti sono state collaudate per funzionare.

## Configurazione di certificati client personalizzati {#section-2083fd41973e451fa404e7a4ae4da591}

1. Aggiungere il certificato della CA emittente al [!DNL trust_cert_ca.pem], che è installato nel **Certificati** directory del client e di ogni server in ogni cluster a cui si accede utilizzando questo certificato personalizzato.

1. Ottieni un certificato personalizzato per ogni server del cluster con le seguenti condizioni:

   1. Il certificato è formattato come [!DNL .pem] certificato.
   1. Il certificato contiene la sua chiave e non è crittografato (ovvero non ha una frase di password/pass).

      Un certificato contiene la relativa chiave con una delle seguenti righe:

      ```
      BEGIN PRIVATE KEY
      BEGIN RSA PRIVATE KEY
      ```

      Un modo per rimuovere la frase password da un [!DNL .pem] certificato:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Il certificato ha la NC, O, OU, ecc. come richiesto per questo client nei server [!DNL Access Control.cfg] file.
   1. Il certificato è stato rilasciato con un *scopo&#42;&#42;&#42;* di *client* o *server* **e** *client*).

      Per verificare che un certificato abbia un codice di scopo del server e/o del client, è possibile utilizzare i seguenti comandi:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Per i certificati server, entrambi i comandi devono restituire:

      ```
      custom_communications_cert.pem: OK
      ```

      Per un certificato client, è necessario solo il secondo comando per restituire [!DNL OK].

1. Posiziona il certificato nel **Certificati** directory.
1. In [!DNL Insight.cfg] in *serverInfo* per ogni cluster che desideri utilizzare questo certificato, assicurati che il *certificato client personalizzato* viene denominato, ad esempio:

   ```
   Servers = vector: 1 items
     0 = serverInfo:
       SSL Client Certificate = string:
     <my_custom_client_cert.pem>
   ```

## Configurazione di certificati server personalizzati {#setting-up-custom-server-certificates}

Questa sezione presuppone che sia attivo un cluster in esecuzione, utilizzando i certificati rilasciati da Visual Sciences, e che la configurazione segua le pratiche comuni (ad esempio *Componenti per i server di elaborazione* la directory sul master viene sincronizzata con il *Componenti* directory di tutte le DPU).

1. Aggiungere il certificato della CA emittente al [!DNL trust_cert_ca.pem] che viene installato su ogni server del cluster e su ogni client che deve comunicare con questo cluster.
1. Ottieni un certificato personalizzato per ogni server del cluster con i seguenti requisiti:

   1. Il certificato personalizzato è formattato come [!DNL .pem] certificato.
   1. Il certificato contiene la sua chiave e non è crittografato (ovvero non ha una frase di password/pass).

      Un certificato contiene la relativa chiave se presenta una riga come:

      ```
      BEGIN PRIVATE KEY
      BEGIN RSA PRIVATE KEY
      ```

      Un modo per rimuovere la frase password da un [!DNL .pem] certificato:

      ```
      openssl rsa  -in password-protected-cert.pem -out no-password-cert.pem
      openssl x509 -in password-protected-cert.pem >> no-password.pem
      ```

   1. Il certificato ha la stessa NC del certificato [!DNL server_cert.pem] attualmente installato sul server.
   1. Il certificato è stato rilasciato a fini di *server* e *client*.

      Per verificare che un certificato abbia un codice di scopo del server e/o del client, è possibile utilizzare i seguenti comandi:

      ```
      openssl verify -CAfile trust_ca_cert.pem -purpose sslserver -x509_strict custom_communications_cert.pem
      openssl verify -CAfile trust_ca_cert.pem -purpose sslclient -x509_strict custom_communications_cert.pem
      ```

      Per i certificati server, entrambi i comandi devono restituire:

      ```
      custom_communications_cert.pem: OK
      ```

      Per un certificato client, è necessario solo il secondo comando per restituire [!DNL OK].

1. Installa il certificato personalizzato di ogni server nel **Certificati** directory del server come [!DNL custom_communications_cert.pem].

1. Utilizzando un editor di testo, aggiungi la seguente riga a **Communications.cfg** in entrambi i *Componenti* e *Componenti per i server di elaborazione* directory, direttamente sotto la prima riga ( [!DNL component = CommServer]):

   ```
   Certificate = string: Certificates\\custom_communications_cert.pem
   ```

1. Riavvia tutti i server.

**Informazioni sull’avviso di errore del certificato**

Quando il server o il client Insight cerca un **licenza** nel certificato **Certificati** cerca di convalidare tutti i certificati (tranne [!DNL trust_ca_cert.pem]), rispetto a una copia hardcoded del certificato Insight CA, che non riesce su alcun certificato personalizzato presente nella directory. Il server invia questo avviso:

```
Certificate failed to verify. Error 20 at 0 depth. Desc: unable to get local issuer certificate. Cert details:
```

Questo avviso può essere ignorato in tutta sicurezza.

## Crittografia della stringa {#concept-35da0b53650a4d7e82b240ad27f6d45a}

Crittografa le password e altre stringhe durante la comunicazione tra il client e il server.

<!--
string_encryption.xml
-->

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
