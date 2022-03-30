---
description: È necessario aggiungere il campo x-Experts al file Log Processing.cfg, utilizzato per creare una dimensione estesa.
solution: Analytics
title: Modifica del registro Processing.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# Modifica del registro Processing.cfg{#modifying-log-processing-cfg}

È necessario aggiungere il campo x-Experts al file Log Processing.cfg, utilizzato per creare una dimensione estesa.

Vedi [Modifica di Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Per modificare Log Processing.cfg**

1. In [!DNL Insight], apri [!DNL Profile Manager] facendo clic con il pulsante destro del mouse all’interno di un’area di lavoro e facendo clic su **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** oppure aprendo l’area di lavoro Gestione profili in [!DNL Admin] scheda .
1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Dataset]** per visualizzarne il contenuto.
1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Log Processing.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nel [!DNL User] colonna.
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La [!DNL Log Processing.cfg] viene visualizzata la finestra .
1. Fai clic su **[!UICONTROL Fields]** per visualizzarne il contenuto.
1. Fare clic con il pulsante destro del mouse sull’ultimo campo dell’elenco corrente e fare clic su **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Digita l’esperimento x nel campo appena creato, come illustrato nell’esempio seguente:

   ![Informazioni sul passaggio](assets/logprocessing.png)

1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta [!DNL Log Processing.cfg] in [!DNL User] , quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* per salvare le modifiche apportate localmente al profilo di lavoro.

   >[!NOTE]
   >
   >Il set di dati inizia a essere rielaborato immediatamente.

   Per ulteriori informazioni sull’elaborazione dei registri e sui campi, consulta la sezione *Guida alla configurazione del set di dati*.
