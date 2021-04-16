---
description: È necessario aggiungere il campo x-Experts al file Log Processing.cfg, utilizzato per creare una dimensione estesa.
solution: Analytics,Analytics
title: Modifica del registro Processing.cfg
uuid: 9105b09b-e3d5-4922-a205-b459553a4bec
exl-id: 23c7873f-8ffd-422f-896b-d6c7e16aabbd
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 4%

---

# Modifica del registro Processing.cfg{#modifying-log-processing-cfg}

È necessario aggiungere il campo x-Experts al file Log Processing.cfg, utilizzato per creare una dimensione estesa.

Vedere [Modifica di Transformation.cfg](../../../home/c-undst-ctrld-exp/c-vw-rslts/t-mod-trfmtn.md#task-d61b02853a82492c9a76e3c5fe8a3fb6).

**Per modificare Log Processing.cfg**

1. In [!DNL Insight], apri l’ [!DNL Profile Manager] facendo clic con il pulsante destro del mouse in un’area di lavoro e facendo clic su **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** oppure aprendo l’area di lavoro Gestione profili nella scheda [!DNL Admin] .
1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Dataset]** per visualizzarne il contenuto.
1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Log Processing.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Viene visualizzata la finestra [!DNL Log Processing.cfg].
1. Fai clic su **[!UICONTROL Fields]** per visualizzarne il contenuto.
1. Fare clic con il pulsante destro del mouse sull&#39;ultimo campo dell&#39;elenco corrente e fare clic su **[!UICONTROL Add new]** > **[!UICONTROL Field]**.
1. Digita l’esperimento x nel campo appena creato, come illustrato nell’esempio seguente:

   ![Informazioni sul passaggio](assets/logprocessing.png)

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL Log Processing.cfg] nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>* per salvare le modifiche apportate localmente al profilo di lavoro.

   >[!NOTE]
   >
   >Il set di dati inizia a essere rielaborato immediatamente.

   Per ulteriori informazioni sull&#39;elaborazione del registro e sui campi, consulta la *Guida alla configurazione del set di dati*.
