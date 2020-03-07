---
description: Istruzioni per l'installazione e la configurazione del sensore sulla famiglia di server Web che si sono evoluti dal server Web Netscape Enterprise originale in esecuzione su computer Linux o Solaris. Include i server di sistema Netscape Enterprise, iPlanet, Sun ONE e Sun Java su Linux o Solaris.
title: Netscape Enterprise su Linux o Solaris
uuid: 47ea614c-d45c-4ab4-a8fe-ed9227da4582
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Netscape Enterprise su Linux o Solaris{#netscape-enteprise-on-linux-or-solaris}

Istruzioni per l&#39;installazione e la configurazione del sensore sulla famiglia di server Web che si sono evoluti dal server Web Netscape Enterprise originale in esecuzione su computer Linux o Solaris. Include i server di sistema Netscape Enterprise, iPlanet, Sun ONE e Sun Java su Linux o Solaris.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponete già del file di installazione Sensor per il vostro particolare server Web, scaricatelo (o ottenetelo dal rappresentante Adobe) prima di iniziare le seguenti procedure.

Sensor supporta i seguenti server in esecuzione con RedHat Linux 7.x o versioni successive o Sun Solaris SPARC 2.6 o versioni successive:

* Netscape Enterprise Server 3.6 o successivo
* iPlanet Web Server 4.0 o successivo

Sensore supporta questi server in esecuzione con RedHat Linux 7.x o successivo o Sun Solaris 8.x o successivo:

* Sun ONE Web Server 6.0 o successivo
* Sun Java System Web Server 6.1 o successivo

Il sensore supporta questi server in esecuzione in Sun Solaris x86 9 o versione successiva:

* Sun Java System Web Server 6.1 o successivo

>[!NOTE]
>
>Il file di installazione per questa famiglia di server Web è elencato come &quot;Netscape Solaris Sensor&quot; o &quot;Netscape LINUX Sensor&quot; nel sito di download di Adobe.

Per installare e configurare Sensor, devi eseguire le seguenti operazioni:

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedura per estrarre e installare i file di programma per Sensor.

1. Accedete come utente principale o come utente con autorizzazione principale.
1. Decomprimete e decomprimete il file di installazione utilizzando il seguente comando:

   ```
   gunzip installationFilename.tar.gz 
   
       tar -xf installationFilename.tar
   ```

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
   <td colname="col1"> aol_visual_sciences.so </td> 
   <td colname="col2"> Modulo di caricamento del raccoglitore. </td> 
   <td colname="col3"> <i>/usr/local/aolserver/visual_sciences</i> </td> 
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

## Modificare il file di configurazione Sensor {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

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

## Aggiungere l&#39;agente di raccolta al server AOL {#section-c5b83ae4ebce430aa764f951e849b333}

Per AOLServer, l&#39;agente di raccolta è un oggetto condiviso dinamico caricato nel processo del server Web.

Per aggiungere l&#39;agente di raccolta al server AOL, è necessario modificare il file di configurazione del server come descritto di seguito e riavviare il server AOL. Solitamente il file di configurazione del server è denominato nsd.tcl e si trova nella directory in cui è installato AOL Server.

1. Aprite il file di configurazione in un editor di testo e individuate la sezione seguente:

   ```
   ns_section "ns/server/${servername}/modules" 
   ```

1. Aggiungete la riga seguente. (Aggiungi come singola istruzione. Ignora ritorno a capo automatico come illustrato di seguito.

   ```
   ns_param aol_visual_sciences /usr/local/aolserver/visual_sciences/aol_visual_sciences.so 
   ```

1. Create una nuova sezione come segue.

   ```
   ns_section "ns/server/${servername}/module/aol_visual_sciences"
   ```

1. A questa nuova sezione, aggiungere la riga:

   ```
   ns_param    VisualSciencesConfig    /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Queste righe sono con distinzione tra maiuscole e minuscole. Digitate esattamente come appaiono sopra.

1. Riavviare il server AOL. Il raccoglitore viene caricato e inizierà a raccogliere i dati dell&#39;evento e a scriverli nella coda del disco.

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

Questo comando avvia il trasmettitore come un demone. I messaggi operativi ed di errore generati dal trasmettitore sono scritti [!DNL syslog].

L&#39;impostazione predefinita di Solaris è 60. In base ai test condotti con Sensor, che utilizza tre semafori per ogni istanza, Adobe consiglia di usare 1024 come impostazione. Questo numero è sufficientemente elevato da consentire il funzionamento del sensore insieme ad altre applicazioni sul server che possono richiedere dei semafori, ma non influisce sulle prestazioni. Per sostenere questa raccomandazione, si prega di notare che Adrian Cockcroft ha dichiarato quanto segue nel suo libro Sun Performance and Tuning (Prentice Hall, ottobre 1994): &quot;I database tendono a utilizzare un sacco di memoria condivisa e di impostazioni del semaforo. che non incidono sulle prestazioni; fintanto che sono abbastanza grandi, i programmi funzioneranno.&quot;
