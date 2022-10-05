---
description: I file di registro di controllo tengono traccia di tutte le connessioni tentate a Insight Server e delle disconnessioni da esse eseguite, ognuna delle quali è registrata <yyyymmdd>I file -access.txt si trovano per impostazione predefinita nella cartella Audit all'interno della directory di installazione di Insight Server.
title: Monitoraggio degli audit di controllo
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# Monitoraggio degli audit di controllo{#monitoring-audit-logs}

{{eol}}

I file di registro di controllo tengono traccia di tutte le connessioni tentate a Insight Server e delle disconnessioni da esse eseguite, ognuna delle quali è registrata `<YYYYMMDD>-access.txt` i file che si trovano per impostazione predefinita nella cartella Audit all&#39;interno della directory di installazione di Insight Server.

**Frequenza consigliata:** Giornaliero o in base alle esigenze per la risoluzione dei problemi

I log di controllo possono essere molto utili quando si risolvono problemi di connessione a [!DNL Insight Server]. Puoi monitorare questi registri utilizzando il tuo strumento di gestione automatizzata o visualizzando il [!DNL access.txt] file direttamente.

**Per visualizzare i file access.txt tramite[!DNL Server Files Manager]**

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.
1. Fai clic con il pulsante destro del mouse sull’icona di un attivo [!DNL Insight Server] e fai clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Audit]** per visualizzarne il contenuto.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* accanto al file desiderato e fai clic su **[!UICONTROL Make Local]**. Accanto al nome del file nel [!DNL Temp] colonna.
1. Fai clic con il pulsante destro del mouse sul nuovo segno di spunta nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il registro di controllo viene visualizzato in una nuova finestra Blocco note di Microsoft Windows.

   ![Informazioni sul passaggio](assets/cfg_accesscontrol_accessFile.png)
