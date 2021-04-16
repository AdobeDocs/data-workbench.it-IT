---
description: Il punteggio tendenza ti consente di definire i clienti in base alla loro possibilità di una conversione o del completamento di un evento specifico. Consente di massimizzare l’impatto potenziale delle attività prima di eseguire un processo o indirizzare una campagna.
title: Punteggio tendenza
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
exl-id: 832a1e6c-8eeb-4dcc-97e8-9570e1a6eb4f
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '747'
ht-degree: 24%

---

# Punteggio tendenza{#propensity-scoring}

Il punteggio tendenza ti consente di definire i clienti in base alla loro possibilità di una conversione o del completamento di un evento specifico. Consente di massimizzare l’impatto potenziale delle attività prima di eseguire un processo o indirizzare una campagna.

## Valore del punteggio tendenza  {#section-c51ece66effc42de9b754f0f46027c1b}

Il punteggio tendenza ti consente di eseguire il rilevamento dei dati per identificare i comportamenti o i pattern nascosti esistenti nei tuoi dati. In particolare, il punteggio di propensione ti aiuta a identificare cluster di clienti simili utilizzando metodi più focalizzati e obiettivi al posto dei semplici filtri o segmentazione. Inoltre, il punteggio di tendenza ti consente di impostare funzionalità predittive per l’identificazione del comportamento del cliente di alto valore della tua azienda.

Una volta identificato il pubblico di alto valore, puoi coinvolgerlo per il massimo risultato. Ad esempio, se sei un&#39;azienda Business to Business, puoi avere dei lead di chiamata di vendita che ti consentono di valutare i lead e identificarne la probabilità di conversione offline. Poiché ogni lead aumenta i costi, la creazione di un incentivo per identificare potenziali clienti con la massima probabilità di conversione di una vendita rappresenta il modo più efficace e meno costoso per concentrare le tue risorse.

Il punteggio tendenza ti consente di identificare i fattori più predittivi di un punteggio particolare o di aumentare la probabilità che si verifichi un evento, ma può anche essere applicato per rispondere a domande specifiche: Il cliente arriverà alla conversione? Il cliente risponderà a un’e-mail? Il cliente riacquisterà? Il punteggio tendenza consente di rispondere a tutte queste domande, identificando i visitatori inclini all’azione che possono essere impostati e valutati.

Inoltre, puoi utilizzare i filtri per definire un sottoinsieme di visitatori da assegnare al punteggio utilizzando la funzione opzionale **[!UICONTROL Training Filter]** . Se non viene applicato alcun filtro, il punteggio verrà assegnato a tutti i visitatori.

## Funzionalità della visualizzazione Punteggio tendenza {#section-28413bc7d33b42c59cecb427c1c5a3fa}

Per aprire la visualizzazione Punteggio tendenza, fai clic su **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

![](assets/propensity_visualization_GO.png)

La visualizzazione Propensity Scoring (Punteggio tendenza) include le seguenti funzioni accessibili dalla relativa barra degli strumenti:

| Funzione Barra degli strumenti | Descrizione |
|---|---|
| Vai | Fai clic su per eseguire il processo di punteggio dopo aver impostato i parametri. |
| Ripristino | Cancella tutte le impostazioni nella visualizzazione. |
| Load | Carica un ScoreDim creato in precedenza che consente di modificare e/o ricreare il modello di punteggio. |
| Salva | Salva la visualizzazione con punteggio tendenza come file Dim da accedere e aprire in base alle esigenze. |
| Submit | Invia un’attività di punteggio per l’elaborazione sul lato server. |
| Opzioni | Imposta il filtro di formazione per limitare il sottoinsieme di visitatori. Il filtro predefinito è **[!UICONTROL Train on Everyone]**, ma è possibile modificarlo effettuando selezioni dell&#39;area di lavoro o creando un filtro utilizzando **[!UICONTROL Filter Editor]**. |
| Impostare Target | Imposta la variabile dipendente. |
| Metrica | Aggiungi metriche come variabili indipendenti. |
| Elementi | Trascina gli elementi di Dimension utilizzando i tasti `<Ctrl>` + `<Alt>` dalle tabelle dei Dimension. |

**Vedi anche**:

* I [grafici ad incremento e guadagno](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a). Queste visualizzazioni possono essere aperte da un modello di punteggio completo o da [!DNL Add Visualization> Predictive Analytics > Scoring.]
* Il [Visualizzatore modelli](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd). Queste visualizzazioni possono essere aperte da un modello di punteggio completo o da [!DNL Add Visualization> Predictive Analytics > Scoring.]
* La funzione [Descrizione filtro complesso](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff).

## Utilizzo della visualizzazione Punteggio tendenza {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **Definisci uno o più filtri per definire la popolazione dei visitatori per il punteggio**. Questa opzione opzionale **[!UICONTROL Training Filter]** consente di eseguire il targeting dei visitatori in base ai criteri selezionati. Se non viene applicato alcun filtro di formazione, tutti i visitatori vengono selezionati per il punteggio. Se il filtro di formazione è impostato, il risultato del punteggio è significativo per la popolazione di visitatori definita, anche se a ogni visitatore verrà comunque assegnato un punteggio.
* **Identifica i visitatori** positivi. Per definire la variabile dipendente per specificare un filtro target che identifichi i visitatori positivi che corrispondono al risultato desiderato. Può essere semplice come Revenue > $10 o un filtro molto più complesso.
* **Il filtro Target non può essere uguale al filtro** Training. Logicamente, il filtro di Target deve essere un’aggiunta al filtro di formazione, dando luogo a un sottoinsieme positivo della popolazione del visitatore da valutare.
* **Seleziona le variabili di interesse (variabili indipendenti) come input per l’algoritmo** Punteggio tendenza. Possono essere metriche o singoli elementi di un Dimension. Il Punteggio tendenza inizierà la preelaborazione come in [Clustering visitatore](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d). Il sistema inizia a catturare una certa quantità di campioni che corrispondono alla definizione del filtro di formazione precedentemente impostato (se presente). Attualmente, la dimensione del campione è impostata come 10% della popolazione del punteggio (definita dal filtro di formazione), con un minimo di 20.000 e un massimo di 100.000, ed è associata alla dimensione della popolazione del punteggio.

* Un Dimension Punteggio ha elementi compresi tra lo 0% e il 100% che determinano la probabilità che i visitatori corrispondano alla variabile Target.
