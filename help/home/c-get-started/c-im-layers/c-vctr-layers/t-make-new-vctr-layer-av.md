---
description: Passaggi per rendere disponibile qualsiasi livello vettoriale da visualizzare sulla visualizzazione globale.
title: Rendere disponibile un nuovo livello vettoriale
uuid: 7bfbae0d-e5db-4aa2-8a8b-15b4980aadb5
exl-id: 6c084bac-1a6d-452a-bf07-e502d0f2145a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 7%

---

# Rendere disponibile un nuovo livello vettoriale{#make-a-new-vector-layer-available}

{{eol}}

Passaggi per rendere disponibile qualsiasi livello vettoriale da visualizzare sulla visualizzazione globale.

1. Nella cartella Profiles\*profile name*\Maps all&#39;interno della directory di installazione del server Data Workbench, posizionare il file di livello e il [!DNL .vec] o [!DNL .tsv] file.
1. Modifica le [!DNL order.txt] nella cartella Profiles\*profile name*\Maps per rispecchiare l&#39;ordine di visualizzazione dei livelli. Per impostazione predefinita, i livelli vengono visualizzati in ordine lessicografico in base ai loro nomi.

   >[!NOTE]
   >
   >Durante la modifica del [!DNL order.txt] file, fare attenzione a non coprire i livelli mappa che si desidera mostrare.

   Per ulteriori informazioni sull&#39;utilizzo di [!DNL order.txt] file, vedi [Personalizzazione dei menu tramite i file Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).

1. In Insight, seleziona il profilo desiderato facendo clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e facendo clic su **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Fai clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e fai clic su **[!UICONTROL Work Online]**. Accanto a Work Online viene visualizzata una X.
1. Apri un’area di lavoro e, su una visualizzazione a globo, fai clic con il pulsante destro del mouse e seleziona il nuovo livello. Accanto al nome del livello viene visualizzata una X.
