---
description: È possibile utilizzare i fogli di lavoro per indicare che una metrica ha raggiunto una soglia definita.
solution: Analytics
title: Creare un indicatore di metrica
topic: Data workbench
uuid: da304004-ef45-4c89-8c91-dd5158172dd6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creare un indicatore di metrica{#create-a-metric-indicator}

È possibile utilizzare i fogli di lavoro per indicare che una metrica ha raggiunto una soglia definita.

Inoltre, puoi utilizzare [!DNL Report] per generare e distribuire automaticamente un rapporto quando una metrica raggiunge una soglia definita entro un intervallo di tempo specificato.

Per ulteriori informazioni su [!DNL Report]questo argomento, vedere la Guida *al rapporto di Workbench* dati.

* [Indicatore Su o Giù](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)
* [Indicatore di controllo](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)

**Creazione di un indicatore di metrica tramite un foglio di lavoro**

1. Definire il contenuto delle celle del foglio di lavoro.

   1. Nella colonna A, inserite il nome della metrica desiderata (ad esempio, [!DNL Visitors]).
   1. Nella colonna B, inserite il valore della metrica desiderata (ad esempio, [!DNL =Visitors]).
   1. Nella colonna C, immettete la soglia minima della metrica.
   1. Nella colonna D, immetti la soglia alta della metrica.
   1. Nella colonna E, immettere una formula appropriata. Ad esempio, vedere [Indicatore](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba) Su o Giù o [Indicatore](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)di spunta.
   1. Nella cella formula (Colonna E), fare clic con il pulsante destro del mouse e scegliere **[!UICONTROL Format]** > **[!UICONTROL Indicator]**, quindi fare clic su una delle opzioni seguenti:

      * **[!UICONTROL None]**: Elenca il calcolo esatto invece di un indicatore.
      * **[!UICONTROL Check]**: Utilizza un segno di spunta o una X per indicare che il valore è superiore o inferiore alla soglia impostata, a seconda della formula. Vedere [Indicatore](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-98c5298a74f34dcbaaf151549fcc7090)di controllo.
      * **[!UICONTROL Up or Down]**: Utilizza una freccia su o giù per indicare se il valore è inferiore alla soglia bassa (freccia giù), sopra la soglia alta (freccia su) o tra le soglie basse e alte (vuoto). Consultate [Indicatore](../../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#section-40d7a2c3df0d40d4a7bb1a7e856abcba)Su o Giù.

1. Ripetere il passaggio 1 per altre metriche per le quali si desidera creare indicatori.

Il foglio di lavoro risultante sarà simile al seguente esempio:

![](assets/vis_Worksheet_Alerts.png)

## Indicatore su o giù {#section-40d7a2c3df0d40d4a7bb1a7e856abcba}

Per [!DNL Up] o [!DNL Down indicator], utilizzare la seguente formula:

[!DNL (metric value - low threshold)/(high threshold - low threshold)*2 - 1]

Ad esempio: [!DNL =(b2-c2)/(d2-c2)*2-1]

Tre risultati sono possibili per ogni metrica quando si utilizza questa formula con [!DNL Up] o [!DNL Down indicator]:

* Se il valore della metrica è compreso tra soglie basse e alte, la formula restituisce un numero compreso tra -1 e 1 (esclusivamente). La freccia su o giù non viene visualizzata nel foglio di lavoro.
* Se il valore della metrica è minore o uguale alla soglia bassa, la formula restituisce un valore minore o uguale a -1. L’indicatore della metrica diventa una freccia giù.
* Se il valore della metrica è maggiore o uguale alla soglia alta, la formula restituisce un numero maggiore o uguale a 1. L’indicatore della metrica diventa una freccia su.

Il seguente foglio di lavoro illustra la visualizzazione della formula di esempio: [!DNL =(b2-c2)/(d2-c2)*2-1]

![](assets/vis_Worksheet_Alerts_UpDown.png)

## Indicatore di controllo {#section-98c5298a74f34dcbaaf151549fcc7090}

Per [!DNL Check indicator], si utilizza una formula che indica se si desidera ricevere una notifica quando il valore della metrica è superiore o inferiore alla soglia specificata. Ad esempio:

* Se desiderate ricevere una notifica quando il valore è inferiore alla soglia impostata, potete utilizzare il formato seguente:

   * [!DNL threshold - metric]

      Ad esempio: [!DNL =(c2-b2)]

* Se desiderate ricevere una notifica quando il valore è superiore alla soglia impostata, potete utilizzare la seguente formula:

   * [!DNL metric - threshold]

      Ad esempio: [!DNL =(b3-c3)]

Quando viene visualizzato un segno di spunta, la formula viene valutata in un numero positivo. Quando viene visualizzata una X, la formula è valutata su un numero negativo.

Esistono due possibili risultati per ogni metrica quando si utilizza [!DNL Check indicator]:

* Se la formula indica che è auspicabile mantenere il valore della metrica al di sopra della soglia, viene visualizzato un segno di spunta quando il valore della metrica è maggiore o uguale alla soglia, e una X viene visualizzata quando il valore è inferiore alla soglia.
* Se la formula indica che è auspicabile mantenere il valore della metrica al di sotto della soglia, viene visualizzato un segno di spunta quando il valore della metrica è minore o uguale alla soglia, e una X viene visualizzata quando il valore è maggiore della soglia.

Il seguente foglio di lavoro illustra le formule di esempio [!DNL =(c2-b2)] e [!DNL =(b3-c3)] la relativa visualizzazione:

![](assets/vis_Worksheet_Alerts_Check.png)

