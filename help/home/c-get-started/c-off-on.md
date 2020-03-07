---
description: Informazioni sull'utilizzo del server Workbench dati offline o online.
solution: Analytics
title: Utilizzo offline e online
topic: Data workbench
uuid: 613699d4-6d06-4c3c-b0aa-620933ae4d67
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Utilizzo offline e online{#working-offline-and-online}

Informazioni sull&#39;utilizzo del server Workbench dati offline o online.

Workbench dati scarica automaticamente gli aggiornamenti al profilo e ai relativi dati dal server Workbench dati se si dispone di una connessione di rete a [!DNL server] e si lavora online. Se non si è specificato di lavorare online, Workbench dati carica il profilo e i relativi dati dalla cache del computer. In questo caso, state visualizzando la versione del profilo e i relativi dati che sono stati scaricati l&#39;ultima volta che avete lavorato online con il profilo.

Lavorare offline offre un vantaggio in termini di velocità di elaborazione perché si lavora dalla cache locale e si esegue una query sui dati sul computer. Quando si lavora online, ogni query deve tornare al server Workbench dati, che richiede più tempo e obbliga a competere con altri utenti online per le risorse del server. Se si dispone di una connessione di rete al server Workbench dati, lavorare offline impedisce al server Workbench dati di aggiornare i profili o i dati nel workbench dati, ma non impedisce di salvare gli elementi nel server Workbench dati.

A causa della capacità di lavorare offline, il server Workbench dati è dimensionato in modo da gestire una certa quantità di input di traffico in tempo reale e una certa quantità di dati nel dataset, insieme ad alcuni utenti di Workbench dati, ma non deve essere ridimensionato per supportare il numero massimo di utenti simultanei (che in pratica non si verifica spesso). Poiché gli utenti in genere cercano tendenze e rapporti, esplorando i dati man mano che si va, nella maggior parte dei casi non è necessario un conteggio esatto. Se è necessario eseguire una query e risolvere i conteggi esatti utilizzando i dati correnti, è possibile lavorare online e ottenere questo risultato, ma la risoluzione delle query richiederà più tempo fino al 100%.

**Per lavorare online o offline**

Nella barra laterale, fate clic sull’ **[!UICONTROL Connection]** impostazione e fate clic su **[!UICONTROL Work Online]**.

![](assets/sidebar_work_online.png)

Quando si lavora online, Workbench dati si connette al server Workbench dati e sincronizza le informazioni sul computer con il profilo e le relative informazioni del dataset presenti sul server Workbench dati.

La configurazione predefinita di Workbench dati prevede la modalità non in linea, ma come descritto nella sezione seguente, ogni utente può modificare il proprio [!DNL Insight.cfg] file per rendere la propria istanza di Workbench dati online per impostazione predefinita.

**Per lavorare online per impostazione predefinita**

1. Andate alla directory di installazione di Insight.
1. Aprite il [!DNL Insight.cfg] file in un editor di testo.
1. Aggiungete la riga evidenziata al file come illustrato nell&#39;esempio seguente:

```
Update Software = bool: true
Default to Online = bool: true
Color Set = int: 0
```

La prossima volta che si apre Workbench dati, si connette al server Workbench dati e funziona online per impostazione predefinita.
