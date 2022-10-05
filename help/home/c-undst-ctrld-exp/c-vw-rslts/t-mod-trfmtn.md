---
description: Ora che il campo x-Experts è disponibile, devi creare una dimensione estesa per includere il campo x-Experts nel set di dati, che ti consenta di visualizzare i risultati in Insight.
solution: Analytics
title: Modifica di Transformation.cfg
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# Modifica di Transformation.cfg{#modifying-transformation-cfg}

{{eol}}

Ora che il campo x-Experts è disponibile, devi creare una dimensione estesa per includere il campo x-Experts nel set di dati, che ti consenta di visualizzare i risultati in Insight.

A questo scopo, devi aggiungere una nuova dimensione al [!DNL Transformation.cfg] file.

Se si prevede di eseguire più esperimenti, è inoltre necessario aggiungere una nuova trasformazione Split alla [!DNL Transformation.cfg] file. Questa trasformazione Split separa i diversi nomi dell&#39;esperimento e del gruppo in modo che le informazioni siano più facili da interpretare. Per evitare di rielaborare i dati se è necessario aggiungere ulteriori esperimenti in una data successiva, l’Adobe consiglia di aggiungere la trasformazione Split anche se non si prevede attualmente l’esecuzione di più esperimenti.

La procedura seguente include la creazione sia della nuova trasformazione Split che della dimensione estesa. Se non desideri aggiungere la trasformazione Split, salta semplicemente i passaggi 5-7.

**Per modificare Transformation.cfg**

1. In [!DNL Insight], apri [!DNL Profile Manager] facendo clic con il pulsante destro del mouse all’interno di un’area di lavoro e facendo clic su **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** oppure aprendo l’area di lavoro Gestione profili in [!DNL Admin] scheda .
1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Dataset]** per visualizzarne il contenuto.
1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Transformation.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nel [!DNL User] colonna.
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La [!DNL Transformation.cfg] viene visualizzata la finestra .
1. Fai clic su **[!UICONTROL Transformation]** per visualizzarne il contenuto.
1. Fai clic con il pulsante destro del mouse **[!UICONTROL Transformations]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Completa la nuova divisione sulla trasformazione della virgola come mostrato nell’esempio seguente:

   ![Informazioni sul passaggio](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >È possibile immettere qualsiasi valore nel campo Nome.

1. Fai clic con il pulsante destro del mouse **[!UICONTROL Extended Dimensions]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Completa la nuova dimensione come mostrato nell’esempio seguente:

   ![Informazioni sul passaggio](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* È possibile immettere qualsiasi valore nel campo Nome.
   >* Se non hai incluso la trasformazione Split, devi digitare &quot;x-sperimentale&quot; nel [!DNL Input] campo .


1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta [!DNL Transformation.cfg] in [!DNL User] , quindi fai clic su **[!UICONTROL Save to]** > **[!UICONTROL profile name]** per salvare le modifiche apportate localmente al profilo di lavoro.

   >[!NOTE]
   >
   >Il set di dati inizia a trasformarsi immediatamente.

   Per ulteriori informazioni [!DNL Transformation.cfg] e le dimensioni estese, vedi *Guida alla configurazione del set di dati*.
