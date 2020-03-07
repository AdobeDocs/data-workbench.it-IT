---
description: Passaggi per garantire che la rielaborazione o la riconversione proceda senza problemi e finisca in tempo per consentire agli utenti del workbench dati di tornare al lavoro
solution: Analytics
title: Preparazione alla riconversione o alla riconversione
topic: Data workbench
uuid: 69a5878e-707a-4100-89ba-bae0b8a16c84
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Preparazione alla riconversione o alla riconversione{#preparing-for-reprocessing-or-retransformation}

Passaggi per garantire che la rielaborazione o la riconversione proceda senza problemi e finisca in tempo per consentire agli utenti del workbench dati di tornare al lavoro

1. Determinare il tempo trascorso dell&#39;elaborazione o trasformazione precedente controllando il profilo del set di dati [!DNL Processing Mode History] nell&#39; [!DNL Detailed Status] interfaccia.

   1. Quando lavori nel profilo del set di dati, apri l’ [!DNL Detailed Status] interfaccia.
   1. Fare clic **[!UICONTROL Processing Status]** > *&lt;**[!UICONTROL dataset profile name]**>* > **[!UICONTROL Processing Mode History]** per visualizzare i tempi trascorsi per l&#39;elaborazione o la trasformazione precedente.

      * Fast Input è il tempo totale necessario per l’elaborazione del registro.
      * Unione veloce è il tempo totale necessario per la trasformazione.
      * La somma delle due volte (Fast Input + Fast Merge) è il tempo totale necessario per l&#39;elaborazione del dataset.
      L’esempio seguente indica che l’elaborazione del registro ha richiesto circa 43 secondi, mentre la trasformazione ha richiesto meno di 2 minuti.

      ![](assets/vis_DetailedStatus_ProcessingModeHistory.png)

      Per ulteriori informazioni sull&#39; [!DNL Detailed Status] interfaccia, vedere la Guida *utente di Workbench* dati.


1. Pianificare e pianificare la rielaborazione. Poiché gli utenti del workbench dati non hanno accesso ai dati durante la fase di elaborazione del registro, assicurarsi di pianificare la rielaborazione in modo che si verifichi durante l&#39;ora appropriata, ad esempio durante il fine settimana.
1. Monitorare l&#39;avanzamento della rielaborazione e della riconversione utilizzando i campi nella sezione [!DNL Processing Legend.] Per ulteriori informazioni sull&#39; [!DNL Processing Legend]elaborazione, vedere la Guida *utente di Workbench* dati.
