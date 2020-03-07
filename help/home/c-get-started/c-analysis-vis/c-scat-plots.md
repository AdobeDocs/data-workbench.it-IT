---
description: Dispersione grafico rappresenta gli elementi di una dimensione dati (ad esempio Pagina o Città) su una griglia in cui gli assi x e y rappresentano metriche diverse.
solution: Analytics
title: Dispersione 2D
topic: Data workbench
uuid: 73c23d22-3c3a-4535-b66b-0e3508bd904c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dispersione 2D{#d-scatter-plots}

Dispersione grafico rappresenta gli elementi di una dimensione dati (ad esempio Pagina o Città) su una griglia in cui gli assi x e y rappresentano metriche diverse.

I grafici a dispersione possono essere utili quando si cerca di comprendere la relazione tra un gran numero di elementi diversi, in base a due metriche diverse. Nell&#39;esempio seguente, il grafico a dispersione mostra ogni città in base al numero di visitatori e al relativo tasso di fidelizzazione.

![](assets/vis_ScatterPlot_City.png)

Il grafico a dispersione consente di vedere rapidamente i contorni. Salt Lake City, ad esempio, ha un tasso di fidelizzazione superiore alla media per visitatore.

I grafici a dispersione possono essere utilizzati anche per mostrare la coerenza dei dati. Nell&#39;esempio seguente, il grafico a dispersione mostra il numero di visitatori con sessioni di una determinata lunghezza.

![](assets/vis_ScatterPlot_SessionDuration.png)

La dimensione di ciascun punto del grafico a dispersione è determinata dalla metrica del raggio. La metrica del raggio predefinito è diversa per ogni applicazione Adobe. Ad esempio, in [!DNL Site]la metrica radius è basata su Sessioni per impostazione predefinita. Potete modificare la metrica del raggio in modo che i punti nei grafici a dispersione rappresentino qualsiasi metrica disponibile. Per i passaggi necessari, consultate [Modifica delle metriche](../../../home/c-get-started/c-analysis-vis/c-scat-plots.md#section-fd80576d583c430cb469daf12e39aa2a) dei raggi Il colore dei punti è basato sulla legenda del colore aperta nell’area di lavoro. Per ulteriori informazioni sulle legende a colori, consultate Legende [a](../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)colori.

## Seleziona punti {#section-4b4d45f39b884d54bb7407b3b2f4ea50}

**Selezione di un singolo punto**

* Fare clic sul punto.

**Per aggiungere un altro punto o gruppo di punti alla selezione**

* Ctrl+clic su un punto o Ctrl+trascinamento su più punti.

**Per rimuovere un punto o un gruppo di punti dalla selezione**

* Maiusc+clic su un punto o Maiusc+trascinamento su più punti.

## Modifica delle dimensioni {#section-796cd962ef3f476caa89d99083782ed1}

* Fare clic con il pulsante destro del mouse sull&#39;etichetta della dimensione nella parte superiore del grafico e scegliere **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

## Modifica delle metriche {#section-44b8be9215cd4039b1eeb98ae1b31445}

**Per modificare la metrica visualizzata sull&#39;asse x o y di un grafico a dispersione**

* Fare clic con il pulsante destro del mouse sull&#39;etichetta della metrica da modificare e scegliere **[!UICONTROL Change Metric]** > *&lt;**[!UICONTROL metric name]**>*.

## Modifica delle metriche del raggio {#section-fd80576d583c430cb469daf12e39aa2a}

**Per modificare la metrica del raggio di un grafico a dispersione**

Fare clic con il pulsante destro del mouse sull&#39;etichetta della dimensione nella parte superiore del grafico e scegliere **[!UICONTROL Change Radius Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_ScatterPlot_Change.png)

