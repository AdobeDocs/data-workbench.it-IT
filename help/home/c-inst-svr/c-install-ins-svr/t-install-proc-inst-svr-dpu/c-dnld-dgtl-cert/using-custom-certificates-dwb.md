---
description: Istruzioni per l'uso dei certificati personalizzati.
title: Uso di certificati personalizzati in Workbench dati
uuid: c3a2db27-bdb2-44b3-95dd-65eedd05c957
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Uso di certificati personalizzati in Workbench dati{#using-custom-certificates-in-data-workbench}

Istruzioni per l&#39;uso dei certificati personalizzati.

Un certificato utilizzato dal client o dal server di Workbench dati deve essere firmato da un&#39;autorità di certificazione (Certificate Authority) affidabile. I clienti di Workbench dati ricevono i certificati firmati da Visual Sciences CA. Questi certificati sono affidabili dal software Workbench dati, dal momento che [!DNL trust_ca_cert.pem] (fornito insieme al software Insight e memorizzato nella directory **Certificates** di server e client) contiene un certificato *CA* Root per Visual Sciences CA. Questi certificati vengono utilizzati sia per la licenza del software che per l&#39;autenticazione quando client e server comunicano tra loro utilizzando SSL. Solo i certificati rilasciati dalla CA di Visual Sciences possono essere utilizzati per la licenza, ma altri certificati possono essere utilizzati per la comunicazione e l&#39;autenticazione. I certificati rilasciati da CA diverse da Visual Sciences sono indicati di seguito come certificati *personalizzati.*

**Nota importante:** Per server e client, il software Workbench dati utilizza i file di certificato installati nella directory **Certificati** del client o del server o i certificati esplicitamente identificati nella relativa configurazione. Tuttavia, potete anche utilizzare l&#39;archivio [certificati di](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/crypto-api.md#concept-4acb13b7de9340ea8cde8ad84b93358d) Windows per i client.

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

1. Utilizzando un editor di testo, aggiungi la riga seguente al file **Communications.cfg** sia in directory *Components* che *Components for Processing Servers* , direttamente sotto la prima riga ([!DNL component = CommServer]):

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
