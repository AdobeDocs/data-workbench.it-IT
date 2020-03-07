---
description: Istruzioni su come installare e configurare Apache Server 2.0.40, 2.0.42 o versioni successive, Apache Server 2.2 o Apache Server 2.4 su Linux, Sun Solaris o FreeBSD.
title: Apache Server 2.0.40, 2.0.42 o versioni successive e Apache Server 2.2 o 2.4 su Linux, Solaris o FreeBSD
uuid: 3703e2c1-5b8d-4def-b146-49e59d78a669
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Apache Server 2.0.40, 2.0.42 o versioni successive e Apache Server 2.2 o 2.4 su Linux, Solaris o FreeBSD{#apache-server-or-later-and-apache-server-or-on-linux-solaris-or-freebsd}

Istruzioni su come installare e configurare Apache Server 2.0.40, 2.0.42 o versioni successive, Apache Server 2.2 o Apache Server 2.4 su Linux, Sun Solaris o FreeBSD.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponete già del file di installazione Sensor per il vostro particolare server Web, scaricatelo (o ottenetelo dal rappresentante Adobe) prima di iniziare le seguenti procedure.

Per installare e configurare Sensor, devi eseguire i seguenti passaggi di alto livello:

Sono supportati i seguenti server Apache:

* Apache Server 2.0.40 eseguito con RedHat Linux 7.x o versione successiva oppure con Sun Solaris SPARC 2.6 o versione successiva.
* Apache Server 2.0.40, 2.0.42 o versioni successive, Apache Server 2.2 o Apache Server 2.4 su Linux, Sun Solaris o FreeBSD
* Apache Server 2.0.42 o versione successiva eseguito con RedHat Linux 7.x o versione successiva, Sun Solaris SPARC 2.6 o versione successiva, SUSE Linux 9.x o versione successiva o FreeBSD 5.3.
* Apache Server 2.0.42 o versione successiva con versioni a 64 bit di RedHat Linux ES 4 e ES 5.
* Apache Server 2.2 in esecuzione con RedHat Linux 7.x o versioni successive o Sun Solaris SPARC 2.6 o versioni successive.
* Apache Server 2.4 in esecuzione con RedHat Linux 7.x o versione successiva, o Sun Solaris x86_64 o FreeBSD

>[!NOTE]
>
>Sebbene le istruzioni per installare Sensor sui server Web che eseguono Apache Server versioni 2.0.40, 2.0.42 o successive (32 bit e 64 bit) o 2.2 siano le stesse (tranne nei casi in cui indicato nelle procedure seguenti), i file di installazione per ciascuna versione sono diversi. Prima di installare il sensore, assicurarsi di aver ricevuto i file di installazione corretti per le versioni di Apache Server e del sistema operativo in esecuzione.

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedura per estrarre e installare i file di programma per Sensor.

1. Accedete come utente principale o come utente con autorizzazione principale.
1. Decomprimete e decomprimete il file di installazione utilizzando il seguente comando:

   * In Linux:

      ```
      tar -zxf installationFilename
      ```

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

   * Su Solaris:

1. Copiare i file di programma non imballati nelle directory indicate nella tabella seguente:

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
   <td colname="col3"> <i> IBMHttpServer/module</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Il programma del trasmettitore. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>—OR—</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
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
>Il pacchetto di installazione contiene un foglio di calcolo denominato TestExperiment.xls. Questo foglio di calcolo è uno strumento che gli architetti usano per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se potete scegliere di farlo). Potreste desiderare, invece, copiare il file in una posizione in cui gli architetti possano accedervi o semplicemente estrarre il file dal pacchetto di installazione in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati di Insight.

**Autorizzazioni sui file del programma**

>[!NOTE]
>
>Autorizzazioni errate sui file del programma causano la maggior parte dei problemi incontrati durante l&#39;installazione del sensore. Accertatevi di impostare le autorizzazioni esattamente come indicato in questa sezione.
>
>Per impostazione predefinita, i file di programma nel file tar hanno le seguenti autorizzazioni. A seconda della configurazione del sistema, queste impostazioni potrebbero essere modificate (non mascherate) al momento dell’estrazione dei file. Per ripristinare le autorizzazioni alle impostazioni predefinite consigliate, utilizzate i comandi chmod riportati di seguito. Verificate che le directory in cui avete installato i file consentano almeno questo livello di accesso.

| File | Autorizzazioni predefinite | chmod, comando |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- r— r— | chmod 664 |
| trust_ca_cert.pem | rw- r— r— | chmod 664 |

## Abilita accesso al server di runtime {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Passaggi che consentono di accedere al server Time.

1. Utilizzare il client Lotus Domino Administrator per connettersi al server Lotus Domino che esegue Sametime.
1. In Amministrazione Lotus Domino, fare clic sulla scheda File, quindi fare doppio clic su Configurazione standard - stconfig.nsf per aprire il file di configurazione Sametime.
1. Nel file Configurazione standard, aprire il modulo Servizi community e fare doppio clic in un punto qualsiasi del modulo per passare alla modalità di modifica.
1. Impostate il flag di registrazione della chat su &quot;rigoroso&quot; e il tipo di servizio di acquisizione su &quot;0x1000&quot;.
1. Salvate e chiudete il modulo Community Services, quindi chiudete il file di configurazione Time.
1. Riavviate il server di Sametime.

## Modificare il file di configurazione Sensor {#section-de0eb4a646394b61abb6cd5a2b706de0}

Il [!DNL txlogd.conf] file contiene i parametri di configurazione per Sensor.

È necessario modificare questo file per specificare, tra le altre cose, le dimensioni e la posizione del file della coda del disco, l&#39;indirizzo del server di Insight e l&#39;ID che verrà allegato ai dati dell&#39;evento prodotti da questo sensore.

Il file di configurazione contiene i parametri obbligatori e i parametri facoltativi.

* **I parametri** richiesti sono impostazioni che dovete specificare quando installate Sensor. Senza queste impostazioni, il sensore non viene eseguito correttamente.
* **I parametri** facoltativi sono impostazioni predefinite per valori predefiniti (che è possibile modificare) o per abilitare funzioni facoltative.

**Per modificare il file di configurazione Sensor**

* Aprite il [!DNL /etc/txlogd.conf] file in un editor di testo e impostate i parametri richiesti, nonché eventuali parametri opzionali desiderati.
* Salvate e chiudete il file.

**Per modificare il file di configurazione Sensor**

1. Aprite il [!DNL /etc/txlogd.conf] file in un editor di testo e impostate i parametri richiesti, nonché eventuali parametri opzionali desiderati.
1. Salvate e chiudete il file.

## Avviare il trasmettitore e creare la coda del disco {#section-55630de65f264274aefd771da2002852}

Dopo aver configurato il file txlogd.conf, potete avviare il programma di trasmettitore, registrarlo come servizio Windows e creare la coda del disco.

1. Se la directory in cui risiede la coda del disco non esiste già, crearla. Verificate che la directory fornisca sia il modulo di raccolta che il programma di trasmettitore con accesso in lettura/scrittura al file.

   Per ulteriori informazioni sulle autorizzazioni richieste dai file della coda del disco, vedere Autorizzazioni per i file UNIX Sensor.
1. Sul computer in cui è installato Sensor, eseguire il comando seguente per avviare il trasmettitore:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * L&#39;opzione &quot;i&quot; di questo comando avvia il trasmettitore in &quot;modalità interattiva&quot;. Questa modalità visualizza i messaggi del trasmettitore sullo schermo e consente di interagire con il trasmettitore utilizzando i comandi della tastiera.
   * L&#39;opzione &quot;c&quot; indirizza il trasmettitore a creare la coda del disco.
   * L&#39;opzione &quot;f&quot; specifica la posizione del file di configurazione.
   Per ulteriori informazioni sulle opzioni che potete utilizzare quando avviate il trasmettitore, consultate Opzioni della riga di comando del trasmettitore sensore.

1. Verificate che il trasmettitore abbia creato la coda del disco nella posizione specificata nel parametro QueueFile e nella dimensione specificata nel parametro QueueSize.
1. Se la coda non è stata creata correttamente, digitate Ctrl+C per terminare il trasmettitore, quindi eseguite le seguenti operazioni:

   1. Esaminate il file txtlogd.conf e verificate che i parametri QueueFile e QueueSize siano impostati correttamente.
   1. Verificare che il dispositivo a cui è assegnata la coda di dischi sia operativo e che disponga di spazio sufficiente per contenere un file delle dimensioni specificate nel parametro QueueSize.
   1. Effettuare le correzioni necessarie e ripetere la procedura.

## Aggiungere l&#39;agente di raccolta al server Web {#section-c5b83ae4ebce430aa764f951e849b333}

Per i server HTTP IBM, l&#39;agente di raccolta è un oggetto condiviso dinamico caricato nel processo del server Web.

Per aggiungere l&#39;agente di raccolta al server Web, è necessario modificare il file httpd.conf come descritto di seguito e riavviare il server Web.

Se Sensor sta acquisendo dati per più server Web sul computer server, è necessario eseguire la procedura seguente per ciascun server Web.

1. Utilizzando un editor di testo, aprite il file httpd.conf per il server Web i cui eventi Sensor acquisiscono.
1. Aggiungete le due righe seguenti alla fine del file:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Queste righe sono con distinzione tra maiuscole e minuscole. Digitate esattamente come appaiono sopra.

1. Riavviate il processo del server Web (non è necessario riavviare l&#39;intero computer del server, ma è sufficiente riavviare il processo del server Web). L&#39;agente di raccolta viene caricato con il server Web e inizia a raccogliere i dati dell&#39;evento e a scriverli nella coda del disco.

## Prova del sensore {#section-0dae181ef8884f10a57f6cfda8500969}

Verificate che il raccoglitore raccolga i dati dell&#39;evento e che il trasmettitore li trasmetta al server di insight di destinazione.

>[!NOTE]
>
>Per verificare che il trasmettitore possa inviare correttamente i dati dell&#39;evento al server di Insight, accertatevi che il server di Insight di destinazione sia installato ed in esecuzione prima di iniziare il test seguente.

1. Se il trasmettitore non è già in esecuzione, riavviarlo utilizzando il seguente comando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Aprite un browser (su qualsiasi computer) e richiedete una pagina dal server Web su cui è in esecuzione Sensor (accertatevi di selezionare una pagina che il sensore sta monitorando).
1. Dopo aver inviato la richiesta, controllate la console del trasmettitore per i messaggi che indicano l&#39;invio dei dati dell&#39;evento al server di visualizzazione di destinazione.
1. Se Sensor non trasmette correttamente i dati, verificare che:

   * Il server di destinazione Insight è in esecuzione.
   * I parametri ServerAddress e ServerPort sono impostati correttamente in txtlogd.conf. Se è stato specificato ServerAddress utilizzando un nome server, provare a utilizzare il relativo indirizzo IP numerico.
   * Il valore del parametro CertName corrisponde esattamente al nome comune che viene visualizzato sul certificato digitale del server Insight di destinazione.

## Aggiungere il trasmettitore allo script di avvio del sistema {#section-19a38f27c9f44adf88f8910f5ed483a3}

Informazioni sul caricamento automatico del trasmettitore nello script di avvio del sistema.

Per fare in modo che il trasmettitore si carichi automaticamente al riavvio del server Web, aggiungere il seguente comando (che avvia il trasmettitore) allo script di avvio del sistema:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Questo comando avvia il trasmettitore come un demone. I messaggi di funzionamento e di errore generati dal trasmettitore vengono scritti in syslog.
