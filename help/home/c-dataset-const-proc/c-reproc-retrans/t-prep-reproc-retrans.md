---
description: Passaggi per garantire che la rielaborazione o la riconversione proceda senza problemi e si concluda in tempo per consentire agli utenti di Data Workbench di tornare al lavoro
title: Preparazione alla rielaborazione o alla riconversione
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
exl-id: f3746edf-416e-45c2-896c-48a3c875318c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 4%

---

# Preparazione alla rielaborazione o alla riconversione{#preparing-for-reprocessing-or-retransformation}

Passaggi per garantire che la rielaborazione o la riconversione proceda senza problemi e si concluda in tempo per consentire agli utenti di Data Workbench di tornare al lavoro

1. Determina il tempo trascorso dell&#39;elaborazione o della trasformazione precedente controllando il profilo del set di dati [!DNL Processing Mode History] nell&#39;interfaccia [!DNL Detailed Status].

   1. Quando lavori nel tuo profilo di set di dati, apri l’interfaccia [!DNL Detailed Status] .
   1. Fai clic su **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]*** > **[!UICONTROL Processing Mode History]** per visualizzare i tempi trascorsi per l’elaborazione o la trasformazione precedenti.

      * Fast Input è il tempo totale necessario per l&#39;elaborazione dei log.
      * Fast Merge è il tempo totale necessario per la trasformazione.
      * La somma delle due volte (Fast Input + Fast Merge) è il tempo totale necessario per l&#39;elaborazione del set di dati.

      L’esempio seguente indica che l’elaborazione del registro ha richiesto circa 43 secondi, mentre la trasformazione ha richiesto meno di 2 minuti.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Per ulteriori informazioni sull&#39;interfaccia [!DNL Detailed Status], consulta la *Guida utente alla Data Workbench*.


1. Pianifica e pianifica la rielaborazione. Poiché gli utenti di Data Workbench non hanno accesso ai dati durante la fase di elaborazione del registro, assicurati di pianificare la rielaborazione in modo che avvenga durante un’ora appropriata, ad esempio nel corso del fine settimana.
1. Monitora l&#39;avanzamento della rielaborazione e della riconversione utilizzando i campi in [!DNL Processing Legend.] Per ulteriori informazioni su [!DNL Processing Legend], consulta la *Guida utente Data Workbench*.
