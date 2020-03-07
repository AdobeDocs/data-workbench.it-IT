---
description: I callout richiamano l'attenzione su un particolare elemento di dimensione creando una nuova visualizzazione con una selezione virtuale di un particolare elemento di dimensione in una visualizzazione.
solution: Analytics
title: Configurare un callout
topic: Data workbench
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurare un callout{#configure-a-callout}

I callout richiamano l&#39;attenzione su un particolare elemento di dimensione creando una nuova visualizzazione con una selezione virtuale di un particolare elemento di dimensione in una visualizzazione.

È possibile aggiungere o modificare i callout configurando i file di callout memorizzati in una cartella di installazione Profili\*\Context\Callout folder of the [!DNL Server] . I callout che richiamano l&#39;attenzione su una particolare metrica in una visualizzazione di un foglio di lavoro sono denominati callout di metrica. I file di callout delle metriche sono memorizzati nel nome del profilo\*\Context\Metric Callout folder.

Per istruzioni su come aggiungere un callout o un callout di metriche a una visualizzazione, vedere [Aggiunta di callout a un’area di lavoro](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**Per creare un nuovo tipo di callout**

1. In qualsiasi area di lavoro, creare una visualizzazione contenente i dati che si desidera visualizzare nel nuovo tipo di callout. Ad esempio, se si desidera che il callout sia una tabella, è possibile creare una visualizzazione di tabella che mostra la metrica e la dimensione desiderate.
1. Fare clic con il pulsante destro del mouse sul bordo superiore della finestra del callout e quindi scegliere **[!UICONTROL Save]**.
1. Nella [!DNL Save] finestra fare clic ![](assets/btn_folder_up.png), fare doppio clic **[!UICONTROL Context]**, quindi fare doppio clic **[!UICONTROL Callout]**. Nel [!DNL File Name] campo, digitare un nome per il file e fare clic su **[!UICONTROL Save]**. Il file del callout viene salvato nel nome del profilo di lavoro dell&#39;utente\*\Context\Callout folder.

   >[!NOTE]
   >
   >Quando assegnate un nome al callout, scegliete un nome descrittivo che rifletta il tipo di visualizzazione e la metrica e la dimensione mostrata. Ad esempio, se si desidera creare un callout da una visualizzazione di tabella che mostra la metrica Sessioni sulla dimensione Giorno, è possibile assegnare al callout il nome &quot;Sessioni per tabella giorno&quot;.

1. (Facoltativo) Per rendere disponibile questa modifica a tutti gli utenti del profilo di lavoro:

   1. In the [!DNL Profile Manager], click **[!UICONTROL Context]**, then click **[!UICONTROL Callout]**. Questa cartella contiene tutti i file di visualizzazione ( [!DNL .vw]) che definiscono i tipi di callout esistenti.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file del nuovo callout nella [!DNL User] colonna e scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Per modificare un callout in un callout di metriche**

1. In the [!DNL Profile Manager], click **[!UICONTROL Context]**, then click **[!UICONTROL Callout]**. Questa cartella contiene tutti i file di visualizzazione ( [!DNL .vw]) che definiscono i tipi di callout esistenti.

1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file del tipo di callout che si desidera modificare e fare clic **[!UICONTROL Make Local]**. Dopo che il file è stato scaricato nel computer locale, nella [!DNL User] colonna viene visualizzato un segno di spunta.

1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file nella [!DNL User] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Individuare la [!DNL metric_y = ref:] voce nel file del callout e sostituire il valore esistente con la parola Metrica. Il testo evidenziato nel frammento di file seguente mostra la posizione in cui viene inserita la parola.

   ```
   window = simpleBorderWindow: 
     client = graph: 
       bars = bool: true
       dim_x = ref: wdata/model/dim/dimension name
       lines = bool: false
       metrics = vector: 1 items
         0 = gr_metric: 
           metric_y = ref: Metric
           yaxis = axisLegend: 
             max_value = double: maximum y-value
             min_value = double: minimum y-value
             zoom_max = double: maximum y-zoom
             zoom_min = double: minimum y-zoom
   . . . 
   ```

1. Fai clic su **[!UICONTROL File]** > **[!UICONTROL Save As]**. Nella **[!UICONTROL Save As]** finestra, fare clic una volta, quindi fare doppio clic **[!UICONTROL Metric Callout]**. Nel [!DNL File Name] campo, digitare un nome per il file e fare clic su **[!UICONTROL Save]**. Il file del callout della metrica viene salvato nel nome del profilo di lavoro dell&#39;utente\*\Context\Metric Callout folder.

1. (Facoltativo) Per rendere disponibile questo callout metrica a tutti gli utenti del profilo di lavoro, fare clic con il pulsante destro del [!DNL Profile Manager]mouse sul segno di spunta accanto al nome del file nella [!DNL User] colonna e scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

