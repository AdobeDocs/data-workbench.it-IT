---
description: I file di log di controllo tengono traccia di tutte le connessioni tentate a Insight Server e delle disconnessioni da esse, ognuna delle quali è registrata nei file <YYYYMMDD>-access.txt che si trovano per impostazione predefinita nella cartella Audit all'interno della directory di installazione di Insight Server.
title: Monitoraggio degli audit di controllo
uuid: 38af9328-3f72-48a4-a0de-bf7477fedc25
exl-id: 220330da-e5dc-4ac0-9b70-42b08ccb3577
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 4%

---

# Monitoraggio degli audit di controllo{#monitoring-audit-logs}

I file di registro di controllo tengono traccia di tutte le connessioni tentate a Insight Server e delle disconnessioni da esse, ognuna delle quali è registrata nei file `<YYYYMMDD>-access.txt` che si trovano per impostazione predefinita nella cartella di controllo all’interno della directory di installazione di Insight Server.

**Frequenza consigliata:** giornaliera o in base alle esigenze per la risoluzione dei problemi

I log di controllo possono essere molto utili per la risoluzione dei problemi relativi alla connessione a [!DNL Insight Server]. Puoi monitorare questi registri utilizzando il tuo strumento di gestione automatizzata o visualizzando direttamente i file [!DNL access.txt] .

**Per visualizzare i file access.txt tramite[!DNL Server Files Manager]**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.
1. Fai clic con il pulsante destro del mouse sull&#39;icona di un elemento attivo [!DNL Insight Server] e fai clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Audit]** per visualizzarne il contenuto.
1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* accanto al file desiderato e fai clic su **[!UICONTROL Make Local]**. Accanto al nome del file nella colonna [!DNL Temp] viene visualizzato un segno di spunta.
1. Fai clic con il pulsante destro del mouse sul nuovo segno di spunta nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Il registro di controllo viene visualizzato in una nuova finestra Blocco note di Microsoft Windows.

   ![Informazioni sul passaggio](assets/cfg_accesscontrol_accessFile.png)
