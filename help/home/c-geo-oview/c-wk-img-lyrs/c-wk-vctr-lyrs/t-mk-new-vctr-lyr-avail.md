---
description: Passaggi per rendere disponibile un livello vettoriale da visualizzare sulla visualizzazione globale.
title: Come rendere disponibile un nuovo livello vettoriale
uuid: 7e88f183-b0aa-452d-b124-7cd970be9bb9
exl-id: aaa1a680-3733-43c3-9d14-5aaa5f4aad6e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 6%

---

# Come rendere disponibile un nuovo livello vettoriale{#making-a-new-vector-layer-available}

{{eol}}

Passaggi per rendere disponibile un livello vettoriale da visualizzare sulla visualizzazione globale.

1. Nella cartella Profiles\*profile name*\Maps all’interno della directory di installazione del server di Data Workbench, posiziona il file di livello e il [!DNL .vec] o [!DNL .tsv] file.
1. Modifica le [!DNL order.txt] nella cartella Profiles\*profile name*\Maps per rispecchiare l&#39;ordine di visualizzazione dei livelli. Per impostazione predefinita, i livelli vengono visualizzati in ordine lessicografico in base ai loro nomi.

   >[!NOTE]
   >
   >Durante la modifica del [!DNL order.txt] file, fare attenzione a non coprire i livelli mappa che si desidera mostrare.

   Per ulteriori informazioni sull&#39;utilizzo di [!DNL order.txt] file, consulta il capitolo Configuring Interface and Analysis Features (Configurazione di interfacce e funzionalità di analisi) *Guida utente di Data Workbench*.

1. All’interno di Data Workbench, seleziona il profilo desiderato facendo clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e facendo clic su **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Fai clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e fai clic su **[!UICONTROL Work Online]**. Accanto a [!DNL Work Online].
1. Apri un’area di lavoro e, su una visualizzazione a globo, fai clic con il pulsante destro del mouse e seleziona il nuovo livello. Accanto al nome del livello viene visualizzata una X.
