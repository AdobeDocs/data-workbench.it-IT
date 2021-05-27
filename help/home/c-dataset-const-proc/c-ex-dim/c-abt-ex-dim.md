---
description: Insight Server (InsightServer64.exe) consente di definire dimensioni personalizzate a partire dai dati evento o dai dati di ricerca.
title: Informazioni sulle dimensioni estese
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# Informazioni sulle dimensioni estese{#about-extended-dimensions}

Insight Server (InsightServer64.exe) consente di definire dimensioni personalizzate a partire dai dati evento o dai dati di ricerca.

Tutte le dimensioni personalizzate definite vengono definite dimensioni estese. Puoi utilizzarli per creare visualizzazioni, generare metriche estese o eseguire analisi per comprendere le operazioni e i problemi associati al canale aziendale. Puoi definire diversi tipi di dimensioni estese nel file [!DNL Transformation.cfg] o nei file [!DNL Transformation Dataset Include].

Una dimensione estesa rappresenta una relazione tra i valori dei campi di registro e una dimensione padre. Una dimensione padre può essere qualsiasi dimensione conteggiata definita dall’utente. Vedere [Dimension conteggiabili](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). È possibile specificare l&#39;elemento padre quando si definisce la dimensione nel file [!DNL Transformation.cfg] o in un file [!DNL Transformation Dataset Include]. L’elemento padre di una dimensione è lo stesso livello. Ad esempio, se definisci una dimensione con un elemento padre di Session, tale dimensione sarà a livello di sessione.

>[!NOTE]
>
>I valori dei campi di log possono provenire dai valori intrinseci disponibili nei file di log ( [!DNL .vsl]) o in altre origini dati evento o da campi di log estesi creati tramite l&#39;uso di trasformazioni.

Per aggiungere una dimensione estesa a una visualizzazione, puoi accedervi dall’elenco Esteso nel menu [!DNL Select Dimension] . Ad esempio, per aggiungere una dimensione estesa a una visualizzazione grafico, fai clic con il pulsante destro del mouse nell’area di lavoro e fai clic su **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Se desideri organizzare l’elenco delle dimensioni estese all’interno dell’interfaccia di Data Workbench, puoi spostare le dimensioni estese in sottocartelle create. Vedere il capitolo relativo alle interfacce amministrative della *Guida utente Data Workbench*. In questo caso, i nomi delle sottocartelle vengono visualizzati anche nel menu, come in Aggiungi visualizzazione > Grafico > Esteso > &lt;*nome della sottocartella*> > &lt;*nome dimensione*.

Per visualizzare tutte le dimensioni definite per il profilo di set di dati e le dimensioni del buffer per ciascuna di esse, apri l’interfaccia [!DNL Detailed Status] in Data Workbench e fai clic su **[!UICONTROL Performance]**, quindi **[!UICONTROL Dimensions]** per espandere i nodi. La dimensione del buffer, che controlla i tempi di query, è espressa in MB. Per ulteriori informazioni sull&#39;interfaccia [!DNL Detailed Status], consulta la guida all&#39;amministrazione e all&#39;installazione del server .
