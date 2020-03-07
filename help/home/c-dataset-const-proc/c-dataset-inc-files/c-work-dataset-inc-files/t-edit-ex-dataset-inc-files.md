---
description: I passaggi per modificare i dataset esistenti includono i file.
solution: Analytics
title: Modifica dei set di dati esistenti Includi file
topic: Data workbench
uuid: fcce2e46-b4a8-4c53-83bb-32ab410eb89e
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Modifica dei set di dati esistenti Includi file{#editing-existing-dataset-include-files}

I passaggi per modificare i dataset esistenti includono i file.

Si apre un file di set di dati esistente con l&#39;operatore [!DNL Profile Manager] in workbench dati.

Per informazioni sull&#39;apertura e l&#39;utilizzo di [!DNL Profile Manager], vedere la Guida *utente di Workbench* dati.

1. Quando lavori nel profilo del set di dati, apri il set di dati [!DNL Profile Manager] e fai clic **[!UICONTROL Dataset]** per visualizzare il contenuto della directory.

   * Per aprire un [!DNL Log Processing Dataset Include] file, fate clic **[!UICONTROL Log Processing]** per visualizzare il contenuto della directory.

   * Per aprire un [!DNL Transformation Dataset Include] file, fate clic **[!UICONTROL Transformation]** per visualizzare il contenuto della directory.

1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al set di dati desiderato e scegliere **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata la finestra di configurazione.

   Potete anche aprire un file di inclusione di un set di dati da un [!DNL Transformation Dependency Maps]. Per informazioni su [!DNL Transformation Dependency Maps], vedere [Rielaborazione e](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md)Trasformazione.

1. Modificate i parametri nel file di configurazione come appropriato. Per una descrizione dei parametri, vedere [Log Processing Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab) or [Transformation Dataset Include Files](../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace) .

   Quando si modifica un set di dati includere file all&#39;interno di una finestra del workbench di dati, è possibile utilizzare i tasti di scelta rapida per funzioni di modifica di base, quali taglio (Ctrl+x ), copia (Ctrl+c), incolla (Ctrl+v), annullamento (Ctrl+z ), ripristino (Ctrl+Maiusc+Z ), selezione sezione (clic+trascinamento) e selezione di tutto (Ctrl+a ). Inoltre, potete utilizzare i collegamenti per copiare e incollare il testo da un file di configurazione ( [!DNL .cfg]) a un altro.

1. Per salvare le modifiche, fate clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fate clic su **[!UICONTROL Save]**.
1. Per rendere attive le modifiche apportate localmente, nella [!DNL Profile Manager]colonna fare clic con il pulsante destro del mouse sul segno di spunta del file, quindi fare clic su [!DNL User] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL profile name]***, dove il nome del profilo è il nome del profilo del set di dati o il profilo ereditato a cui appartiene il file del set di dati. La rielaborazione o la riconversione dei dati inizia dopo la sincronizzazione del profilo del dataset.

   >[!NOTE]
   >
   >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.

