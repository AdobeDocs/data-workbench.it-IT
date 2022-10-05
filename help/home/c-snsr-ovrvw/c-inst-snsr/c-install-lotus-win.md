---
description: Istruzioni su come installare e configurare Sensor per Lotus Sametime per Windows 3.1 o versione successiva in esecuzione in Microsoft Windows Server 2000 o versione successiva.
title: Lotus Sametime su Windows Server 2000 o versione successiva
uuid: 5e24da54-7ef6-42cf-b693-cc4fd267af93
exl-id: 9292bfca-ad3b-436d-9d22-be67a61b8c05
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1023'
ht-degree: 1%

---

# Lotus Sametime su Windows Server 2000 o versione successiva{#lotus-sametime-on-windows-server-or-later}

{{eol}}

Istruzioni su come installare e configurare Sensor per Lotus Sametime per Windows 3.1 o versione successiva in esecuzione in Microsoft Windows Server 2000 o versione successiva.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponi già del file di installazione di Sensor per il tuo particolare server web, scaricalo (o ottenerlo dal tuo rappresentante di Adobe) prima di iniziare le seguenti procedure.

Per installare e configurare Sensor, devi eseguire i seguenti passaggi di alto livello:

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

Quando si esegue Sensor su Sametime, i file del programma e il file della coda del disco devono trovarsi nella stessa directory.

Pertanto, prima di installare i file del programma, è necessario determinare dove si desidera mantenere la coda del disco, perché è anche in questo caso che è necessario installare i file del programma.

Segui la procedura seguente per estrarre e installare i file di programma per Sensor.

1. Arrestare Lotus Domino Server e il servizio di registrazione chat di Sametime.
1. Sul computer Windows, nella directory Lotus Domino, eliminare o eseguire il backup del file denominato StChatLog.dll.
1. Estrarre il contenuto del file di installazione nella directory Lotus Domino. Durante questo passaggio, Sensor installa i seguenti file:

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
   <td colname="col2"> Messaggi del Visualizzatore eventi </td> 
  </tr> 
  <tr> 
   <td colname="col1"> stchatlog.dll </td> 
   <td colname="col2"> Modulo di raccolta </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>TestExperiment.xls </p> </td> 
   <td colname="col2"> <p>Un file di foglio di calcolo Excel che gli architetti possono utilizzare per configurare un esperimento controllato </p> <p>Il sensore non utilizza questo file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificato utilizzato per convalidare il certificato digitale presentato da Insight Server durante il processo di connessione </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> Il programma del trasmettitore </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd.conf </p> </td> 
   <td colname="col2"> Il file di configurazione Sensor </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Il pacchetto di installazione contiene un file di foglio di calcolo denominato TestExperiment.xls. Questo foglio di calcolo è uno strumento che gli architetti utilizzano per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se è possibile scegliere di farlo). È invece possibile copiare il file in un percorso in cui gli architetti possono accedervi o semplicemente estrarre il file dal pacchetto di installazione, in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati da Insight.

## Abilitare l’accesso al server Sametime {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Passaggi che consentono di accedere al server Sametime.

1. Utilizzare il client Lotus Domino Administrator per connettersi al server Lotus Domino che esegue Sametime.
1. In Amministrazione Lotus Domino, fare clic sulla scheda File, quindi fare doppio clic su Configurazione Sametime - stconfig.nsf per aprire il file Configurazione Sametime.
1. Nel file di configurazione del tempo stesso, apri il modulo Servizi della community e fai doppio clic in un punto qualsiasi del modulo per accedere alla modalità di modifica.
1. Imposta il flag di registrazione chat su &quot;rigoroso&quot; e il tipo di servizio di acquisizione su &quot;0x1000&quot;.
1. Salva e chiudi il modulo Community Services , quindi chiudi il file di configurazione Sametime.
1. Riavvia il server Sametime.

## Modificare il file di configurazione del sensore {#section-de0eb4a646394b61abb6cd5a2b706de0}

Il file txlogd.conf contiene i parametri di configurazione per Sensor.

È necessario modificare questo file per specificare, tra l’altro, le dimensioni e la posizione del file della coda del disco, l’indirizzo di Insight Server e l’ID che verrà allegato ai dati dell’evento prodotti da questo sensore.

Il file di configurazione contiene i parametri richiesti e i parametri facoltativi.

* **Parametri richiesti** sono impostazioni che è necessario specificare quando si installa Sensor. Senza queste impostazioni, il sensore non viene eseguito correttamente.
* **Parametri opzionali** sono impostazioni predefinite per valori predefiniti (che è possibile modificare) o per l’abilitazione di funzionalità facoltative.

**Per modificare il file di configurazione Sensor**

* Apri `<Sensor directory>/txlogd.conf` in un editor di testo e imposta i parametri richiesti ed eventuali parametri facoltativi desiderati.
* Salva e chiudi il file.

## Avviare il trasmettitore e creare la coda del disco {#section-55630de65f264274aefd771da2002852}

Dopo aver configurato il file txlogd.conf, è possibile avviare il programma del trasmettitore, registrarlo come servizio Windows e creare la coda del disco.

1. Dal menu Start in Windows, selezionare Accessori > Prompt dei comandi.
1. Nella finestra del prompt dei comandi, passare alla directory in cui è stato installato Sensor ed eseguire il seguente comando:

   ```
   txlog /regserver
   ```

   Questo comando avvia il trasmettitore, crea la coda del disco e registra Sensor come servizio Windows.

1. Per confermare che il trasmettitore è in esecuzione correttamente, fai clic su Start > Pannello di controllo Campaign > Strumenti di amministrazione > Servizi.

   >[!NOTE]
   >
   >Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

   1. Nell&#39;elenco dei servizi, individuare la voce per Sensor e confermare che il suo stato è Avviato e che il suo tipo di avvio è Automatico.
   1. Chiudere il pannello di controllo Servizi.

1. Per verificare se il trasmettitore ha riscontrato errori durante l&#39;avvio, fai clic su Start > Pannello di controllo Campaign > Strumenti di amministrazione > Visualizzatore eventi per aprire il Visualizzatore eventi.

   >[!NOTE]
   >
   >Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

   1. Nel riquadro a sinistra della finestra Visualizzatore eventi selezionare il registro Applicazioni.
   1. Nel riquadro a destra, cerca gli eventi con &quot;Adobe&quot; nella colonna Origine.
   1. Se si trova un errore da &quot;Adobe&quot;, fare doppio clic sull&#39;errore per visualizzare la finestra Proprietà evento. Questa finestra fornisce informazioni dettagliate sull’errore.

1. Al termine dell&#39;esame del registro Applicazioni, chiudere il Visualizzatore eventi.
1. Verificare che il trasmettitore abbia creato la coda del disco (Diskq2000.log) nella directory in cui sono stati installati i file del programma Sensor e che si tratti della dimensione specificata nel parametro QueueSize nel file txlogd.conf.

   Se la coda non è stata creata correttamente:

   1. Esamina il file txtlogd.conf e verifica che il parametro QueueSize sia impostato correttamente.
   1. Verificare che il dispositivo su cui è installato Sensor disponga di spazio sufficiente per contenere un file delle dimensioni specificate nel parametro QueueSize.
   1. Utilizzando il pannello di controllo Servizi in Windows, arrestare il trasmettitore.
   1. Elimina il file della coda.
   1. Registra nuovamente Sensor come servizio Windows: dal menu Start in Windows, selezionare Accessori > Prompt dei comandi. Nella finestra del prompt dei comandi, passare alla directory in cui è stato installato Sensor ed eseguire il seguente comando:

      ```
      txlog /regserver
      ```

      Il trasmettitore è progettato per funzionare continuamente. Se si riavvia il computer, il trasmettitore si riavvia automaticamente. Se è necessario avviare e arrestare il trasmettitore manualmente, è possibile farlo utilizzando il pannello di controllo Servizi di Windows.

1. Riavviare Lotus Domino Server e il servizio di registrazione chat di Sametime.
