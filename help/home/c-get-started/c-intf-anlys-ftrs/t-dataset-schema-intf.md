---
description: Passaggi per modificare la visualizzazione predefinita.
title: Configurare l’interfaccia Interfaccia Dataset Schema (Schema del set di dati)
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---

# Configurare l’interfaccia Interfaccia Dataset Schema (Schema del set di dati){#configure-the-dataset-schema-interface}

Passaggi per modificare la visualizzazione predefinita.

Puoi controllare quale tipo di visualizzazione viene visualizzato quando fai clic su un nome di dimensione in una [!DNL Dataset Schema Interface] aggiungendo file al nome del profilo Profiles\*\Context\Dimension Legend folder of the Data Workbench server installation folder. Il file [!DNL Default.1d] in questa cartella controlla il tipo di visualizzazione predefinito per tutte le dimensioni. Aggiungendo un file *nome dimensione*.1d (ad esempio [!DNL Hour.1d]) a questa cartella, puoi controllare la visualizzazione predefinita per quella particolare dimensione.

Per ulteriori informazioni su [!DNL Dataset Schema Interfaces], consulta [Interfaccia schema set di dati](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**Per modificare la visualizzazione predefinita**

1. Crea una visualizzazione in qualsiasi area di lavoro contenente i dati che vuoi visualizzare nella nuova visualizzazione predefinita.

   Ad esempio, se desideri che la dimensione venga visualizzata in un grafico a barre, crea una visualizzazione grafico a barre con la metrica e la dimensione desiderate.

1. Fare clic con il pulsante destro del mouse sul bordo superiore della finestra del callout e fare clic su **[!UICONTROL Save]**.
1. Nella finestra [!DNL Save], fai clic su ![](assets/btn_folder_up.png), fai doppio clic su **[!UICONTROL Context]**, quindi fai doppio clic su **[!UICONTROL Dimension Legend]**.
1. Nel campo [!DNL File Name] , digita il nome della dimensione.

   Il nome del file [!DNL .1d] deve corrispondere esattamente al nome della dimensione. Ad esempio, [!DNL Hour.1d].

1. Modifica l’estensione del file in &quot;1d&quot; e fai clic su **[!UICONTROL Save]**.

   Il file viene salvato nel nome del profilo di lavoro utente\*\Context\Dimension Legend folder.

   La prossima volta che fai clic su tale dimensione in una [!DNL Dataset Schema Interface] viene visualizzata la visualizzazione specificata.

1. (Facoltativo) Per rendere questa modifica disponibile a tutti gli utenti del profilo di lavoro:

   1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Context]**, quindi fai clic su **[!UICONTROL Dimension Legend]**.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file del nuovo callout nella colonna [!DNL User] e fare clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
