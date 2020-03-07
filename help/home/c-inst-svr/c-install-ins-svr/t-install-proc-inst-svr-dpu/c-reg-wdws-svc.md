---
description: Procedura per avviare Insight Server e registrarlo contemporaneamente come Microsoft Windows Service.
solution: Insight
title: Registrazione di Insight Server come servizio Windows
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Registrazione di Insight Server come servizio Windows{#registering-insight-server-as-a-windows-service}

Procedura per avviare Insight Server e registrarlo contemporaneamente come Microsoft Windows Service.

>[!NOTE]
>
>Quando si avvia [!DNL Insight Server] per la prima volta, si connette automaticamente al server delle licenze Adobe per registrare il certificato digitale. Per completare correttamente il processo di registrazione, è necessario che il computer sia connesso a Internet quando si eseguono i seguenti passaggi.

**Per avviarlo[!DNL Insight Server]e registrarlo come servizio Windows**

1. Aprite un prompt dei comandi e andate alla sottodirectory bin nella cartella in cui avete installato [!DNL Insight Server].

   Esempio: [!DNL C:\Adobe\Server\bin]

1. Al prompt dei comandi, eseguire il comando seguente per avviare [!DNL Insight Server] e registrare contemporaneamente il comando per l&#39;esecuzione come servizio in Microsoft Windows:

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. Per confermare che [!DNL Insight Server] l&#39;esecuzione è corretta, fate clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

   1. Nell&#39;elenco dei servizi, individuare la voce **[!DNL Adobe Insight Server]** e confermare che il relativo stato è Avviato e che il tipo di avvio è Automatico.
   1. Chiudere il pannello di controllo Servizi.

1. Per verificare se [!DNL Insight Server] si sono verificati errori durante l&#39;avvio, fate clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

   1. Nel riquadro a sinistra della [!DNL Event Viewer] finestra, selezionare il **[!UICONTROL Application]** registro.
   1. Nel riquadro a destra, cercate gli eventi con &quot;Adobe&quot; nella [!DNL Source] colonna.
   1. Se si verifica un errore in &quot;Adobe&quot;, fare doppio clic sull&#39;errore per visualizzare la [!DNL Event Properties] finestra. Questa finestra fornisce informazioni dettagliate sull&#39;errore.

1. Al termine dell’analisi del [!DNL Applications] registro, chiudete il visualizzatore eventi.

L&#39;installazione di [!DNL Insight Server]. [!DNL Insight Server] è progettato per essere eseguito in modo continuo. Se si riavvia il computer, [!DNL Insight Server] si riavvia automaticamente. Se è necessario avviare e arrestare [!DNL Insight Server] manualmente, è possibile farlo utilizzando il pannello di controllo Servizi in Windows. Come descritto nella sezione seguente, è possibile configurare il [!DNL Insight Server] servizio in modo che venga riavviato automaticamente periodicamente.

## Configurazione automatica del servizio per il riavvio {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] è progettato per continuare a funzionare senza interruzioni. In genere viene interrotto o avviato solo quando si eseguono attività non frequenti come aggiornamenti software o modifiche di certificati o in caso di determinati errori del sistema. Non è necessario arrestare o riavviare il [!DNL Insight Server] servizio durante il normale funzionamento del sistema; tuttavia, potete configurare il servizio per il riavvio periodico (giornaliero, settimanale o mensile), ad esempio per cancellare i messaggi dell&#39;evento.

**Per configurare il[!DNL Insight Server]servizio per il riavvio automatico**

1. Andate alla [!DNL Components] cartella nella directory in cui avete installato [!DNL Insight Server].

   Esempio: [!DNL C:\Adobe\Server\Components]

1. Usate un editor di testo come Blocco note per creare un nuovo file denominato [!DNL ScheduledRestart.cfg].
1. Immettere il testo seguente nel [!DNL ScheduledRestart.cfg] file:

   ```
   component = ScheduledRestart:  
     Start Time = string: Month DD, YYYY HH:MM:SS TZone 
     Restart Every = string: frequency
   ```

   <table id="table_AC05861E141E4928BE844C8611DEC43D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Per questo valore... </th> 
      <th colname="col2" class="entry"> Specifica </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <i>Mese GG, AAAA HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>Momento in cui si desidera che <span class="keyword"> Insight Server </span> venga riavviato per la prima volta. </p> <p>Esempio: 13 agosto 2013 22:30:00 EST </p> <p> <p>Nota:  È necessario specificare un fuso orario. Se non viene specificato, il fuso orario predefinito non corrisponde all'ora del sistema. Se desiderate implementare un'ora legale o un criterio simile per lo spostamento dell'orologio, dovete salvare il file <span class="filepath"> .dst </span> contenente le regole appropriate nel computer Base\Dataset\Timezone directory on the <span class="keyword"> Insight Server </span> . Per un elenco delle abbreviazioni dei fusi orari supportati e informazioni sull'implementazione dell'ora legale, consultate <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Codici dei fusi orari </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>frequenza</i> </td> 
      <td colname="col2"> <p>Uno dei seguenti valori: 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">mese </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">settimana </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">giorno </li> 
       </ul> </p> <p>Per indicare la frequenza con cui si desidera riavviare <span class="keyword"> Insight Server </span> dopo l’ora iniziale specificata in Ora di inizio. </p> <p>Ad esempio, se si desidera che <span class="keyword"> Insight Server </span> venga riavviato una volta alla settimana, impostare questo valore su "week". </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Save the [!DNL ScheduledRestart.cfg] file.

   Verificate che il [!DNL ScheduledRestart.cfg] file si trovi nella [!DNL Components] cartella nella directory in cui avete installato [!DNL Insight Server].
