---
description: Passaggi per rendere disponibile un livello vettoriale da visualizzare sulla visualizzazione globale.
solution: Analytics
title: Come rendere disponibile un nuovo livello vettoriale
topic: Data workbench
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Come rendere disponibile un nuovo livello vettoriale{#making-a-new-vector-layer-available}

Passaggi per rendere disponibile un livello vettoriale da visualizzare sulla visualizzazione globale.

1. Nella cartella Profili\*nome profilo*\Mappe all&#39;interno della directory di installazione del server workbench dati, inserire il file livello e i [!DNL .vec] o [!DNL .tsv] i file.
1. Modificate il [!DNL order.txt] file nella cartella Profili\*nome profilo*\Maps per riflettere l&#39;ordine in cui desiderate visualizzare i livelli. Per impostazione predefinita, i livelli vengono visualizzati in ordine lessicografico in base ai relativi nomi.

   >[!NOTE]
   >
   >Quando modificate il [!DNL order.txt] file, prestate attenzione a non nascondere i livelli mappa che desiderate mostrare.

   Per ulteriori informazioni sull&#39;utilizzo dei [!DNL order.txt] file, vedere il capitolo Configurazione delle funzioni di interfaccia e analisi della Guida utente di Workbench *dati*.

1. Nel workbench dati, selezionare il profilo desiderato facendo clic con il pulsante destro del mouse sulla barra del titolo dell&#39;area di lavoro e scegliendo **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Fate clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e fate clic **[!UICONTROL Work Online]**. Accanto a [!DNL Work Online].
1. Aprite un’area di lavoro e, in una visualizzazione globale, fate clic con il pulsante destro del mouse e selezionate il nuovo livello. Accanto al nome del livello viene visualizzata una X.
