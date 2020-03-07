---
description: I callout sono finestre aggiunte a un'area di lavoro per attirare l'attenzione su un particolare elemento dimensione creando una nuova visualizzazione con una selezione virtuale di tale elemento.
solution: Analytics
title: Aggiunta di layout a un'area di lavoro
topic: Data workbench
uuid: fb3dd74d-da20-40cb-bc96-e56d25003e48
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aggiunta di layout a un&#39;area di lavoro{#adding-callouts-to-a-workspace}

I callout sono finestre aggiunte a un&#39;area di lavoro per attirare l&#39;attenzione su un particolare elemento dimensione creando una nuova visualizzazione con una selezione virtuale di tale elemento.

Workbench dati viene distribuito con un set standard di tipi di callout. Poiché l&#39;implementazione può essere completamente personalizzata, i tipi di callout disponibili visualizzati nell&#39;implementazione potrebbero essere diversi da quelli documentati in questa guida.

Per impostazione predefinita, Workbench dati fornisce i seguenti callout:

* [Annotazione](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-7b6742160b3f4aed872a09c8c023f90d)
* [Grafico a linee vuote](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Tracciato a dispersione vuoto](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Tabella vuota](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-5dcc0504bdb64ed4976f880e2f7b277f)
* [Legenda di confidenza](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-386d1293ddc24a0c9cccb332e20db791)
* [Legenda metrica](../../../home/c-get-started/c-vis/c-call-wkspc.md#section-daa6d372c22246d9827880a9d6e804d8)

>[!NOTE]
>
>I callout non funzionano come selezioni, ovvero non influenzano altre visualizzazioni all&#39;interno dell&#39;area di lavoro, a meno che non venga effettuata una selezione all&#39;interno del callout.

È possibile aggiungere o modificare le definizioni dei callout configurando i file dei callout memorizzati nel nome del *profilo*\Context\Callout folder of the [!DNL Server] cartella di installazione. Consultate [Configurazione di Callout](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-callouts.md#concept-f6e91e172f5e4c009245c9c549beb76a).

## Aggiunta di un callout di annotazioni a una visualizzazione {#section-7b6742160b3f4aed872a09c8c023f90d}

1. Fare clic con il pulsante destro del mouse sull&#39;elemento per il quale si desidera creare un callout, quindi scegliere **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Image]** o **[!UICONTROL Add Callout]** > **[!UICONTROL Annotation]** > **[!UICONTROL Text]**. Viene visualizzata una finestra vuota con una connessione visibile a tale elemento.

   ![](assets/client-call.png)

   Per aggiungere delle didascalie alle visualizzazioni Grafico, fai clic con il pulsante destro del mouse nella parte inferiore della visualizzazione (l’asse di base) per aprire un menu.

   ![](assets/visualization_callout_linegraph.png)

1. A seconda della selezione, completa il passaggio appropriato:

   * Per un&#39;annotazione di testo, digitate o incollate il testo desiderato nel callout, quindi formattate il testo come appropriato. Vedere [Uso delle annotazioni](../../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777)di testo.
   * Per un’annotazione immagine, incollate l’immagine desiderata nel callout copiando l’immagine, quindi facendo clic con il pulsante destro del mouse all’interno del callout. Fai clic su **[!UICONTROL Paste image]** (Fine). Consultate [Utilizzo delle annotazioni](../../../home/c-get-started/c-analysis-vis/c-annots/c-image-annots.md#concept-02081ed7d91c4fdcb8fc863f2a51c962)immagine.

## Aggiunta di un callout vuoto per tabelle, grafici a linee o grafici a dispersione a una visualizzazione {#section-5dcc0504bdb64ed4976f880e2f7b277f}

1. Fare clic con il pulsante destro del mouse sull&#39;elemento per il quale si desidera creare un callout e scegliere **[!UICONTROL Add Callout]** > *&lt;**[!UICONTROL callout type]**>*.

   L&#39;esempio seguente mostra un callout di tabella vuota.

   ![](assets/vis_callout_blank_bar_graph.png)

1. Per selezionare una dimensione, fare clic con il pulsante destro del mouse **[!UICONTROL None]** e scegliere **[!UICONTROL Change Dimension]** > *&lt;**[!UICONTROL dimension name]**>*.

   >[!NOTE]
   >
   >Se si modifica la dimensione all’interno di una visualizzazione con un callout, il callout passa dall’essere connesso all’elemento della dimensione originale a essere connesso all’intera visualizzazione.

## Aggiunta di un callout con una legenda di confidenza a una visualizzazione {#section-386d1293ddc24a0c9cccb332e20db791}

1. Fare clic con il pulsante destro del mouse sull&#39;elemento per il quale si desidera creare il callout, quindi scegliere **[!UICONTROL Add Callout]** > **[!UICONTROL Confidence Legend]**.

   ![](assets/vis_callout_confidenceLegend.png)

1. Se desiderato, modificate il [!DNL Metric or Formula] campo.

Per le regole di sintassi delle espressioni, vedere Sintassi [della lingua](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)query. Consulta Leggende sulla [fiducia](../../../home/c-get-started/c-analysis-vis/c-legends/c-conf-leg.md#concept-73db81c2c218427786c04068aa778efd).

## Aggiunta di un callout della legenda metrica a una visualizzazione {#section-daa6d372c22246d9827880a9d6e804d8}

1. Fare clic con il pulsante destro del mouse sull&#39;elemento per il quale si desidera creare il callout, quindi scegliere **[!UICONTROL Add Callout]** > **[!UICONTROL Metric Legend]**.

   ![](assets/vis_callout_metricLegend.png)

1. Se necessario, aggiungi o rimuovi metriche dalla legenda delle metriche.

Consulta Legende [](../../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b)metriche.
