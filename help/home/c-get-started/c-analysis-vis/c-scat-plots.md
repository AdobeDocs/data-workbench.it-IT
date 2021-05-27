---
description: I grafici a dispersione rappresentano gli elementi di una dimensione dati (ad esempio Pagina o Città) in una griglia in cui gli assi x e y rappresentano metriche diverse.
title: Dispersioni 2D
uuid: 73c23d22-3c3a-4535-b66b-0e3508bd904c
exl-id: 340f8c18-ce47-4f3a-aba4-3d6124505313
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 1%

---

# Dispersioni 2D{#d-scatter-plots}

I grafici a dispersione rappresentano gli elementi di una dimensione dati (ad esempio Pagina o Città) in una griglia in cui gli assi x e y rappresentano metriche diverse.

I grafici a dispersione possono essere utili quando si cerca di comprendere la relazione tra un numero elevato di elementi diversi, in base a due metriche diverse. Nell’esempio seguente, il grafico a dispersione mostra ogni città in base al numero di visitatori e al relativo tasso di fidelizzazione.

![](assets/vis_ScatterPlot_City.png)

Il grafico a dispersione consente di vedere rapidamente gli outlier. Salt Lake City, ad esempio, ha un tasso di fidelizzazione superiore alla media per visitatore.

I grafici a dispersione possono essere utilizzati anche per mostrare la coerenza dei dati. Nell’esempio seguente, il grafico a dispersione mostra il numero di visitatori con sessioni di una particolare lunghezza.

![](assets/vis_ScatterPlot_SessionDuration.png)

La dimensione di ogni punto del grafico a dispersione è determinata dalla metrica del raggio. La metrica del raggio predefinito è diversa per ogni applicazione di Adobe. Ad esempio, in [!DNL Site], la metrica del raggio è basata su Sessioni per impostazione predefinita. Puoi modificare la metrica del raggio in modo che i punti nei grafici a dispersione rappresentino qualsiasi metrica disponibile. Per i passaggi necessari, consulta [Modifica delle metriche del raggio](../../../home/c-get-started/c-analysis-vis/c-scat-plots.md#section-fd80576d583c430cb469daf12e39aa2a) Il colore dei punti è basato sulla legenda del colore aperta nell’area di lavoro. Per ulteriori informazioni sulle legende a colori, consulta [Color Legends](../../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).

## Seleziona punti {#section-4b4d45f39b884d54bb7407b3b2f4ea50}

**Selezione di un singolo punto**

* Fai clic sul punto.

**Per aggiungere un altro punto o gruppo di punti alla selezione**

* Ctrl+clic su un punto o Ctrl+trascinamento su più punti.

**Per rimuovere un punto o un gruppo di punti dalla selezione**

* Maiusc+clic su un punto o Maiusc+trascinamento su diversi punti.

## Modifica delle dimensioni {#section-796cd962ef3f476caa89d99083782ed1}

* Fai clic con il pulsante destro del mouse sull’etichetta della dimensione nella parte superiore del grafico e fai clic su **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

## Modifica delle metriche {#section-44b8be9215cd4039b1eeb98ae1b31445}

**Per modificare la metrica visualizzata sull’asse x o y di un grafico a dispersione**

* Fai clic con il pulsante destro del mouse sull’etichetta della metrica da modificare e fai clic su **[!UICONTROL Change Metric]** > *&lt;**[!UICONTROL metric name]**>*.

## Modifica delle metriche del raggio {#section-fd80576d583c430cb469daf12e39aa2a}

**Per modificare la metrica del raggio di un grafico a dispersione**

Fai clic con il pulsante destro del mouse sull’etichetta della dimensione nella parte superiore del grafico e fai clic su **[!UICONTROL Change Radius Metric]** > *&lt;**[!UICONTROL metric name]**>*.

![](assets/mnu_ScatterPlot_Change.png)
