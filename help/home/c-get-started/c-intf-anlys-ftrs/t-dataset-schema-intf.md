---
description: Passaggi per modificare la visualizzazione predefinita.
solution: Analytics
title: Configurare l'interfaccia dello schema del set di dati
topic: Data workbench
uuid: 953909e8-3382-43cf-98c0-d4785c6d1dda
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Configurare l&#39;interfaccia dello schema del set di dati{#configure-the-dataset-schema-interface}

Passaggi per modificare la visualizzazione predefinita.

Puoi controllare quale tipo di visualizzazione viene visualizzato quando fai clic su un nome di dimensione in un [!DNL Dataset Schema Interface] file aggiungendo dei file al nome del profilo\*\Context\Dimension Legend folder of the Data Workbench server installation folder. Il [!DNL Default.1d] file in questa cartella controlla il tipo di visualizzazione predefinito per tutte le dimensioni. Aggiungendo un file *Dimension name*.1d (ad esempio [!DNL Hour.1d]) a questa cartella, potete controllare la visualizzazione predefinita per quella particolare dimensione.

Per ulteriori informazioni su [!DNL Dataset Schema Interfaces], vedere [L&#39;interfaccia](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)Schema del set di dati.

**Per modificare la visualizzazione predefinita**

1. In qualsiasi area di lavoro, crea una visualizzazione contenente i dati da visualizzare nella nuova visualizzazione predefinita.

   Ad esempio, se desiderate che la dimensione venga visualizzata in un grafico a barre, create una visualizzazione grafico a barre che mostri la metrica e la dimensione desiderate.

1. Fare clic con il pulsante destro del mouse sul bordo superiore della finestra del callout e quindi scegliere **[!UICONTROL Save]**.
1. Nella [!DNL Save] finestra fare clic ![](assets/btn_folder_up.png), fare doppio clic **[!UICONTROL Context]**, quindi fare doppio clic **[!UICONTROL Dimension Legend]**.
1. Nel [!DNL File Name] campo, digitare il nome della dimensione.

   The name of the [!DNL .1d] file must match the name of the dimension exactly. Ad esempio, [!DNL Hour.1d] (Indirizzo IP).

1. Cambia l&#39;estensione del file in &quot;1d&quot; e fai clic **[!UICONTROL Save]**.

   Il file viene salvato nel nome del profilo di lavoro dell&#39;utente\*\Context\Dimension Legend folder.

   La prossima volta che fai clic su tale dimensione in una [!DNL Dataset Schema Interface], viene visualizzata la visualizzazione specificata.

1. (Facoltativo) Per rendere disponibile questa modifica a tutti gli utenti del profilo di lavoro:

   1. In the [!DNL Profile Manager], click **[!UICONTROL Context]**, then click **[!UICONTROL Dimension Legend]**.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file del nuovo callout nella [!DNL User] colonna e scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

