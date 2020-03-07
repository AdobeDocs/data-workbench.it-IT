---
description: Passaggi per rendere disponibile un qualsiasi livello punto elemento da visualizzare sulla visualizzazione globale.
solution: Analytics
title: Rendere disponibile un nuovo livello punto elemento
topic: Data workbench
uuid: 5f4bad2f-e98d-4224-bba8-285ad5e23da9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Rendere disponibile un nuovo livello punto elemento{#make-a-new-element-point-layer-available}

Passaggi per rendere disponibile un qualsiasi livello punto elemento da visualizzare sulla visualizzazione globale.

1. Nella cartella Profili\*nome profilo*\Mappe all&#39;interno della directory di installazione del server Workbench dati, posizionare il file di livello e il relativo file di ricerca.
1. Se hai definito una nuova dimensione per il livello del punto elemento e non hai ancora ritrasformato il set di dati, trasforma ora il set di dati.
1. Modificate il [!DNL order.txt] file nella cartella Profili\*nome profilo*\Maps per riflettere l&#39;ordine in cui desiderate visualizzare i livelli. Per impostazione predefinita, i livelli vengono visualizzati in ordine lessicografico in base ai relativi nomi.

   >[!NOTE]
   >
   >Quando modificate il [!DNL order.txt] file, prestate attenzione a non nascondere i livelli mappa che desiderate mostrare.

   Per ulteriori informazioni sull&#39;utilizzo dei [!DNL order.txt] file, vedere il capitolo Configurazione delle funzioni di interfaccia e analisi della Guida utente di Workbench *dati*.

1. In Workbench dati, selezionare il profilo desiderato facendo clic con il pulsante destro del mouse sulla barra del titolo dell&#39;area di lavoro e scegliendo **[!UICONTROL Switch Profile]** > *&lt;**[!UICONTROL profile name]**>*.
1. Fate clic con il pulsante destro del mouse sulla barra del titolo dell’area di lavoro e fate clic **[!UICONTROL Work Online]**. Accanto a Work Online viene visualizzata una X.
1. Aprite un’area di lavoro e, in una visualizzazione globale, fate clic con il pulsante destro del mouse e selezionate il nuovo livello. Accanto al nome del livello viene visualizzata una X.
