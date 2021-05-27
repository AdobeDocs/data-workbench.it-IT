---
description: Passaggi per rendere disponibile un nuovo livello del terreno da visualizzare sulla visualizzazione del globo.
title: Come rendere disponibile un nuovo livello immagine del terreno
uuid: aeeb4ab0-f55c-47b8-96e4-eafd4df4d68a
exl-id: 76374298-ed65-4fcf-b40b-be7c15784f40
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '180'
ht-degree: 7%

---

# Come rendere disponibile un nuovo livello immagine del terreno{#making-a-new-terrain-image-layer-available}

Passaggi per rendere disponibile un nuovo livello del terreno da visualizzare sulla visualizzazione del globo.

1. Nella cartella Profiles\*profile name*\Maps all&#39;interno della directory di installazione **[!UICONTROL Insight Server]**, posiziona il file di livello e i file di immagine di supporto.
1. Modificate il file [!DNL order.txt] nella cartella Profiles\*profile name*\Maps per rispecchiare l&#39;ordine in cui desiderate visualizzare i livelli. Per impostazione predefinita, i livelli vengono visualizzati in ordine lessicografico in base ai loro nomi.

   >[!NOTE]
   >
   >Durante la modifica del file [!DNL order.txt] , assicurati di non nascondere i livelli mappa che desideri mostrare.

   Per ulteriori informazioni sull&#39;utilizzo dei file [!DNL order.txt], vedere il capitolo Configuring Interface and Analysis Features (Configurazione delle funzionalità di interfaccia e analisi) della *Data Workbench User Guide*.

1. All’interno di Data Workbench, seleziona il profilo desiderato facendo clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e facendo clic su **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Fai clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e fai clic su **[!UICONTROL Work Online]**. Accanto a [!DNL Work Online] viene visualizzata una X.
1. Apri un’area di lavoro e, su una visualizzazione a globo, fai clic con il pulsante destro del mouse e seleziona il nuovo livello. Accanto al nome del livello viene visualizzata una X.
