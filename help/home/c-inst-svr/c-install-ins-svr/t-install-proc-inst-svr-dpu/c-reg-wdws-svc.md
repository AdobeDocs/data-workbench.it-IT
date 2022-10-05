---
description: Procedura per avviare Insight Server e registrarlo contemporaneamente come servizio Microsoft Windows.
title: Registrazione di Insight Server come servizio Windows
uuid: 1b3d53ca-d50f-4520-abf5-6d5c40493b88
exl-id: ba74d4c0-5d99-47a4-8b92-c65d0ec514e2
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 3%

---

# Registrazione di Insight Server come servizio Windows{#registering-insight-server-as-a-windows-service}

{{eol}}

Procedura per avviare Insight Server e registrarlo contemporaneamente come servizio Microsoft Windows.

>[!NOTE]
>
>Quando si inizia [!DNL Insight Server] per la prima volta, si connette automaticamente al server licenze Adobe per registrare il certificato digitale. Per completare correttamente il processo di registrazione, è necessario che il computer sia connesso a Internet quando si eseguono i seguenti passaggi.

**Per iniziare [!DNL Insight Server] e registrarlo come servizio Windows**

1. Apri un prompt dei comandi e passa alla sottodirectory bin nella cartella in cui hai installato [!DNL Insight Server].

   Esempio: [!DNL C:\Adobe\Server\bin]

1. Al prompt dei comandi, eseguire il comando seguente per avviare [!DNL Insight Server] e contemporaneamente registrarlo per l&#39;esecuzione come servizio in Microsoft Windows:

   ```
   <filepath>
   InsightServer64.exe /regserver 
   </filepath>
   ```

1. Confermare che [!DNL Insight Server] è in esecuzione correttamente, fai clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Services]**. Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

   1. Nell’elenco dei servizi, individua la voce per **[!DNL Adobe Insight Server]** e confermare che il relativo stato è Avviato e che il relativo tipo di avvio è Automatico.
   1. Chiudere il pannello di controllo Servizi.

1. Per verificare se [!DNL Insight Server] si sono verificati errori durante l&#39;avvio, fare clic su **[!UICONTROL Start]** > **[!UICONTROL Control Panel]** > **[!UICONTROL Administrative Tools]** > **[!UICONTROL Event Viewer]**. Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

   1. Nel riquadro a sinistra del [!DNL Event Viewer] seleziona la finestra **[!UICONTROL Application]** registro.
   1. Nel riquadro a destra, cerca gli eventi con &quot;Adobe&quot; nel [!DNL Source] colonna.
   1. Se trovi un errore da &quot;Adobe&quot;, fai doppio clic sull&#39;errore per visualizzare il [!DNL Event Properties] finestra. Questa finestra fornisce informazioni dettagliate sull’errore.

1. Al termine dell&#39;esame [!DNL Applications] chiudere il Visualizzatore eventi.

L&#39;installazione di [!DNL Insight Server]. [!DNL Insight Server] è progettato per funzionare continuamente. Se si riavvia il computer, [!DNL Insight Server] si riavvia automaticamente. Se devi iniziare e fermarti [!DNL Insight Server] manualmente, è possibile farlo utilizzando il pannello di controllo Servizi di Windows. Come descritto nella sezione seguente, è possibile configurare facoltativamente [!DNL Insight Server] per il riavvio automatico periodicamente.

## Configurazione del servizio per il riavvio automatico {#section-f9bb91614513435f84ee55c0ec8edb13}

[!DNL Insight Server] è progettato per continuare a funzionare ininterrottamente. In genere viene arrestato o avviato solo quando si eseguono attività non frequenti come gli aggiornamenti software o le modifiche dei certificati o in caso di determinati errori di sistema. Non è necessario arrestare o riavviare il [!DNL Insight Server] durante il normale funzionamento del sistema; tuttavia, è possibile configurare il servizio per il riavvio periodico (giornaliero, settimanale o mensile), ad esempio per cancellare i messaggi dell’evento.

**Per configurare le [!DNL Insight Server] riavvio automatico**

1. Passa a [!DNL Components] nella directory in cui è stata installata [!DNL Insight Server].

   Esempio: [!DNL C:\Adobe\Server\Components]

1. Utilizza un editor di testo come Blocco note per creare un nuovo file denominato [!DNL ScheduledRestart.cfg].
1. Immetti il seguente testo nella sezione [!DNL ScheduledRestart.cfg] file:

   ```
   component = ScheduledRestart:  
     Start Time = string: Month DD, YYYY HH:MM:SS TZone 
     Restart Every = string: frequency
   ```

   <table id="table_AC05861E141E4928BE844C8611DEC43D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Per questo valore.. </th> 
      <th colname="col2" class="entry"> Specifica </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <i>Mese GG, AAAA HH:MM:SS TZone</i> </td> 
      <td colname="col2"> <p>L'ora in cui vuoi <span class="keyword"> Insight Server </span> da riavviare per la prima volta. </p> <p>Esempio: 13 agosto 2013 22:30:00 EST </p> <p> <p>Nota: È necessario specificare un fuso orario. Se non specificato, il fuso orario non viene impostato automaticamente sull'ora del sistema. Se desideri implementare un'ora legale o un criterio simile per lo spostamento dell'orologio, è necessario salvare il <span class="filepath"> .dst </span> file contenente le regole appropriate nella directory Base\Dataset\Timezone <span class="keyword"> Insight Server </span> macchina. Per un elenco delle abbreviazioni dei fusi orari supportati e informazioni sull'implementazione dell'ora legale, vedi <a href="../../../../home/c-inst-svr/c-time-zn-cds.md#concept-eed5ba32d5d347cf94b76db83b29f211"> Codici del fuso orario </a>. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <i>frequenza</i> </td> 
      <td colname="col2"> <p>Uno dei seguenti valori: 
       <ul id="ul_C29A40CD8FBB4333B5FA1D9E7DAD35EC"> 
       <li id="li_9FE07DD30C524CBB81C8F7968E7C733E">mese </li> 
       <li id="li_E5E1B97ED8FB43C0BDA496C620D24A4C">settimana </li> 
       <li id="li_E6043B382FAE4B5D85CAADDFA60E4902">giorno </li> 
       </ul> </p> <p>Per indicare la frequenza alla quale si desidera <span class="keyword"> Insight Server </span> da riavviare dopo l'ora iniziale specificata in Start Time. </p> <p>Ad esempio, se desideri <span class="keyword"> Insight Server </span> per riavviare una volta alla settimana, imposterai questo valore su "week". </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Salva il [!DNL ScheduledRestart.cfg] file.

   Verifica che [!DNL ScheduledRestart.cfg] nel [!DNL Components] nella directory in cui è stata installata [!DNL Insight Server].
