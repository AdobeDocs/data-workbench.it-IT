---
description: Istruzioni dettagliate per l'installazione e la configurazione del sensore per un server Apache 1.3.x su RedHat Linux 7.x o versioni successive, SUSE Linux 9.x o versioni successive, Sun Solaris SPARC 2.6 o versioni successive, Sun Solaris x86 9 o versioni successive, FreeBSD 4 o versioni successive o Mac OS X PowerPC.
title: Apache Server 1.3.x su Linux, Sun Solaris, FreeBSD o Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
translation-type: tm+mt
source-git-commit: 98452ba81d71db65c75e3d07712eefa18c003f53
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---


# Apache Server 1.3.x su Linux, Sun Solaris, FreeBSD o Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

Istruzioni dettagliate per l&#39;installazione e la configurazione del sensore per un server Apache 1.3.x su RedHat Linux 7.x o versioni successive, SUSE Linux 9.x o versioni successive, Sun Solaris SPARC 2.6 o versioni successive, Sun Solaris x86 9 o versioni successive, FreeBSD 4 o versioni successive o Mac OS X PowerPC.

I file di programma per Sensor sono pacchetti in un file di installazione che si ottiene dal sito di download del Adobe . Se non disponete già del file di installazione Sensor per il vostro particolare server Web, scaricatelo (o ottenetelo dal rappresentante del Adobe ) prima di iniziare le seguenti procedure.

Per installare e configurare Sensor, devi eseguire i seguenti passaggi di alto livello:

## Installare i file del programma {#section-aae323e252394212bf4096d65fdd280c}

Istruzioni per estrarre e installare i file di programma per Sensor al computer server.

1. Accedete come utente principale o come utente con autorizzazione principale.
1. Decomprimete e decomprimete il file di installazione utilizzando il seguente comando:

   * In Linux:

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * Su Solaris:

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. Copiare i file di programma non imballati nelle directory indicate nella tabella seguente:

<table id="table_A97CF630633C4543A742D96C302D1138"> 
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
   <td colname="col2"> Modulo di carico del collettore </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Il programma del trasmettitore </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--O-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Il file di configurazione Sensor </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificato utilizzato per convalidare il certificato digitale presentato da Insight Server durante il processo di connessione </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Il pacchetto di installazione contiene un foglio di calcolo denominato TestExperiment.xls. Questo foglio di calcolo è uno strumento che gli architetti usano per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se potete scegliere di farlo). Potreste desiderare, invece, copiare il file in una posizione in cui gli architetti possano accedervi o semplicemente estrarre il file dal pacchetto di installazione in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati di Insight.

**Autorizzazioni sui file del programma**

Autorizzazioni errate sui file del programma causano la maggior parte dei problemi incontrati durante l&#39;installazione del sensore.

Accertatevi di impostare le autorizzazioni esattamente come indicato in questa sezione.

Per impostazione predefinita, i file di programma nel file tar hanno le seguenti autorizzazioni. A seconda della configurazione del sistema, queste impostazioni potrebbero essere modificate (non mascherate) al momento dell’estrazione dei file. Per ripristinare le autorizzazioni alle impostazioni predefinite consigliate, utilizzate i comandi chmod riportati di seguito. Verificate che le directory in cui avete installato i file consentano almeno questo livello di accesso.

| File | Autorizzazioni predefinite | chmod, comando |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

## Edit the Sensor configuration file {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

Il [!DNL txlogd.conf] file contiene i parametri di configurazione per Sensor.

È necessario modificare il file per specificare, tra l&#39;altro, le dimensioni della coda del disco, l&#39;indirizzo del server di Insight e l&#39;ID che verrà allegato ai dati prodotti da questo sensore.

Il file di configurazione contiene i parametri obbligatori e i parametri facoltativi.

* I parametri richiesti sono impostazioni che dovete specificare quando installate Sensor. Senza queste impostazioni, il sensore non viene eseguito correttamente.
* I parametri facoltativi sono impostazioni predefinite per valori predefiniti (che è possibile modificare) o per abilitare funzioni facoltative.

Per modificare il file di configurazione Sensor

1. Aprite il file /etc/txlogd.conf in un editor di testo e impostate i parametri richiesti, nonché eventuali parametri facoltativi desiderati.
1. Salvate e chiudete il file.

## Avviare il trasmettitore e creare la coda del disco {#section-a453d912ec3d47aa8e40ccacf527119d}

Istruzioni per creare la coda del disco dopo aver configurato il file txlogd.conf.

1. Se la directory in cui risiede la coda del disco non esiste già, crearla. Verificate che la directory fornisca sia il modulo di raccolta che il programma di trasmettitore con accesso in lettura/scrittura al file.
1. Sul computer in cui è installato Sensor, eseguire il comando seguente per avviare il trasmettitore:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * L&#39;opzione &quot;i&quot; di questo comando avvia il trasmettitore in modalità interattiva. Questa modalità visualizza i messaggi del trasmettitore sullo schermo e consente di interagire con il trasmettitore utilizzando i comandi della tastiera.
   * L&#39;opzione &quot;c&quot; indirizza il trasmettitore a creare la coda del disco.
   * L&#39;opzione &quot;f&quot; specifica la posizione del file di configurazione.

1. Verificate che il trasmettitore abbia creato la coda del disco nella posizione specificata nel parametro QueueFile e nella dimensione specificata nel parametro QueueSize.
1. Se la coda non è stata creata correttamente, digitate Ctrl+C per terminare il trasmettitore, quindi eseguite le seguenti operazioni:

   1. Esaminate il file txtlogd.conf e verificate che i parametri QueueFile e QueueSize siano impostati correttamente.
   1. Verificare che il dispositivo a cui è assegnata la coda di dischi sia operativo e che disponga di spazio sufficiente per contenere un file delle dimensioni specificate nel parametro QueueSize.
   1. Effettuare le correzioni necessarie e ripetere la procedura.

## Aggiungere l&#39;agente di raccolta al server Web {#section-a7fb6425956f4f518ae3a7db091b33d2}

Per i server Apache, l&#39;agente di raccolta è un oggetto condiviso dinamico caricato nel processo del server Web.

Per aggiungere l&#39;agente di raccolta al server Web, è necessario modificare il file httpd.conf come descritto di seguito e riavviare il server Web.

Se Sensor sta acquisendo dati per più server Web sul computer server, è necessario eseguire la procedura seguente per ciascun server Web.

1. Utilizzando un editor di testo, aprite il [!DNL httpd.conf] file per il server Web i cui eventi Sensor acquisisce.
1. Aggiungete le righe seguenti alla fine del file:

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >Queste righe sono con distinzione tra maiuscole e minuscole. Digitate esattamente come appaiono sopra.

1. Riavviate il server Web. L&#39;agente di raccolta viene caricato con il server Web e inizierà a raccogliere i dati dell&#39;evento e a scriverli nella coda del disco.

## Prova del sensore {#section-83d9f60b39a6474f9c76bee3e19b2575}

Avviate il trasmettitore e verificate che possa connettersi correttamente al server Insight e trasmettervi i dati dell&#39;evento.

>[!NOTE]
>
>Per verificare che il trasmettitore possa inviare correttamente i dati dell&#39;evento al server di Insight, accertatevi che il server di Insight di destinazione sia installato ed in esecuzione prima di iniziare il test seguente.

1. Se il trasmettitore non è già in esecuzione, riavviarlo utilizzando il seguente comando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Aprite un browser (su qualsiasi computer) e richiedete una pagina dal server Web su cui è in esecuzione Sensor (accertatevi di selezionare una pagina che il sensore sta monitorando).
1. Dopo aver inviato la richiesta, controllate la console del trasmettitore per i messaggi che indicano l&#39;invio dei dati dell&#39;evento al server di visualizzazione di destinazione.
1. Se Sensor non trasmette correttamente i dati, verifica che:

   * Il server di destinazione Insight è in esecuzione.
   * I parametri [!DNL ServerAddress] e [!DNL ServerPort] sono impostati correttamente in [!DNL txtlogd.conf].

   * Se avete specificato [!DNL ServerAddress] con un nome server, provate a utilizzare il relativo indirizzo IP numerico. Il valore del [!DNL CertName] parametro corrisponde esattamente al nome comune visualizzato sul certificato digitale del server di insight di destinazione.

## Aggiungere il trasmettitore allo script di avvio del sistema {#section-4e1ffa6e043941ab91411d91d596477a}

Informazioni per garantire che il trasmettitore si carichi automaticamente al riavvio del server Web.

Aggiungete il seguente comando (che avvia il trasmettitore) allo script di avvio del sistema.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Questo comando avvia il trasmettitore come un demone. I messaggi di funzionamento e di errore generati dal trasmettitore vengono scritti in syslog.

>[!NOTE]
>
>Alcuni utenti di Solaris potrebbero riscontrare un errore &quot;impossibile acquisire mutex&quot;. Affinché il sensore funzioni correttamente su questi sistemi, è necessario aggiungere o modificare la seguente riga nel file /etc/system:
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>L&#39;impostazione predefinita di Solaris è 60. In base ai test condotti con Sensor, che utilizza tre semafori per ogni istanza,  Adobe consiglia di usare 1024 come impostazione. Questo numero è sufficientemente elevato da consentire il funzionamento del sensore insieme ad altre applicazioni sul server che possono richiedere dei semafori, ma non influisce sulle prestazioni. Per sostenere questa raccomandazione, si prega di notare che Adrian Cockcroft ha dichiarato quanto segue nel suo libro Sun Performance and Tuning (Prentice Hall, ottobre 1994): &quot;I database tendono a utilizzare un sacco di memoria condivisa e di impostazioni del semaforo. che non incidono sulle prestazioni; fintanto che sono abbastanza grandi, i programmi funzioneranno.&quot;

