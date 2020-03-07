---
description: Il server Insight (InsightServer64.exe) consente di definire dimensioni personalizzate dai dati dell'evento o dai dati di ricerca.
solution: Analytics
title: Informazioni sulle dimensioni estese
topic: Data workbench
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni sulle dimensioni estese{#about-extended-dimensions}

Il server Insight (InsightServer64.exe) consente di definire dimensioni personalizzate dai dati dell&#39;evento o dai dati di ricerca.

Eventuali dimensioni personalizzate definite vengono denominate dimensioni estese. Puoi utilizzarli per creare visualizzazioni, generare metriche estese o eseguire analisi per comprendere le operazioni e i problemi associati al canale aziendale. Potete definire diversi tipi di dimensioni estese nel [!DNL Transformation.cfg] file o nei [!DNL Transformation Dataset Include] file.

Una dimensione estesa rappresenta una relazione tra i valori dei campi di registro e una dimensione padre. Una dimensione padre può essere una qualsiasi dimensione numerabile definita dall&#39;utente. Vedere Dimensioni [](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8)conteggiabili. È possibile specificare l&#39;elemento padre quando si definisce la dimensione nel [!DNL Transformation.cfg] file o in un [!DNL Transformation Dataset Include] file. L&#39;elemento padre di una dimensione è uguale al suo livello. Ad esempio, se definite una dimensione con un elemento padre della sessione, tale dimensione è una dimensione a livello di sessione.

>[!NOTE]
>
>I valori dei campi di registro possono provenire dai valori intrinseci disponibili nei file di registro ( [!DNL .vsl]) o in altre origini dati evento o dai campi di registro estesi creati mediante l&#39;uso di trasformazioni.

Per aggiungere una dimensione estesa a una visualizzazione, puoi accedervi dall’elenco Estese all’interno del [!DNL Select Dimension] menu. Ad esempio, per aggiungere una dimensione estesa a una visualizzazione grafico, fai clic con il pulsante destro del mouse nell’area di lavoro e fai clic su **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Se si desidera organizzare l&#39;elenco delle dimensioni estese all&#39;interno dell&#39;interfaccia del workbench dati, è possibile spostare le dimensioni estese in sottocartelle create. Vedere il capitolo relativo alle interfacce amministrative della Guida *utente di Workbench* dati. In questo caso, anche i nomi delle sottocartelle vengono visualizzati nel menu, come in Aggiungi visualizzazione > Grafico > Esteso > &lt;nome ** sottocartella> > &lt;nome ** dimensione>.

Per visualizzare tutte le dimensioni definite per il profilo del set di dati e le dimensioni del buffer per ogni profilo, aprire l&#39; [!DNL Detailed Status] interfaccia in workbench dati e fare clic **[!UICONTROL Performance]**, quindi **[!UICONTROL Dimensions]** per espandere i nodi. La dimensione del buffer, che controlla i tempi di query, è espressa in MB. Per ulteriori informazioni sull&#39; [!DNL Detailed Status] interfaccia, consultate la guida all&#39;amministrazione e all&#39;installazione del server.
