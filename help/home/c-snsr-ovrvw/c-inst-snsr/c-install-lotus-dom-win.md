---
description: Istruzioni su come installare e configurare Sensor per Lotus Domino Server 6 per Windows 3.1 o versione successiva in esecuzione in Microsoft Windows Server 2000 o versione successiva.
title: Lotus Domino Server su Windows Server 2000 o versione successiva
uuid: e3fb1478-92d1-4488-a4b8-244d258cc00a
exl-id: b736c8e6-0642-419c-8715-6586c21f2182
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 2%

---

# Lotus Domino Server su Windows Server 2000 o versione successiva{#lotus-domino-server-on-windows-server-or-later}

{{eol}}

Istruzioni su come installare e configurare Sensor per Lotus Domino Server 6 per Windows 3.1 o versione successiva in esecuzione in Microsoft Windows Server 2000 o versione successiva.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponi già del file di installazione di Sensor per il tuo particolare server web, scaricalo (o ottenerlo dal tuo rappresentante di Adobe) prima di iniziare le seguenti procedure.

Per installare e configurare Sensor, devi eseguire le seguenti operazioni:

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

1. Sul computer Lotus Domino, creare una directory per installare i file del programma Sensor. Tenere presente che la coda del disco si trova anche in questa directory, quindi assicurarsi che il dispositivo scelto abbia spazio sufficiente per contenere una coda delle dimensioni necessarie.

   ```
   C:\VisualSensor
   ```

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

## Configurare Lotus Domino Server {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

Procedura per configurare il server Lotus Domino.

1. Accedere all&#39;amministratore di Lotus Domino e fare clic su **[!UICONTROL Domain]**.

   ![](assets/dom_svr1.png)

1. In Amministrazione Lotus Domino fare clic su **[!UICONTROL Configuration]**.

   ![](assets/dom_svr2.png)

1. Espandi il nodo Server e fai clic su **[!UICONTROL Current Server Document]**.

   ![](assets/dom_svr3.png)

1. Fai clic su **[!UICONTROL Current Server Document]**, quindi su **[!UICONTROL Internet Protocols]**.

   ![](assets/dom_svr4.png)

1. Nella scheda HTTP, sotto la sezione DSAPI, fai doppio clic dopo la parola [!DNL ndolextn].

   ![](assets/dom_svr5.png)

1. Press **[!UICONTROL Enter]** e digitare il percorso della [!DNL dominosensor.dll] file.

   ![](assets/dom_svr6.png)

1. Fai clic su **[!UICONTROL Save & Close]**.

   ![](assets/dom_svr7.png)

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

1. Dal menu Start in Windows, selezionare **Accessori** > **Prompt dei comandi**.

1. Nella finestra del prompt dei comandi, passare alla directory in cui è stato installato Sensor ed eseguire il seguente comando:

   ```
   txlog /regserver
   ```

   Questo comando avvia il trasmettitore, crea la coda del disco e registra Sensor come servizio Windows.

1. Per verificare che il trasmettitore funzioni correttamente, fai clic su **Start > Pannello di controllo Campaign > Strumenti di amministrazione > Servizi**.

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
1. Verifica che il trasmettitore abbia creato la coda del disco ( [!DNL Diskq2000.log]) nella directory in cui sono stati installati i file del programma Sensor e che si tratta della dimensione specificata nel [!DNL QueueSize] nel [!DNL txlogd.conf] file.

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
