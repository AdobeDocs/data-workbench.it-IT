---
description: Ora che il campo x-Experts è disponibile, devi creare una dimensione estesa per includere il campo x-Experts nel set di dati, che ti consenta di visualizzare i risultati in Insight.
solution: Analytics,Analytics
title: Modifica di Transformation.cfg
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# Modifica di Transformation.cfg{#modifying-transformation-cfg}

Ora che il campo x-Experts è disponibile, devi creare una dimensione estesa per includere il campo x-Experts nel set di dati, che ti consenta di visualizzare i risultati in Insight.

A questo scopo, devi aggiungere una nuova dimensione al file [!DNL Transformation.cfg] .

Se si prevede di eseguire più esperimenti, è inoltre necessario aggiungere una nuova trasformazione Split al file [!DNL Transformation.cfg]. Questa trasformazione Split separa i diversi nomi dell&#39;esperimento e del gruppo in modo che le informazioni siano più facili da interpretare. Per evitare di rielaborare i dati se è necessario aggiungere ulteriori esperimenti in una data successiva, l’Adobe consiglia di aggiungere la trasformazione Split anche se non si prevede attualmente l’esecuzione di più esperimenti.

La procedura seguente include la creazione sia della nuova trasformazione Split che della dimensione estesa. Se non desideri aggiungere la trasformazione Split, salta semplicemente i passaggi 5-7.

**Per modificare Transformation.cfg**

1. In [!DNL Insight], apri l’ [!DNL Profile Manager] facendo clic con il pulsante destro del mouse in un’area di lavoro e facendo clic su **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** oppure aprendo l’area di lavoro Gestione profili nella scheda [!DNL Admin] .
1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Dataset]** per visualizzarne il contenuto.
1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Transformation.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Viene visualizzata la finestra [!DNL Transformation.cfg].
1. Fai clic su **[!UICONTROL Transformation]** per visualizzarne il contenuto.
1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Transformations]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Completa la nuova divisione sulla trasformazione della virgola come mostrato nell’esempio seguente:

   ![Informazioni sul passaggio](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >È possibile immettere qualsiasi valore nel campo Nome.

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Extended Dimensions]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Completa la nuova dimensione come mostrato nell’esempio seguente:

   ![Informazioni sul passaggio](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* È possibile immettere qualsiasi valore nel campo Nome.
   >* Se non hai incluso la trasformazione Split, devi digitare &quot;x-sperimentale&quot; nel campo [!DNL Input].


1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL Transformation.cfg] nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > **[!UICONTROL profile name]** per salvare le modifiche apportate localmente al profilo di lavoro.

   >[!NOTE]
   >
   >Il set di dati inizia a trasformarsi immediatamente.

   Per ulteriori informazioni su [!DNL Transformation.cfg] e dimensioni estese, consulta la *Guida alla configurazione del set di dati*.
