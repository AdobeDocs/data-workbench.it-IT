---
description: Gli avvisi amministrativi inviano notifiche e-mail agli indirizzi e-mail specificati quando vengono rilevati errori da Insight Server durante il normale funzionamento.
title: Configurazione degli avvisi amministrativi
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 2%

---

# Configurazione degli avvisi amministrativi{#configuring-administrative-alerts}

Gli avvisi amministrativi inviano notifiche e-mail agli indirizzi e-mail specificati quando vengono rilevati errori da Insight Server durante il normale funzionamento.

**Frequenza consigliata:** prima della produzione

>[!NOTE]
>
>L’utilizzo di avvisi amministrativi richiede che [!DNL Insight Server] abbia accesso a un server SMTP di inoltro per inviare avvisi tramite e-mail.

I destinatari delle notifiche e-mail dovrebbero essere il personale amministrativo chiave dei sistemi e le principali parti interessate.

Il file di avvisi amministrativi [!DNL Administrative Alerts.cfg] viene utilizzato per configurare gli avvisi amministrativi per [!DNL Insight Server].

>[!NOTE]
>
>Se si esegue un cluster, è necessario creare o modificare gli avvisi sul master [!DNL Insight Server] nel cluster.

**Creazione o modifica di un avviso amministrativo**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.
1. Fai clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] da configurare e fai clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL Administrative Alerts.cfg] si trova all&#39;interno di questa directory.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server *per [!DNL Administrative Alerts.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL Administrative Alerts.cfg].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. Nella finestra [!DNL Administrative Alerts.cfg] fare clic su **[!UICONTROL component]** per visualizzarne il contenuto.
1. Compila i parametri desiderati. Per un elenco dei parametri disponibili in questo file, consulta [Impostazioni di configurazione avvisi amministrativi](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![Informazioni sul passaggio](assets/cfg_adminalerts_examplevalues.png)

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. (Facoltativo) Se si lavora in un cluster e si desidera applicare gli stessi avvisi amministrativi a ogni unità di elaborazione dati, è necessario copiare e incollare il file [!DNL Administrative Alerts.cfg] aggiornato nella cartella [!DNL Components for Processing Servers] all&#39;interno della directory di installazione principale [!DNL Insight Server].
