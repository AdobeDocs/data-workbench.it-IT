---
description: Per creare una dimensione di segmento, inizia effettuando una selezione all’interno di un’area di lavoro e quindi aggiungendo il segmento a una visualizzazione.
title: Creazione di dimensioni di segmento
uuid: 68dcf3bf-fbc9-4924-a0dd-d112cf366131
exl-id: 393d544e-e821-49e3-8cfb-5a3496aa7380
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 3%

---

# Creazione di dimensioni di segmento{#create-a-segment-dimensions}

Per creare una dimensione di segmento, inizia effettuando una selezione all’interno di un’area di lavoro e quindi aggiungendo il segmento a una visualizzazione.

**Creazione di una dimensione di segmento**

1. Aggiungi una visualizzazione segmento all’area di lavoro. Ad esempio:

   ![](assets/vis_Segment.png)

1. Aggiungi all’area di lavoro visualizzazioni da utilizzare per definire il segmento, quindi effettua le selezioni desiderate per definire il segmento.
1. Nella visualizzazione dei segmenti, fai clic con il pulsante destro del mouse sull’etichetta del segmento dopo il quale vuoi aggiungere il nuovo segmento e fai clic su **[!UICONTROL Add Segment]**.

   >[!NOTE]
   >
   >Per creare un nuovo primo segmento, fai clic con il pulsante destro del mouse sull’etichetta **[!UICONTROL Segments]** e fai clic su **[!UICONTROL Add Segment]**.

   ![](assets/vis_SegmentNew.png)

   Nella visualizzazione viene visualizzato un nuovo segmento (denominato Nuovo segmento). Il segmento Altro rappresenta tutti i dati non inclusi nei segmenti definiti: si tratta in modo efficace della differenza tra i dati del set di dati e i dati del segmento.

1. Fai clic con il pulsante destro del mouse sul segmento appena creato e fai clic su **[!UICONTROL Rename Segment]**.
1. Inserisci un nome descrittivo per il nuovo segmento nel campo name.

   >[!NOTE]
   >
   >Se un valore di metrica, come un particolare visitatore in [!DNL Site], soddisfa i criteri di più segmenti, il valore di metrica viene incluso solo nel primo segmento elencato a cui corrisponde.

**Salvataggio della dimensione del segmento**

1. Fai clic con il pulsante destro del mouse sull’etichetta Segmenti e fai clic su **[!UICONTROL Save Dimension]**. Viene visualizzata la finestra [!DNL Save Dimension As]. Il percorso di salvataggio predefinito è la cartella User\*profile name*\Dimension.
1. Nel campo [!DNL File name] , digita un nome descrittivo per i segmenti che stai salvando come dimensione e fai clic su **[!UICONTROL Save]**.

Puoi accedere alla dimensione del segmento ogni volta che lavori con una visualizzazione. Puoi anche esportare i dati associati agli elementi della dimensione salvata utilizzando la funzione di esportazione del segmento.

Per ulteriori informazioni sulla funzione di esportazione dei segmenti e istruzioni per configurarla in base alle tue esigenze, consulta [Configurazione dei segmenti per l’esportazione](../../../../home/c-get-started/c-exp-data-seg-exp/t-config-sgts-expt.md#task-8857f221fa66463990ec9b60db6db372).
