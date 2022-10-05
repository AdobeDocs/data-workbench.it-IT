---
description: Insight Server (InsightServer64.exe) consente di definire dimensioni personalizzate a partire dai dati evento o dai dati di ricerca.
title: Informazioni sulle dimensioni estese
uuid: ae014a26-5286-4e36-9098-aaa463d9fe05
exl-id: f74aa85e-f880-4ab5-a8fb-128862aa808f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# Informazioni sulle dimensioni estese{#about-extended-dimensions}

{{eol}}

Insight Server (InsightServer64.exe) consente di definire dimensioni personalizzate a partire dai dati evento o dai dati di ricerca.

Tutte le dimensioni personalizzate definite vengono definite dimensioni estese. Puoi utilizzarli per creare visualizzazioni, generare metriche estese o eseguire analisi per comprendere le operazioni e i problemi associati al canale aziendale. È possibile definire diversi tipi di dimensioni estese nel [!DNL Transformation.cfg] file o in [!DNL Transformation Dataset Include] file.

Una dimensione estesa rappresenta una relazione tra i valori dei campi di registro e una dimensione padre. Una dimensione padre può essere qualsiasi dimensione conteggiata definita dall’utente. Vedi [Dimension conteggiabili](../../../home/c-dataset-const-proc/c-ex-dim/c-types-ex-dim/c-count-dim.md#concept-f28b633419494e7bbc510012dbfcc6f8). Quando definisci la dimensione nel [!DNL Transformation.cfg] file o [!DNL Transformation Dataset Include] file. L’elemento padre di una dimensione è lo stesso livello. Ad esempio, se definisci una dimensione con un elemento padre di Session, tale dimensione sarà a livello di sessione.

>[!NOTE]
>
>I valori del campo di log possono provenire dai valori intrinseci disponibili nel log ( [!DNL .vsl]) file o altre origini dati evento o da campi di registro estesi creati tramite l’utilizzo di trasformazioni .

Per aggiungere una dimensione estesa a una visualizzazione, puoi accedervi dall’elenco Esteso all’interno della [!DNL Select Dimension] menu. Ad esempio, per aggiungere una dimensione estesa a una visualizzazione grafico, fai clic con il pulsante destro del mouse nell’area di lavoro e fai clic su **[!UICONTROL Add Visualization]** > **[!UICONTROL Graph]** > **[!UICONTROL Extended]** > *&lt;**[!UICONTROL dimension name]**>*. Se desideri organizzare l’elenco delle dimensioni estese all’interno dell’interfaccia di Data Workbench, puoi spostare le dimensioni estese in sottocartelle create. Vedere il capitolo relativo alle interfacce amministrative *Guida utente di Data Workbench*. In questo modo, i nomi delle sottocartelle vengono visualizzati anche nel menu , come in Aggiungi visualizzazione > Grafico > Esteso > &lt;*nome della sottocartella*> &lt;*nome dimensione*>

Per visualizzare tutte le dimensioni definite per il profilo del set di dati e le dimensioni del buffer per ciascuna di esse, apri la [!DNL Detailed Status] interfaccia in data workbench e fai clic su **[!UICONTROL Performance]**, quindi **[!UICONTROL Dimensions]** per espandere i nodi. La dimensione del buffer, che controlla i tempi di query, è espressa in MB. Per ulteriori informazioni sulla [!DNL Detailed Status] , consulta la guida all’amministrazione e all’installazione del server .
