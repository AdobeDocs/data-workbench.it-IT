---
description: Passaggi per garantire che la rielaborazione o la riconversione proceda senza problemi e si concluda in tempo per consentire agli utenti di Data Workbench di tornare al lavoro
title: Preparazione alla rielaborazione o alla riconversione
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
exl-id: f3746edf-416e-45c2-896c-48a3c875318c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 4%

---

# Preparazione alla rielaborazione o alla riconversione{#preparing-for-reprocessing-or-retransformation}

{{eol}}

Passaggi per garantire che la rielaborazione o la riconversione proceda senza problemi e si concluda in tempo per consentire agli utenti di Data Workbench di tornare al lavoro

1. Determinare il tempo trascorso dell’elaborazione o della trasformazione precedente controllando il [!DNL Processing Mode History] in [!DNL Detailed Status] interfaccia.

   1. Quando lavori nel tuo profilo di set di dati, apri la [!DNL Detailed Status] interfaccia.
   1. Fai clic su **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]** per visualizzare i tempi trascorsi dell&#39;elaborazione o della trasformazione precedente.

      * Fast Input è il tempo totale necessario per l&#39;elaborazione dei log.
      * Fast Merge è il tempo totale necessario per la trasformazione.
      * La somma delle due volte (Fast Input + Fast Merge) è il tempo totale necessario per l&#39;elaborazione del set di dati.

      L’esempio seguente indica che l’elaborazione del registro ha richiesto circa 43 secondi, mentre la trasformazione ha richiesto meno di 2 minuti.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Per ulteriori informazioni sulla [!DNL Detailed Status] interfaccia, vedi *Guida utente di Data Workbench*.


1. Pianifica e pianifica la rielaborazione. Poiché gli utenti di Data Workbench non hanno accesso ai dati durante la fase di elaborazione del registro, assicurati di pianificare la rielaborazione in modo che avvenga durante un’ora appropriata, ad esempio nel corso del fine settimana.
1. Monitora l&#39;avanzamento della rielaborazione e della riconversione utilizzando i campi nella [!DNL Processing Legend.] Per ulteriori informazioni sulla [!DNL Processing Legend], vedi *Guida utente di Data Workbench*.
