---
description: Istruzioni per l'installazione e la configurazione di Sensor per Apache Server 1.3, Apache Server 2.0.42 o versioni successive o Apache Server 2.2 in esecuzione in Microsoft Windows Server 2000 o versioni successive.
title: Apache Server 1.3, 2, 2.2 o 2.4 su Windows Server 2000 o versioni successive
uuid: e159ed83-6004-4f65-a3b7-502cac1d0862
exl-id: d1bd0fc1-da5b-4183-8270-73c46195f724
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '971'
ht-degree: 1%

---

# Apache Server 1.3, 2, 2.2 o 2.4 su Windows Server 2000 o versioni successive{#apache-server-or-on-windows-server-or-later}

{{eol}}

Istruzioni per l&#39;installazione e la configurazione di Sensor per Apache Server 1.3, Apache Server 2.0.42 o versioni successive o Apache Server 2.2 in esecuzione in Microsoft Windows Server 2000 o versioni successive.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponi già del file di installazione di Sensor per il tuo particolare server web, scaricalo (o ottenerlo dal tuo rappresentante di Adobe) prima di iniziare le seguenti procedure.

* Apache Server 1.3
* Apache Server 2.0.42 o successivo
* Apache Server 2.2 in esecuzione in Microsoft Windows Server 2000 o versione successiva

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

Prima di installare i file di programma, è necessario determinare il punto in cui si desidera mantenere la coda del disco perché è anche il punto in cui è necessario installare i file di programma.Procedura per estrarre e installare i file di programma per Sensor.

Per installare e configurare Sensor, devi eseguire le seguenti operazioni:

1. Sul computer Windows, creare una directory in cui installare i file del programma Sensor. Tenere presente che la coda del disco si trova anche in questa directory, quindi assicurarsi che il dispositivo scelto abbia spazio sufficiente per contenere una coda delle dimensioni necessarie.

   ```
   C:\VisualSensor
   ```

1. Estrai il contenuto del file di installazione nella directory appena creata. Durante questo passaggio, Sensor installa i seguenti file:

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
   <td colname="col2"> Messaggi del Visualizzatore eventi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.dll </td> 
   <td colname="col2"> Modulo di raccolta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>File di foglio di calcolo Excel che gli architetti possono utilizzare per configurare un esperimento controllato. Il sensore non utilizza questo file. </p> </td> 
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
>Il pacchetto di installazione contiene un file di foglio di calcolo denominato TestExperiment.xls. Questo foglio di calcolo è uno strumento che gli architetti utilizzano per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se è possibile scegliere di farlo). È invece possibile copiare il file in un percorso in cui gli architetti possono accedervi o semplicemente estrarre il file dal pacchetto di installazione, in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati da Insight.

## Modificare il file di configurazione del sensore {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

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

Per i server Apache, il raccoglitore è un oggetto dinamico condiviso caricato nel processo del server web.

Per aggiungere il raccoglitore al server web, devi modificare il [!DNL httpd.conf] come descritto di seguito e riavvia il server web.

>[!NOTE]
>
>Se Sensor acquisisce dati per più server Web sul computer server, è necessario eseguire la procedura seguente per ogni server Web.

1. Utilizzando un editor di testo, apri le [!DNL httpd.conf]file per il server web i cui eventi acquisisce Sensor.
1. Aggiungi le due righe seguenti alla fine del file:

   ```
   LoadModule visual_sciences_module modules/mod_visual_sciences.so 
   VisualSciencesConfig /etc/txlogd.conf
   ```

   >[!NOTE]
   >
   >Queste righe sono sensibili all’uso di maiuscole e minuscole. Digitali esattamente come appaiono sopra.

1. Riavviare il processo del server Web (non è necessario riavviare l&#39;intero computer server, è sufficiente riavviare il processo del server Web). Il raccoglitore viene caricato con il server Web e inizia a raccogliere i dati dell&#39;evento e a scriverli nella coda del disco.
