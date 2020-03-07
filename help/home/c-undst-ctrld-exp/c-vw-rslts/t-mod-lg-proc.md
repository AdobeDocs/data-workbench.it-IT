---
description: È necessario aggiungere il campo x-esperimento al file Log Processing.cfg, utilizzato per creare una dimensione estesa.
solution: Insight,Analytics
title: Modifica di Log Processing.cfg
topic: Data workbench
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modifica di Log Processing.cfg{#modifying-log-processing-cfg}

È necessario aggiungere il campo x-esperimento al file Log Processing.cfg, utilizzato per creare una dimensione estesa.

Vedere [Modifica di Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Per modificare Log Processing.cfg**

1. In [!DNL Insight], aprite l’area di lavoro [!DNL Profile Manager] facendo clic con il pulsante destro del mouse in un’area di lavoro e scegliendo **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** oppure aprendo l’area di lavoro Gestione profilo nella [!DNL Admin] scheda.
1. In [!DNL Profile Manager], fate clic **[!UICONTROL Dataset]** per visualizzarne il contenuto.
1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Log Processing.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Viene [!DNL Log Processing.cfg] visualizzata la finestra.
1. Fate clic **[!UICONTROL Fields]** per visualizzarne il contenuto.
1. Fare clic con il pulsante destro del mouse sull&#39;ultimo campo dell&#39;elenco corrente e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Digitate x-Experts nel campo appena creato, come illustrato nell&#39;esempio seguente:

   ![Informazioni sul passaggio](assets/logprocessing.png)

1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.
1. Fare [!DNL Profile Manager]clic con il pulsante destro del mouse sul segno di spunta [!DNL Log Processing.cfg] nella [!DNL User] colonna, quindi scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* per salvare le modifiche locali apportate al profilo di lavoro.

   >[!NOTE]
   >
   >Il set di dati inizia immediatamente la rielaborazione.

   Per ulteriori informazioni sull&#39;elaborazione dei registri e sui campi, vedere la Guida alla configurazione dei *set di dati*.

