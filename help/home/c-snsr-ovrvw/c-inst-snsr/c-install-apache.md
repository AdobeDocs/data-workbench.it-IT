---
description: Istruzioni su come installare e configurare Apache Server 2.0.40, 2.0.42 o versioni successive, Apache Server 2.2 o Apache Server 2.4 su Linux, Sun Solaris o FreeBSD.
title: Apache Server 2.0.40, 2.0.42 o versioni successive e Apache Server 2.2 o 2.4 su Linux, Solaris o FreeBSD
uuid: 3703e2c1-5b8d-4def-b146-49e59d78a669
exl-id: d5b943be-e9ca-4601-88c7-bb2bfdc0d080
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1546'
ht-degree: 1%

---

# Apache Server 2.0.40, 2.0.42 o versioni successive e Apache Server 2.2 o 2.4 su Linux, Solaris o FreeBSD{#apache-server-or-later-and-apache-server-or-on-linux-solaris-or-freebsd}

{{eol}}

Istruzioni su come installare e configurare Apache Server 2.0.40, 2.0.42 o versioni successive, Apache Server 2.2 o Apache Server 2.4 su Linux, Sun Solaris o FreeBSD.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponi già del file di installazione di Sensor per il tuo particolare server web, scaricalo (o ottenerlo dal tuo rappresentante di Adobe) prima di iniziare le seguenti procedure.

Per installare e configurare Sensor, devi eseguire i seguenti passaggi di alto livello:

Sono supportati i seguenti server Apache:

* Apache Server 2.0.40 in esecuzione con RedHat Linux 7.x o successivo, o Sun Solaris SPARC 2.6 o successivo.
* Apache Server 2.0.40, 2.0.42 o versioni successive, Apache Server 2.2 o Apache Server 2.4 su Linux, Sun Solaris o FreeBSD
* Apache Server 2.0.42 o successivo in esecuzione con RedHat Linux 7.x o successivo, Sun Solaris SPARC 2.6 o successivo, SUSE Linux 9.x o successivo, o FreeBSD 5.3.
* Apache Server 2.0.42 o successivo in esecuzione in versioni a 64 bit di RedHat Linux ES 4 e ES 5.
* Apache Server 2.2 in esecuzione con RedHat Linux 7.x o successivo o Sun Solaris SPARC 2.6 o successivo.
* Apache Server 2.4 in esecuzione con RedHat Linux 7.x o successivo, o Sun Solaris x86_64, o FreeBSD

>[!NOTE]
>
>Anche se le istruzioni per installare Sensor su server web che eseguono Apache Server versioni 2.0.40, 2.0.42 o successive (32-bit e 64-bit) o 2.2 sono le stesse (salvo se indicato nelle procedure seguenti), i file di installazione per ogni versione sono diversi. Prima di installare il sensore, assicurati di aver ricevuto i file di installazione corretti per le versioni di Apache Server e del sistema operativo in esecuzione.

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedura per estrarre e installare i file di programma per Sensor.

1. Accedi come utente principale o come utente con autorità radice.
1. Decomprimi e decomprimi il file di installazione utilizzando il seguente comando:

   * Su Linux:

      ```
      tar -zxf installationFilename
      ```

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

   * Su Solaris:

1. Copia i file di programma decompattati nelle directory identificate nella tabella seguente:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Target Directory </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> Modulo di caricamento del raccoglitore. </td> 
   <td colname="col3"> <i> IBMHttpServer/modules</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Il programma del trasmettitore. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>—OPPURE—</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Il file di configurazione Sensor. </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificato utilizzato per convalidare il certificato digitale presentato da Insight Server durante il processo di connessione </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Il pacchetto di installazione contiene un file di foglio di calcolo denominato TestExperiment.xls. Questo foglio di calcolo è uno strumento che gli architetti utilizzano per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se è possibile scegliere di farlo). È invece possibile copiare il file in un percorso in cui gli architetti possono accedervi o semplicemente estrarre il file dal pacchetto di installazione, in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati da Insight.

**Autorizzazioni sui file del programma**

>[!NOTE]
>
>Autorizzazioni errate sui file di programma causano la maggior parte dei problemi incontrati durante l&#39;installazione di Sensor. Assicurati di impostare le autorizzazioni esattamente come indicato in questa sezione.
>
>Per impostazione predefinita, i file di programma nel file tar hanno le seguenti autorizzazioni. A seconda della configurazione del sistema, queste impostazioni potrebbero essere modificate (non mascherate) durante l’estrazione dei file. Per ripristinare le autorizzazioni alle impostazioni predefinite consigliate, utilizza i comandi chmod riportati di seguito. Controlla che le directory in cui hai installato i file consentano almeno questo livello di accesso.

| File | Autorizzazioni predefinite | comando chmod |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- r— r— | chmod 664 |
| trust_ca_cert.pem | rw- r— r— | chmod 664 |

## Abilitare l’accesso al server Sametime {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Passaggi che consentono di accedere al server Sametime.

1. Utilizzare il client Lotus Domino Administrator per connettersi al server Lotus Domino che esegue Sametime.
1. In Amministrazione Lotus Domino, fare clic sulla scheda File, quindi fare doppio clic su Configurazione Sametime - stconfig.nsf per aprire il file Configurazione Sametime.
1. Nel file di configurazione del tempo stesso, apri il modulo Servizi della community e fai doppio clic in un punto qualsiasi del modulo per accedere alla modalità di modifica.
1. Imposta il flag di registrazione chat su &quot;rigoroso&quot; e il tipo di servizio di acquisizione su &quot;0x1000&quot;.
1. Salva e chiudi il modulo Community Services , quindi chiudi il file di configurazione Sametime.
1. Riavvia il server Sametime.

## Modificare il file di configurazione del sensore {#section-de0eb4a646394b61abb6cd5a2b706de0}

La [!DNL txlogd.conf] il file contiene i parametri di configurazione per Sensor.

È necessario modificare questo file per specificare, tra l’altro, le dimensioni e la posizione del file della coda del disco, l’indirizzo di Insight Server e l’ID che verrà allegato ai dati dell’evento prodotti da questo sensore.

Il file di configurazione contiene i parametri richiesti e i parametri facoltativi.

* **Parametri richiesti** sono impostazioni che è necessario specificare quando si installa Sensor. Senza queste impostazioni, il sensore non viene eseguito correttamente.
* **Parametri opzionali** sono impostazioni predefinite per valori predefiniti (che è possibile modificare) o per l’abilitazione di funzionalità facoltative.

**Per modificare il file di configurazione Sensor**

* Apri [!DNL /etc/txlogd.conf] in un editor di testo e imposta i parametri richiesti ed eventuali parametri facoltativi desiderati.
* Salva e chiudi il file.

**Per modificare il file di configurazione Sensor**

1. Apri [!DNL /etc/txlogd.conf] in un editor di testo e imposta i parametri richiesti ed eventuali parametri facoltativi desiderati.
1. Salva e chiudi il file.

## Avviare il trasmettitore e creare la coda del disco {#section-55630de65f264274aefd771da2002852}

Dopo aver configurato il file txlogd.conf, è possibile avviare il programma del trasmettitore, registrarlo come servizio Windows e creare la coda del disco.

1. Se la directory in cui si trova la coda del disco non esiste già, crearla. Assicurati che la directory offra sia il modulo di raccolta che il programma del trasmettitore con accesso in lettura/scrittura al file.

   Per ulteriori informazioni sulle autorizzazioni richieste dai file della coda del disco, vedere Autorizzazioni dei file UNIX di Sensor.
1. Sul computer in cui è installato Sensor, eseguire il seguente comando per avviare il trasmettitore:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * L&#39;opzione &quot;i&quot; in questo comando avvia il trasmettitore in &quot;modalità interattiva&quot;. Questa modalità visualizza i messaggi del trasmettitore sullo schermo e consente inoltre di interagire con il trasmettitore utilizzando i comandi della tastiera.
   * L&#39;opzione &quot;c&quot; indirizza il trasmettitore a creare la coda del disco.
   * L&#39;opzione &quot;f&quot; specifica la posizione del file di configurazione.

   Per ulteriori informazioni sulle opzioni che è possibile utilizzare quando si avvia il trasmettitore, vedere Opzioni della riga di comando del Sensor Transmitter.

1. Verificare che il trasmettitore abbia creato la coda del disco nella posizione specificata nel parametro QueueFile e delle dimensioni specificate nel parametro QueueSize.
1. Se la coda non è stata creata correttamente, digita Ctrl+C per terminare il trasmettitore, quindi procedi come segue:

   1. Esamina il file txtlogd.conf e verifica che i parametri QueueFile e QueueSize siano impostati correttamente.
   1. Verificare che il dispositivo a cui è assegnata la coda del disco sia operativo e che disponga di spazio sufficiente per contenere un file delle dimensioni specificate nel parametro QueueSize.
   1. Apportare le correzioni necessarie e ripetere la procedura.

## Aggiungere l&#39;agente di raccolta al server Web {#section-c5b83ae4ebce430aa764f951e849b333}

Per i server HTTP IBM, il raccoglitore è un oggetto dinamico condiviso caricato nel processo del server web.

Per aggiungere il raccoglitore al server web, devi modificare il file httpd.conf come descritto di seguito e riavviare il server web.

Se Sensor acquisisce dati per più server Web sul computer server, è necessario eseguire la procedura seguente per ogni server Web.

1. Utilizzando un editor di testo, apri il file httpd.conf per il server web i cui eventi vengono acquisiti da Sensor.
1. Aggiungi le due righe seguenti alla fine del file:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Queste righe sono sensibili all’uso di maiuscole e minuscole. Digitali esattamente come appaiono sopra.

1. Riavviare il processo del server Web (non è necessario riavviare l&#39;intero computer server, è sufficiente riavviare il processo del server Web). Il raccoglitore viene caricato con il server Web e inizia a raccogliere i dati dell&#39;evento e a scriverli nella coda del disco.

## Test del sensore {#section-0dae181ef8884f10a57f6cfda8500969}

Verifica che il raccoglitore stia raccogliendo i dati dell’evento e che il trasmettitore lo stia trasmettendo al target Insight Server.

>[!NOTE]
>
>Per verificare che il trasmettitore possa inviare correttamente i dati dell’evento a Insight Server, assicurati che Insight Server di destinazione sia installato ed in esecuzione prima di iniziare il test seguente.

1. Se il trasmettitore non è già in esecuzione, riavviarlo utilizzando il seguente comando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Apri un browser (su qualsiasi computer) e richiedi una pagina dal server web su cui è in esecuzione Sensor (assicurati di selezionare una pagina che Sensor sta monitorando).
1. Dopo aver effettuato la richiesta, controlla nella console del trasmettitore i messaggi che indicano che sta inviando dati evento a Insight Server di destinazione.
1. Se il sensore non trasmette correttamente i dati, verifica che:

   * Target Insight Server è in esecuzione.
   * I parametri ServerAddress e ServerPort sono impostati correttamente in txtlogd.conf. Se ServerAddress è stato specificato utilizzando un nome server, provare a utilizzare il relativo indirizzo IP numerico.
   * Il valore del parametro CertName corrisponde esattamente al nome comune visualizzato nel certificato digitale di Target Insight Server.

## Aggiungi il trasmettitore allo script di avvio del sistema {#section-19a38f27c9f44adf88f8910f5ed483a3}

Informazioni sul caricamento automatico del trasmettitore nello script di avvio del sistema.

Per garantire che il trasmettitore venga caricato automaticamente al riavvio del server Web, aggiungi il seguente comando (che avvia il trasmettitore) allo script di avvio del sistema:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Questo comando avvia il trasmettitore come un daemon. I messaggi di funzionamento ed errore generati dal trasmettitore vengono scritti nel registro di sistema.
