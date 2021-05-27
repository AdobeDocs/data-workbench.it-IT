---
description: Passaggi per rendere disponibile qualsiasi livello di punto elemento da visualizzare sulla visualizzazione globale.
title: Rendere disponibile un nuovo livello di punto elemento
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
exl-id: 12797335-0788-4103-a581-41bc3bb3dcc9
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 6%

---

# Rendere disponibile un nuovo livello di punto elemento{#make-a-new-element-point-layer-available}

Passaggi per rendere disponibile qualsiasi livello di punto elemento da visualizzare sulla visualizzazione globale.

1. Nella cartella Profiles\*profile name*\Maps all&#39;interno della directory di installazione del server Data Workbench, posizionare il file di livello e il relativo file di ricerca.
1. Se hai definito una nuova dimensione per il livello del punto elemento e non hai ancora riformato il set di dati, trasforma ora il set di dati.
1. Modificate il file [!DNL order.txt] nella cartella Profiles\*profile name*\Maps per rispecchiare l&#39;ordine in cui desiderate visualizzare i livelli. Per impostazione predefinita, i livelli vengono visualizzati in ordine lessicografico in base ai loro nomi.

   >[!NOTE]
   >
   >Durante la modifica del file [!DNL order.txt] , assicurati di non nascondere i livelli mappa che desideri mostrare.

   Per ulteriori informazioni sull&#39;utilizzo dei file [!DNL order.txt], vedere il capitolo Configuring Interface and Analysis Features (Configurazione delle funzionalità di interfaccia e analisi) della *Data Workbench User Guide*.

1. In Data Workbench, seleziona il profilo desiderato facendo clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e facendo clic su **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]***.
1. Fai clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e fai clic su **[!UICONTROL Work Online]**. Accanto a Work Online viene visualizzata una X.
1. Apri un’area di lavoro e, su una visualizzazione a globo, fai clic con il pulsante destro del mouse e seleziona il nuovo livello. Accanto al nome del livello viene visualizzata una X.
