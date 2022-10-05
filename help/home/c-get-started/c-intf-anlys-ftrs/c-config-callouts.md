---
description: I callout focalizzano l’attenzione su un particolare elemento dimensionale creando una nuova visualizzazione con una selezione virtuale di un particolare elemento dimensionale in una visualizzazione.
title: Configurare un callout
uuid: 779764bd-86c3-49cf-aabc-edb39caf0490
exl-id: 509163b2-0bd1-47b4-8612-aac460a501cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 1%

---

# Configurare un callout{#configure-a-callout}

{{eol}}

I callout focalizzano l’attenzione su un particolare elemento dimensionale creando una nuova visualizzazione con una selezione virtuale di un particolare elemento dimensionale in una visualizzazione.

È possibile aggiungere o modificare i callout configurando i file dei callout memorizzati in una cartella Profiles\*profile name*\Context\Callout di [!DNL Server] cartella di installazione. I callout che attirano l’attenzione su una particolare metrica in una visualizzazione di un foglio di lavoro sono denominati callout di metriche. I file di callout delle metriche sono memorizzati nella cartella Profiles\*profile name*\Context\Metric Callout .

Per istruzioni su come aggiungere un callout o un callout di metriche a una visualizzazione, vedere [Aggiunta di callout a un’area di lavoro](../../../home/c-get-started/c-vis/c-call-wkspc.md#concept-212b09e763044d938987b4a9c658adc0).

**Creazione di un nuovo tipo di callout**

1. In qualsiasi area di lavoro, crea una visualizzazione contenente i dati che desideri visualizzare nel nuovo tipo di callout. Ad esempio, se desideri che il callout sia una tabella, crea una visualizzazione tabella con la metrica e la dimensione desiderate.
1. Fare clic con il pulsante destro del mouse sul bordo superiore della finestra del callout e fare clic su **[!UICONTROL Save]**.
1. In [!DNL Save] finestra, fai clic su ![](assets/btn_folder_up.png), fai doppio clic su **[!UICONTROL Context]**, quindi fai doppio clic su **[!UICONTROL Callout]**. In [!DNL File Name] campo , digitare un nome per il file e fare clic su **[!UICONTROL Save]**. Il file del callout viene salvato nella cartella User\*working profile name*\Context\Callout.

   >[!NOTE]
   >
   >Quando assegni un nome al callout, scegli un nome descrittivo che rifletta il tipo di visualizzazione e la metrica e la dimensione che mostra. Ad esempio, se desideri creare un callout da una visualizzazione tabella che mostra la metrica Sessions sulla dimensione Day (Giorno), puoi denominare il callout &quot;Sessions by Day Table&quot; (Sessioni per tabella giorno).

1. (Facoltativo) Per rendere questa modifica disponibile a tutti gli utenti del profilo di lavoro:

   1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Context]**, quindi fai clic su **[!UICONTROL Callout]**. Questa cartella contiene tutti i file di visualizzazione ( [!DNL .vw]) che definiscono i tipi di callout esistenti.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file del nuovo callout nel [!DNL User] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Per convertire un callout in un callout di metriche**

1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Context]**, quindi fai clic su **[!UICONTROL Callout]**. Questa cartella contiene tutti i file di visualizzazione ( [!DNL .vw]) che definiscono i tipi di callout esistenti.

1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file del tipo di callout che si desidera modificare e fare clic su **[!UICONTROL Make Local]**. Dopo che il file è stato scaricato nel computer locale, viene visualizzato un segno di spunta nel [!DNL User] colonna.

1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file nel [!DNL User] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL In Notepad]**.

1. Individua il [!DNL metric_y = ref:] nel file del callout e sostituire il valore esistente con la parola Metrica. Il testo evidenziato nel frammento di file seguente mostra la posizione in cui è stata inserita la parola.

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

1. Fai clic su **[!UICONTROL File]** > **[!UICONTROL Save As]**. In **[!UICONTROL Save As]** finestra, fare clic una volta, quindi fare doppio clic **[!UICONTROL Metric Callout]**. In [!DNL File Name] campo , digitare un nome per il file e fare clic su **[!UICONTROL Save]**. Il file di callout della metrica viene salvato nella cartella User\*working profile name*\Context\Metric Callout.

1. (Facoltativo) Per rendere questo callout metrico disponibile a tutti gli utenti del profilo di lavoro, nel [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file nel [!DNL User] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
