---
description: Gli avvisi amministrativi inviano notifiche e-mail agli indirizzi e-mail specificati quando vengono rilevati errori da Insight Server durante il normale funzionamento.
solution: Insight
title: Configurazione degli avvisi amministrativi
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurazione degli avvisi amministrativi{#configuring-administrative-alerts}

Gli avvisi amministrativi inviano notifiche e-mail agli indirizzi e-mail specificati quando vengono rilevati errori da Insight Server durante il normale funzionamento.

**Frequenza consigliata:** Prima della produzione

>[!NOTE]
>
>L&#39;utilizzo di avvisi amministrativi richiede che [!DNL Insight Server] sia possibile accedere a un server SMTP di inoltro per inviare avvisi via e-mail.

I destinatari delle notifiche e-mail dovrebbero essere il personale amministrativo dei sistemi chiave e i principali soggetti interessati.

Il file di avvisi amministrativi, [!DNL Administrative Alerts.cfg], viene utilizzato per configurare gli avvisi amministrativi per [!DNL Insight Server].

>[!NOTE]
>
>Se si sta eseguendo un cluster, è necessario creare o modificare gli avvisi sul master [!DNL Insight Server] nel cluster.

**Creazione o modifica di un avviso amministrativo**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.
1. Fare clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] file da configurare e fare clic su **[!UICONTROL Server Files]**.
1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Administrative Alerts.cfg] file si trova all&#39;interno di questa directory.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server *per [!DNL Administrative Alerts.cfg] e fare clic **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Administrative Alerts.cfg].
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Nella [!DNL Administrative Alerts.cfg] finestra, fate clic **[!UICONTROL component]** per visualizzarne il contenuto.
1. Compilate i parametri come desiderate. Per un elenco dei parametri disponibili in questo file, consulta Impostazioni [di configurazione avvisi](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491)amministrativi.

   ![Informazioni sul passaggio](assets/cfg_adminalerts_examplevalues.png)

1. Salvate le modifiche al server effettuando le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare [!DNL Server Files Manager]clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL Temp] colonna e selezionare **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. (Facoltativo) Se si lavora in un cluster e si desidera applicare gli stessi avvisi amministrativi a ciascuna unità di elaborazione dati, è necessario copiare e incollare il [!DNL Administrative Alerts.cfg] file aggiornato nella [!DNL Components for Processing Servers] cartella all&#39;interno della directory di [!DNL Insight Server] installazione principale.
