---
description: Passaggi per modificare la visualizzazione predefinita.
title: Configurare l’interfaccia Interfaccia Dataset Schema (Schema del set di dati)
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
exl-id: 0227663f-4789-4780-b753-d0deb35f6144
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 4%

---

# Configurare l’interfaccia Interfaccia Dataset Schema (Schema del set di dati){#configure-the-dataset-schema-interface}

{{eol}}

Passaggi per modificare la visualizzazione predefinita.

Puoi controllare quale tipo di visualizzazione viene visualizzato quando fai clic sul nome di una dimensione in un [!DNL Dataset Schema Interface] aggiungendo file alla cartella Profiles\*profile name*\Context\Dimension Legend della cartella di installazione del server Data Workbench. La [!DNL Default.1d] in questa cartella controlla il tipo di visualizzazione predefinito per tutte le dimensioni. Aggiungendo una *nome dimensione* file .1d (ad esempio [!DNL Hour.1d]) in questa cartella, puoi controllare la visualizzazione predefinita per quella particolare dimensione.

Per ulteriori informazioni [!DNL Dataset Schema Interfaces], vedi [Interfaccia dello schema del set di dati](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**Per modificare la visualizzazione predefinita**

1. Crea una visualizzazione in qualsiasi area di lavoro contenente i dati che vuoi visualizzare nella nuova visualizzazione predefinita.

   Ad esempio, se desideri che la dimensione venga visualizzata in un grafico a barre, crea una visualizzazione grafico a barre con la metrica e la dimensione desiderate.

1. Fare clic con il pulsante destro del mouse sul bordo superiore della finestra del callout e fare clic su **[!UICONTROL Save]**.
1. In [!DNL Save] finestra, fai clic su ![](assets/btn_folder_up.png), fai doppio clic su **[!UICONTROL Context]**, quindi fai doppio clic su **[!UICONTROL Dimension Legend]**.
1. In [!DNL File Name] campo , digitare il nome della dimensione.

   Nome della [!DNL .1d] il file deve corrispondere esattamente al nome della dimensione. Esempio: [!DNL Hour.1d].

1. Modifica l&#39;estensione del file in &quot;1d&quot; e fai clic su **[!UICONTROL Save]**.

   Il file viene salvato nella cartella User\*working profile name*\Context\Dimension Legend.

   La prossima volta da cui fai clic su tale dimensione in un [!DNL Dataset Schema Interface], viene visualizzata la visualizzazione specificata.

1. (Facoltativo) Per rendere questa modifica disponibile a tutti gli utenti del profilo di lavoro:

   1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Context]**, quindi fai clic su **[!UICONTROL Dimension Legend]**.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file del nuovo callout nel [!DNL User] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
