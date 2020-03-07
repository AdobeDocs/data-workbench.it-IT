---
description: Istruzioni per l'installazione e la configurazione del sensore per Apache Server 1.3, Apache Server 2.0.42 o versione successiva oppure Apache Server 2.2 in esecuzione in Microsoft Windows Server 2000 o versione successiva.
title: Apache Server 1.3, 2, 2.2 o 2.4 su Windows Server 2000 o versioni successive
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Apache Server 1.3, 2, 2.2 o 2.4 su Windows Server 2000 o versioni successive{#apache-server-or-on-windows-server-or-later}

Istruzioni per l&#39;installazione e la configurazione del sensore per Apache Server 1.3, Apache Server 2.0.42 o versione successiva oppure Apache Server 2.2 in esecuzione in Microsoft Windows Server 2000 o versione successiva.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponete già del file di installazione Sensor per il vostro particolare server Web, scaricatelo (o ottenetelo dal rappresentante Adobe) prima di iniziare le seguenti procedure.

* Apache Server 1.3
* Apache Server 2.0.42 o versione successiva
* Apache Server 2.2 in esecuzione in Microsoft Windows Server 2000 o versione successiva

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

Prima di installare i file del programma, è necessario determinare dove si desidera mantenere la coda del disco, perché è anche dove è necessario installare i file del programma.Procedura per estrarre e installare i file del programma per Sensor.

Per installare e configurare Sensor, devi eseguire le seguenti operazioni:

1. Sul computer Windows, creare una directory in cui installare i file del programma Sensor. Tenere presente che la coda del disco risiede anche in questa directory, quindi assicurarsi che il dispositivo scelto disponga di spazio sufficiente per contenere una coda delle dimensioni necessarie.

   ```
   C:\VisualSensor
   ```

1. Estrarre il contenuto del file di installazione nella directory appena creata. Durante questo passaggio, Sensor installa i file seguenti:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> Messaggi del visualizzatore eventi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.dll </td> 
   <td colname="col2"> Modulo di raccolta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>Un file foglio di calcolo Excel che gli architetti possono utilizzare per configurare un esperimento controllato. Il sensore non utilizza questo file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificato utilizzato per convalidare il certificato digitale presentato da Insight Server durante il processo di connessione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> Il programma del trasmettitore </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Il file di configurazione Sensor </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Il pacchetto di installazione contiene un foglio di calcolo denominato TestExperiment.xls. Questo foglio di calcolo è uno strumento che gli architetti usano per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se potete scegliere di farlo). Potreste desiderare, invece, copiare il file in una posizione in cui gli architetti possano accedervi o semplicemente estrarre il file dal pacchetto di installazione in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati di Insight.

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

## Aggiungere l&#39;agente di raccolta al server Web {#section-c5b83ae4ebce430aa764f951e849b333}

Per i server Apache, l&#39;agente di raccolta è un oggetto condiviso dinamico caricato nel processo del server Web.

Per aggiungere l’agente di raccolta al server Web, è necessario modificare il [!DNL httpd.conf] file come descritto di seguito e riavviare il server Web.

>[!NOTE]
>
>Se Sensor sta acquisendo dati per più server Web sul computer server, è necessario eseguire la procedura seguente per ciascun server Web.

1. Utilizzando un editor di testo, aprite il [!DNL httpd.conf]file per il server Web i cui eventi Sensor acquisiscono.
1. Aggiungete le due righe seguenti alla fine del file:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Queste righe sono con distinzione tra maiuscole e minuscole. Digitate esattamente come appaiono sopra.

1. Riavviate il processo del server Web (non è necessario riavviare l&#39;intero computer del server, ma è sufficiente riavviare il processo del server Web). L&#39;agente di raccolta viene caricato con il server Web e inizia a raccogliere i dati dell&#39;evento e a scriverli nella coda del disco.

