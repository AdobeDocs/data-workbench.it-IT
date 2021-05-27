---
description: È possibile utilizzare i fogli di lavoro per indicare che una metrica ha raggiunto una soglia definita.
title: Creare un indicatore di metrica
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
exl-id: 5713f3dd-85ef-407c-b21c-80e9b4390b6d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 2%

---

# Creare un indicatore di metrica{#create-a-metric-indicator}

È possibile utilizzare i fogli di lavoro per indicare che una metrica ha raggiunto una soglia definita.

Inoltre, puoi utilizzare [!DNL Report] per generare e distribuire automaticamente un rapporto quando una metrica raggiunge una soglia definita entro un intervallo di tempo specificato.

Per ulteriori informazioni su [!DNL Report], consulta la *Data Workbench guida ai rapporti*.

* [Indicatore Su o Giù](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [Indicatore di controllo](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**Per creare un indicatore di metrica utilizzando un foglio di lavoro**

1. Definire il contenuto delle celle del foglio di lavoro.

   1. Nella colonna A, immetti il nome della metrica desiderata (ad esempio, [!DNL Visitors]).
   1. Nella colonna B, immetti il valore della metrica desiderata (ad esempio, [!DNL =Visitors]).
   1. Nella colonna C, immetti la soglia minima della metrica.
   1. Nella colonna D, immetti la soglia elevata della metrica.
   1. Nella colonna E, immettere una formula appropriata. Per esempi, vedere [Indicatore Su o Giù](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba) o [Indicatore di spunta](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
   1. Nella cella della formula (Colonna E) fare clic con il pulsante destro del mouse e scegliere **[!UICONTROL Format]** > **[!UICONTROL Indicator]**, quindi fare clic su una delle seguenti opzioni:

      * **[!UICONTROL None]**: Elenca il calcolo esatto invece di un indicatore.
      * **[!UICONTROL Check]**: Utilizza un segno di spunta o una X per indicare che il valore è superiore o inferiore alla soglia impostata, a seconda della formula. Vedere [Indicatore di spunta](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090).
      * **[!UICONTROL Up or Down]**: Utilizza una freccia su o giù per indicare se il valore è inferiore alla soglia bassa (freccia giù), sopra la soglia alta (freccia su) o tra le soglie basse e alte (vuoto). Vedere [Indicatore Su o Giù](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba).

1. Ripeti il passaggio 1 per altre metriche per le quali desideri creare indicatori.

Il foglio di lavoro risultante avrà un aspetto simile al seguente:

![](assets/vis_Worksheet_Alerts.png)

## Indicatore su o giù {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

Per [!DNL Up] o [!DNL Down indicator], utilizza la formula seguente:

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

Ad esempio: [!DNL =(b2-c2)/(d2-c2)*2-1]

Per ogni metrica sono possibili tre risultati quando si utilizza questa formula con [!DNL Up] o [!DNL Down indicator]:

* Se il valore della metrica è compreso tra le soglie basse e alte, la formula restituisce un numero compreso tra -1 e 1 (esclusivamente). La freccia su o giù non viene visualizzata nel foglio di lavoro.
* Se il valore della metrica è minore o uguale alla soglia minima, la formula restituisce un valore minore o uguale a -1. L’indicatore della metrica diventa una freccia giù.
* Se il valore della metrica è maggiore o uguale alla soglia elevata, la formula restituisce un numero maggiore o uguale a 1. L’indicatore della metrica diventa una freccia su.

Il seguente foglio di lavoro illustra la visualizzazione della formula di esempio [!DNL =(b2-c2)/(d2-c2)*2-1]:

![](assets/vis_Worksheet_Alerts_UpDown.png)

## Indicatore di controllo {#section-98c5298a74f34dcbaaf151549fcc7090}

Per [!DNL Check indicator], utilizza una formula che indica se desideri ricevere una notifica quando il valore della metrica è superiore o inferiore alla soglia specificata. Ad esempio:

* Se desideri ricevere una notifica quando il valore è inferiore alla soglia impostata, puoi utilizzare il formato seguente:

   * [!DNL threshold - metric]

      Ad esempio: [!DNL =(c2-b2)]

* Se desideri ricevere una notifica quando il valore è superiore alla soglia impostata, puoi utilizzare la formula seguente:

   * [!DNL metric - threshold]

      Ad esempio: [!DNL =(b3-c3)]

Quando viene visualizzato un segno di spunta, la formula viene valutata in un numero positivo. Quando viene visualizzata una X, la formula viene valutata in un numero negativo.

Esistono due possibili risultati per ogni metrica quando si utilizza [!DNL Check indicator]:

* Se la formula indica che è auspicabile mantenere il valore della metrica al di sopra della soglia, viene visualizzato un segno di spunta quando il valore della metrica è maggiore o uguale alla soglia e viene visualizzata una X quando il valore è inferiore alla soglia.
* Se la formula indica che è auspicabile mantenere il valore della metrica al di sotto della soglia, viene visualizzato un segno di spunta quando il valore della metrica è minore o uguale alla soglia e viene visualizzata una X quando il valore è maggiore della soglia.

Il seguente foglio di lavoro illustra la visualizzazione delle formule di esempio [!DNL =(c2-b2)] e [!DNL =(b3-c3)]:

![](assets/vis_Worksheet_Alerts_Check.png)
