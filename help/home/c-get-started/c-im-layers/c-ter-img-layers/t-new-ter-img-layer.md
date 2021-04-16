---
description: Passaggi per rendere disponibile qualsiasi livello del terreno da visualizzare sulla visualizzazione del globo.
title: Rendere disponibile un nuovo livello di immagine del terreno
uuid: 8fb98a3e-6335-4922-a1e6-35c92b19e2ec
exl-id: bf0e6b37-4c8a-4d50-8bc9-eb70ca1cbb23
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 7%

---

# Rendere disponibile un nuovo livello di immagine del terreno{#make-a-new-terrain-image-layer-available}

Passaggi per rendere disponibile qualsiasi livello del terreno da visualizzare sulla visualizzazione del globo.

1. Nella cartella Profiles\*profile name*\Maps all&#39;interno della directory di installazione del server Data Workbench, posizionare il file di livello e i file di immagine di supporto.
1. Modificate il file [!DNL order.txt] nella cartella Profiles\*profile name*\Maps per rispecchiare l&#39;ordine in cui desiderate visualizzare i livelli. Per impostazione predefinita, i livelli vengono visualizzati in ordine lessicografico in base ai loro nomi.

   >[!NOTE]
   >
   >Durante la modifica del file [!DNL order.txt] , assicurati di non nascondere i livelli mappa che desideri mostrare.

   Per ulteriori informazioni sull&#39;utilizzo dei file [!DNL order.txt], vedere il capitolo Configuring Interface and Analysis Features (Configurazione delle funzionalità di interfaccia e analisi) della *Data Workbench User Guide*.

1. In Data Workbench, seleziona il profilo desiderato facendo clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e facendo clic su **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]***.
1. Fai clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e fai clic su **[!UICONTROL Work Online]**. Accanto a Work Online viene visualizzata una X.
1. Apri un’area di lavoro e, su una visualizzazione a globo, fai clic con il pulsante destro del mouse e seleziona il nuovo livello. Accanto al nome del livello viene visualizzata una X.
