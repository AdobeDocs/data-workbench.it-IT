---
description: Ora che è disponibile il campo x-Experts, è necessario creare una dimensione estesa per includere il campo x-Experts nel dataset, che consente di visualizzare i risultati in Insight.
solution: Analytics,Analytics
title: Modifica di Transformation.cfg
topic: Data workbench
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---


# Modifica di Transformation.cfg{#modifying-transformation-cfg}

Ora che è disponibile il campo x-Experts, è necessario creare una dimensione estesa per includere il campo x-Experts nel dataset, che consente di visualizzare i risultati in Insight.

A tale scopo, è necessario aggiungere una nuova dimensione al [!DNL Transformation.cfg] file.

Se intendete eseguire più esperimenti, dovete anche aggiungere una nuova trasformazione Dividi al [!DNL Transformation.cfg] file. Questa trasformazione Split separa i diversi nomi di esperimenti e gruppi in modo che le informazioni siano più facili da interpretare. Per evitare di ripetere l&#39;elaborazione dei dati se doveste aggiungere ulteriori esperimenti in una data successiva,  Adobe consiglia di aggiungere la trasformazione Spalato anche se al momento non state pianificando l&#39;esecuzione di più esperimenti.

La procedura seguente include la creazione della nuova trasformazione Split e della dimensione estesa. Se non si desidera aggiungere la trasformazione Dividi, è sufficiente saltare i passaggi da 5 a 7.

**Per modificare Transformation.cfg**

1. In [!DNL Insight], aprite l’area di lavoro [!DNL Profile Manager] facendo clic con il pulsante destro del mouse in un’area di lavoro e scegliendo **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** oppure aprendo l’area di lavoro Gestione profilo nella [!DNL Admin] scheda.
1. In [!DNL Profile Manager], fate clic **[!UICONTROL Dataset]** per visualizzarne il contenuto.
1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Transformation.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Viene [!DNL Transformation.cfg] visualizzata la finestra.
1. Fate clic **[!UICONTROL Transformation]** per visualizzarne il contenuto.
1. Fare clic con il pulsante destro del mouse **[!UICONTROL Transformations]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Completate la nuova divisione per la trasformazione della virgola come illustrato nell&#39;esempio seguente:

   ![Informazioni sul passaggio](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >È possibile immettere qualsiasi valore nel campo Nome.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL Extended Dimensions]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Completate la nuova dimensione come illustrato nell&#39;esempio seguente:

   ![Informazioni sul passaggio](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* È possibile immettere qualsiasi valore nel campo Nome.
   >* Se non hai incluso la trasformazione Split, devi digitare &quot;x-Experts&quot; nel [!DNL Input] campo.


1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.
1. Fare [!DNL Profile Manager]clic con il pulsante destro del mouse sul segno di spunta [!DNL Transformation.cfg] nella [!DNL User] colonna, quindi scegliere **[!UICONTROL Save to]** > **[!UICONTROL profile name]** per salvare le modifiche locali apportate al profilo di lavoro.

   >[!NOTE]
   >
   >Il set di dati inizia a trasformarsi immediatamente.

   Per ulteriori informazioni sulle [!DNL Transformation.cfg] dimensioni estese, consulta la Guida alla configurazione del *set di dati*.
