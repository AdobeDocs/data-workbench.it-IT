---
description: Passaggi per rendere disponibile qualsiasi livello vettoriale da visualizzare sulla visualizzazione globale.
solution: Analytics
title: Rendere disponibile un nuovo livello vettoriale
topic: Data workbench
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Rendere disponibile un nuovo livello vettoriale{#make-a-new-vector-layer-available}

Passaggi per rendere disponibile qualsiasi livello vettoriale da visualizzare sulla visualizzazione globale.

1. Nella cartella Profili\*nome profilo*\Mappe all&#39;interno della directory di installazione del server Workbench dati, posizionare il file di livello e i [!DNL .vec] o [!DNL .tsv] i file.
1. Modificate il [!DNL order.txt] file nella cartella Profili\*nome profilo*\Maps per riflettere l&#39;ordine in cui desiderate visualizzare i livelli. Per impostazione predefinita, i livelli vengono visualizzati in ordine lessicografico in base ai relativi nomi.

   >[!NOTE]
   >
   >Quando modificate il [!DNL order.txt] file, prestate attenzione a non nascondere i livelli mappa che desiderate mostrare.

   Per ulteriori informazioni sull&#39;uso [!DNL order.txt] dei file, vedere [Personalizzazione dei menu mediante i file](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.

1. In Insight, selezionate il profilo desiderato facendo clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e scegliendo **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Fate clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e fate clic **[!UICONTROL Work Online]**. Accanto a Work Online viene visualizzata una X.
1. Aprite un’area di lavoro e, in una visualizzazione globale, fate clic con il pulsante destro del mouse e selezionate il nuovo livello. Accanto al nome del livello viene visualizzata una X.
