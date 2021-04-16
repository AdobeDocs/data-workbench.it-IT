---
description: Informazioni sull'utilizzo del server Data Workbench offline o online.
title: Utilizzo offline e online
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
exl-id: 1c9e0f4f-3172-40d3-b751-ebe6f9f57f8a
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 1%

---

# Utilizzo offline e online{#working-offline-and-online}

Informazioni sull&#39;utilizzo del server Data Workbench offline o online.

Data Workbench scarica automaticamente gli aggiornamenti al profilo e ai relativi dati dal server Data Workbench se disponi di una connessione di rete al [!DNL server] e lavori online. Se non hai specificato di lavorare online, Data Workbench carica il profilo e i relativi dati dalla cache del computer. In questo caso, visualizzi la versione del profilo e i relativi dati scaricati l’ultima volta che hai lavorato online con il profilo.

L&#39;utilizzo offline offre un vantaggio in termini di velocità di elaborazione perché si lavora dalla cache locale e si esegue una query dei dati sul proprio computer. Quando si lavora online, ogni query deve tornare al server Data Workbench, che richiede più tempo e ti costringe a competere con altri utenti online per le risorse del server. Se si dispone di una connessione di rete al server di Data Workbench, la modalità non in linea impedisce al server di Data Workbench di aggiornare i profili o i dati della Data Workbench, ma non impedisce il salvataggio degli elementi nel server di Data Workbench.

A causa della capacità di lavorare offline, il server Data Workbench è dimensionato in modo da gestire una certa quantità di input di traffico in tempo reale e una certa quantità di dati nel set di dati, insieme ad un certo numero di utenti Data Workbench, ma non deve essere ridimensionato per supportare il numero massimo di utenti simultanei (che in pratica non succede spesso). Poiché gli utenti di solito cercano tendenze e rapporti, esplorando i dati man mano che vai, nella maggior parte dei casi non è necessario conteggi esatti. Se è necessario eseguire una query e risolvere i conteggi esatti utilizzando i dati correnti, è possibile lavorare online e ottenerlo, ma la risoluzione delle query richiederà più tempo fino al 100%.

**Per lavorare online o offline**

Nella barra laterale, fai clic sull&#39;impostazione **[!UICONTROL Connection]** e fai clic su **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

Quando lavori online, Data Workbench si connette al server Data Workbench e sincronizza le informazioni sul computer con il profilo e le informazioni sul set di dati che risiedono sul server Data Workbench.

La configurazione predefinita per Data Workbench è quella di lavorare offline, ma come descritto nella sezione seguente, ogni utente può modificare il proprio file [!DNL Insight.cfg] per far funzionare online la propria istanza di Data Workbench per impostazione predefinita.

**Per lavorare online per impostazione predefinita**

1. Passa alla directory di installazione di Insight.
1. Apri il file [!DNL Insight.cfg] in un editor di testo.
1. Aggiungi la riga evidenziata al file come mostrato nell’esempio seguente:

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

La prossima volta che apri Data Workbench, si connette al server Data Workbench e funziona online per impostazione predefinita.
