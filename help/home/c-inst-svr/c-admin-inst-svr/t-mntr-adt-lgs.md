---
description: I file di registro di controllo tengono traccia di tutte le connessioni e le disconnessioni tentate da Insight Server, ciascuna delle quali è registrata nei file <YYYYMMDD>-access.txt che si trovano per impostazione predefinita nella cartella Audit all'interno della directory di installazione di Insight Server.
solution: Insight
title: Monitoraggio dei registri di controllo
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Monitoraggio dei registri di controllo{#monitoring-audit-logs}

I file di registro di controllo tengono traccia di tutte le connessioni tentate e le disconnessioni da Insight Server, ciascuna delle quali è registrata nei `<YYYYMMDD>-access.txt` file che si trovano per impostazione predefinita nella cartella di controllo all&#39;interno della directory di installazione di Insight Server.

**Frequenza consigliata:** Giornaliero o in base alle esigenze per la risoluzione dei problemi

I registri di controllo possono essere molto utili per risolvere i problemi di connessione a [!DNL Insight Server]. È possibile monitorare questi registri utilizzando lo strumento di gestione automatizzata o visualizzando direttamente i [!DNL access.txt] file.

**Per visualizzare i file access.txt tramite il pannello[!DNL Server Files Manager]**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.
1. Fare clic con il pulsante destro del mouse sull&#39;icona di un elemento attivo [!DNL Insight Server] e fare clic **[!UICONTROL Server Files]**.
1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Audit]** per visualizzarne il contenuto.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server accanto al file desiderato, quindi fare clic **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato accanto al nome del file nella [!DNL Temp] colonna.
1. Fare clic con il pulsante destro del mouse sul nuovo segno di spunta nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il registro di controllo viene visualizzato in una nuova finestra Blocco note di Microsoft Windows.

   ![Informazioni sul passaggio](assets/cfg_accesscontrol_accessFile.png)

