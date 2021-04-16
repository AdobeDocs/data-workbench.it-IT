---
description: I passaggi per modificare il set di dati esistente includono file.
title: Modifica di Dataset Include Files (File inclusi nel set di dati) esistente
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
exl-id: f4095871-d004-4e10-af18-bf6c1e47493d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---

# Modifica di Dataset Include Files (File inclusi nel set di dati) esistente{#editing-existing-dataset-include-files}

I passaggi per modificare il set di dati esistente includono file.

Apri un file di inclusione di un set di dati esistente utilizzando [!DNL Profile Manager] in Data Workbench.

Per informazioni sull&#39;apertura e l&#39;utilizzo di [!DNL Profile Manager], vedere la *Guida utente alla Data Workbench*.

1. Quando lavori nel tuo profilo di set di dati, apri il [!DNL Profile Manager] e fai clic su **[!UICONTROL Dataset]** per visualizzare il contenuto della directory.

   * Per aprire un file [!DNL Log Processing Dataset Include], fai clic su **[!UICONTROL Log Processing]** per visualizzare il contenuto della directory.

   * Per aprire un file [!DNL Transformation Dataset Include], fai clic su **[!UICONTROL Transformation]** per visualizzare il contenuto della directory.

1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto al file di inclusione del set di dati desiderato e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata la finestra di configurazione.

   Puoi anche aprire un file di inclusione di un set di dati da un [!DNL Transformation Dependency Maps]. Per informazioni su [!DNL Transformation Dependency Maps], vedere [Rielaborazione e ritrasformazione](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).

1. Modifica i parametri nel file di configurazione come appropriato. Per le descrizioni dei parametri, consulta [Elaborazione registro Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) o [Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) (File inclusi nel set di dati di trasformazione).

   Quando modifichi un file di inclusione di un set di dati all’interno di una finestra di Data Workbench, puoi utilizzare i tasti di scelta rapida per le funzioni di modifica di base, tra cui Taglia (Ctrl+x ), Copia (Ctrl+c) , Incolla (Ctrl+v ), Annulla (Ctrl+Z ), Ripristina (Ctrl+Maiusc+Z ), seleziona la sezione (Clic+trascinamento) e seleziona tutto (Ctrl+a ). Inoltre, è possibile utilizzare le scelte rapide per copiare e incollare il testo da un file di configurazione ( [!DNL .cfg]) a un altro.

1. Per salvare le modifiche, fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
1. Per rendere effettive le modifiche apportate localmente, fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, dove nome profilo è il nome del profilo del set di dati o del profilo ereditato a cui appartiene il file del set di dati include. [!DNL Profile Manager] La rielaborazione o la riconversione dei dati inizia dopo la sincronizzazione del profilo del set di dati.

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.
