---
description: Le visualizzazioni gerarchiche sono disponibili solo quando si utilizza l'applicazione Site o HBX.
solution: Analytics
title: Applicare viste gerarchiche
topic: Data workbench
uuid: 859a92af-4f7e-4bb5-9a98-917006894301
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Applicare viste gerarchiche{#apply-hierarchy-views}

Le visualizzazioni gerarchiche sono disponibili solo quando si utilizza l&#39;applicazione Site o HBX.

La visualizzazione gerarchica mostra le pagine in un sito Web organizzato gerarchicamente per nome file e ordinato in ordine alfabetico. Anche se utile per l&#39;analisi stessa, la vista gerarchica può essere utilizzata anche per impostare visualizzazioni avanzate come mappe di processo. Per ulteriori informazioni sulle mappe dei processi, consultate [Process Maps (Mappe](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-proc-maps.md#concept-880aee224404429785b733a4e80d275e)di processo).

>[!NOTE]
>
>Se il set di dati è stato configurato per l&#39;esecuzione su più server in un cluster, affinché questa funzionalità funzioni correttamente, l&#39;amministratore di sistema deve indicare quali funzioni del computer utilizzare per il server di normalizzazione centrale. Per i passaggi necessari, consultare il capitolo File di configurazione dell&#39;elaborazione del registro della Guida alla configurazione del *set di dati*.

![](assets/vis_Table_CompareHierarchy.png)

**Attivazione o disattivazione della visualizzazione gerarchica**

* Da qualsiasi visualizzazione di pagina o URI, fai clic con il pulsante destro del mouse su un elemento o sull’etichetta della dimensione della pagina e fai clic **[!UICONTROL Hierarchy View]**.

   ![](assets/mnu_Table_HierarchyView.png)

   Una X viene visualizzata accanto all&#39;opzione quando l&#39; [!DNL hierarchy view] attività è attiva.

   La gerarchia è organizzata in sezioni e pagine di siti Web utilizzando una struttura ad albero. Le sezioni (nodi) possono essere espanse o condensate utilizzando il simbolo + o - accanto al nome della sezione. Alle singole pagine non è associato un simbolo + o -.

   ![](assets/vis_Table_HierarchyView_Expanded.png)

## Mascheramento di elementi dimensione in una visualizzazione Gerarchia {#section-e477c469934846da8d807f92fc2f3ed1}

Per mascheramento si intende la selezione di un sottoinsieme di dati o di un sottoinsieme di elementi in una dimensione. Potete mascherare o nascondere gli elementi che non desiderate includere nell’analisi. Utilizzando le opzioni del [!DNL Mask] menu per le viste gerarchiche, potete selezionare la percentuale minima di una metrica che un elemento deve essere visualizzata nella visualizzazione.

**Mascheramento dei dati con l&#39;opzione di[!DNL Mask]menu**

1. Fare clic con il pulsante destro del mouse su un elemento o l&#39;etichetta della dimensione e quindi fare clic **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_HierarchyView_Masking.png)

1. In Altro, fai clic sulla percentuale appropriata, quindi fai clic sulla metrica da mascherare.

Ad esempio, se fate clic su 0,1% e quindi su Visualizzazioni di pagina, viene mascherato (nascosto) qualsiasi elemento con meno dello 0,1% del numero totale di visualizzazioni di pagine e viene visualizzato qualsiasi elemento con più dello 0,1% del numero totale di visualizzazioni di pagine. Se fate clic su 0%, vengono mascherati tutti gli elementi con un valore pari a 0 (zero) per la metrica selezionata.
