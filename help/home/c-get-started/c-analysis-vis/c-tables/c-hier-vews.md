---
description: Le visualizzazioni gerarchiche sono disponibili solo quando si utilizza l'applicazione Site o HBX.
title: Applicare viste gerarchiche
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
exl-id: 27a69404-40d3-44ab-bf5c-b2a5d8d836c2
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Applicare viste gerarchiche{#apply-hierarchy-views}

Le visualizzazioni gerarchiche sono disponibili solo quando si utilizza l&#39;applicazione Site o HBX.

Nella visualizzazione gerarchica vengono visualizzate le pagine di un sito Web organizzato gerarchicamente in base al nome del file e in ordine alfabetico. Sebbene utile per l’analisi stessa, la vista gerarchica può anche essere utilizzata per impostare visualizzazioni avanzate come mappe del processo. Per ulteriori informazioni sulle mappe del processo, consulta [Mappe del processo](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e).

>[!NOTE]
>
>Se il set di dati è stato configurato per l’esecuzione su più server in un cluster, affinché questa funzione funzioni correttamente, l’amministratore di sistema deve indicare quale computer funziona come server di normalizzazione centrale. Per i passaggi necessari, vedere il capitolo File di configurazione dell&#39;elaborazione del registro della *Guida alla configurazione del set di dati*.

![](assets/vis_Table_CompareHierarchy.png)

**Per abilitare o disabilitare la visualizzazione gerarchica**

* Da qualsiasi visualizzazione di pagina o URI, fai clic con il pulsante destro del mouse su un elemento o sull’etichetta della dimensione di pagina e fai clic su **[!UICONTROL Hierarchy View]**.

   ![](assets/mnu_Table_HierarchyView.png)

   Una X viene visualizzata accanto all&#39;opzione quando [!DNL hierarchy view] è attivo.

   La gerarchia è organizzata in sezioni e pagine del sito web utilizzando una struttura ad albero. Le sezioni (nodi) possono essere espanse o condensate utilizzando il simbolo + o - accanto al nome della sezione. Le singole pagine non dispongono di un simbolo + o - accanto a esse.

   ![](assets/vis_Table_HierarchyView_Expanded.png)

## Mascheramento degli elementi di Dimension in una visualizzazione gerarchica {#section-e477c469934846da8d807f92fc2f3ed1}

La mascheratura si riferisce alla selezione di un sottoinsieme di dati o di un sottoinsieme di elementi in una dimensione. mascherate o nascondete gli elementi che non desiderate includere nell’analisi. Utilizzando le opzioni del menu [!DNL Mask] per le viste gerarchiche, seleziona la percentuale minima di una metrica che un elemento deve visualizzare nella visualizzazione.

**Mascheramento dei dati tramite l’opzione  [!DNL Mask] menu**

1. Fai clic con il pulsante destro del mouse su un elemento o sull’etichetta della dimensione e fai clic su **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. In Più di, fai clic sulla percentuale appropriata, quindi fai clic sulla metrica da mascherare.

Ad esempio, se fai clic su 0,1% e poi su Visualizzazioni pagina, stai mascherando (nascondendo) qualsiasi elemento con meno dello 0,1% del numero totale di visualizzazioni di pagine e visualizzando qualsiasi elemento con più dello 0,1% del numero totale di visualizzazioni di pagine. Se fai clic su 0%, maschererai tutti gli elementi con un valore pari a 0 (zero) per la metrica selezionata.
