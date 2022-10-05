---
description: Gli avvisi amministrativi inviano notifiche e-mail agli indirizzi e-mail specificati quando vengono rilevati errori da Insight Server durante il normale funzionamento.
title: Configurazione degli avvisi amministrativi
uuid: 398e088b-ff83-46ae-a20c-ba0b50d85702
exl-id: 886e390f-fb2c-4922-8b01-9e5133a94e1b
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 2%

---

# Configurazione degli avvisi amministrativi{#configuring-administrative-alerts}

{{eol}}

Gli avvisi amministrativi inviano notifiche e-mail agli indirizzi e-mail specificati quando vengono rilevati errori da Insight Server durante il normale funzionamento.

**Frequenza consigliata:** Prima della produzione

>[!NOTE]
>
>L&#39;uso di segnalazioni amministrative richiede che [!DNL Insight Server] ha accesso a un server SMTP di inoltro per inviare avvisi tramite e-mail.

I destinatari delle notifiche e-mail dovrebbero essere il personale amministrativo chiave dei sistemi e le principali parti interessate.

Il file Avvisi amministrativi, [!DNL Administrative Alerts.cfg], viene utilizzato per configurare gli avvisi amministrativi per [!DNL Insight Server].

>[!NOTE]
>
>Se si esegue un cluster, è necessario creare o modificare gli avvisi sul master [!DNL Insight Server] nel cluster.

**Creazione o modifica di un avviso amministrativo**

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.
1. Fai clic con il pulsante destro del mouse sull’icona [!DNL Insight Server] si desidera configurare e fare clic su **[!UICONTROL Server Files]**.
1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. La [!DNL Administrative Alerts.cfg] il file si trova all&#39;interno di questa directory.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server *per [!DNL Administrative Alerts.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nel [!DNL Temp] colonna per [!DNL Administrative Alerts.cfg].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. In [!DNL Administrative Alerts.cfg] finestra, fai clic su **[!UICONTROL component]** per visualizzarne il contenuto.
1. Compila i parametri desiderati. Per un elenco dei parametri disponibili in questo file, vedi [Impostazioni di configurazione degli avvisi amministrativi](../../../home/c-inst-svr/c-cfg-stgs-ref/c-admin-alts-cfg-stgs.md#concept-14c3c3ed797f47c5900ec04cae2fc491).

   ![Informazioni sul passaggio](assets/cfg_adminalerts_examplevalues.png)

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

1. (Facoltativo) Se lavori in un cluster e desideri applicare gli stessi avvisi amministrativi a ogni unità di elaborazione dati, devi copiare e incollare l&#39;aggiornamento [!DNL Administrative Alerts.cfg] in [!DNL Components for Processing Servers] cartella all’interno del master [!DNL Insight Server] directory di installazione.
