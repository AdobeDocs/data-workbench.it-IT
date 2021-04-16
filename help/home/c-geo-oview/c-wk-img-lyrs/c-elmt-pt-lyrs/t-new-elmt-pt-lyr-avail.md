---
description: Passaggi per rendere disponibile un livello punto elemento da visualizzare sulla visualizzazione globale.
title: Come rendere disponibile un nuovo livello del punto elemento
uuid: 7880de63-d206-4c56-b8cf-75882d867ace
exl-id: 9001f6b6-5d25-48a0-9381-04f679e0ff4d
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 6%

---

# Come rendere disponibile un nuovo livello del punto elemento{#making-a-new-element-point-layer-available}

Passaggi per rendere disponibile un livello punto elemento da visualizzare sulla visualizzazione globale.

1. Nella cartella Profiles\*profile name*\Maps all’interno della directory di installazione del server di Data Workbench, posiziona il file di livello e il relativo file di ricerca.
1. Se hai definito una nuova dimensione per il livello del punto elemento e non hai ancora riformato il set di dati, trasforma ora il set di dati.
1. Modificate il file [!DNL order.txt] nella cartella Profiles\*profile name*\Maps per rispecchiare l&#39;ordine in cui desiderate visualizzare i livelli. Per impostazione predefinita, i livelli vengono visualizzati in ordine lessicografico in base ai loro nomi.

   >[!NOTE]
   >
   >Durante la modifica del file [!DNL order.txt] , assicurati di non nascondere i livelli mappa che desideri mostrare.

   Per ulteriori informazioni sull&#39;utilizzo dei file [!DNL order.txt], vedere il capitolo Configuring Interface and Analysis Features (Configurazione delle funzionalità di interfaccia e analisi) della *Data Workbench User Guide*.

1. All’interno di Data Workbench, seleziona il profilo desiderato facendo clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e facendo clic su **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Fai clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e fai clic su **[!UICONTROL Work Online]**. Accanto a [!DNL Work Online] viene visualizzata una X.
1. Apri un’area di lavoro e, su una visualizzazione a globo, fai clic con il pulsante destro del mouse e seleziona il nuovo livello. Accanto al nome del livello viene visualizzata una X.
