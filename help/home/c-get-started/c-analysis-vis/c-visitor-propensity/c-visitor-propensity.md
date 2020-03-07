---
description: Il punteggio tendenza consente di definire i clienti in base alla loro possibilità di conversione o completamento di un evento specificato. Consente di massimizzare l'impatto potenziale delle attività prima di eseguire un processo o di indirizzare una campagna.
solution: Analytics
title: Punteggio tendenza
topic: Data workbench
uuid: 4f7163f5-6fe4-4f87-9e27-71ec8b4717af
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Punteggio tendenza{#propensity-scoring}

Il punteggio tendenza consente di definire i clienti in base alla loro possibilità di conversione o completamento di un evento specificato. Consente di massimizzare l&#39;impatto potenziale delle attività prima di eseguire un processo o di indirizzare una campagna.

## Valore del punteggio tendenza {#section-c51ece66effc42de9b754f0f46027c1b}

Il punteggio tendenza consente di eseguire l&#39;individuazione dei dati per identificare comportamenti o pattern nascosti esistenti nei dati. In particolare, il punteggio di propensione ti aiuta a identificare cluster di clienti simili utilizzando metodi più focalizzati e obiettivi al posto dei semplici filtri o segmentazione. Inoltre, il punteggio di propensione ti consente di impostare funzionalità predittive per identificare il comportamento per il cliente di alto valore della tua società.

Una volta identificato il pubblico di alto valore, puoi coinvolgerlo per il massimo risultato. Ad esempio, se sei un&#39;azienda Business to Business, puoi avere dei lead di vendita che ti permettono di valutare i lead e identificarne la probabilità di conversione offline. Poiché ogni lead aumenta i costi, la creazione di un incentivo per identificare potenziali clienti con la massima probabilità di conversione di una vendita è il metodo più efficace e conveniente per focalizzare le risorse.

L&#39;assegnazione di un punteggio di probabilità permette di identificare i fattori più predittivi di un punteggio specifico o di aumentare la probabilità del verifciarsi di un evento, ma anche di rispondere a domande specifiche. Il cliente eseguirà la conversione? Il cliente risponderà a un&#39;e-mail? Il cliente eseguirà di nuovo l&#39;acquisto? Il punteggio tendenza consente di rispondere a queste domande e di identificare i visitatori con un&#39;inclinazione all&#39;azione che potrà essere impostata e valutata.

Inoltre, potete utilizzare i filtri per definire un sottoinsieme di visitatori ai quali assegnare un punteggio utilizzando la **[!UICONTROL Training Filter]** funzione opzionale. Se non viene applicato alcun filtro, tutti i visitatori vengono assegnati al punteggio.

## Funzionalità della visualizzazione Propensity Scoring (Punteggio tendenza) {#section-28413bc7d33b42c59cecb427c1c5a3fa}

Per aprire la visualizzazione Propensity Scoring (Punteggio tendenza), fate clic su **[!UICONTROL Add]** > **[!UICONTROL Visualization]** > **[!UICONTROL Predictive Analytics]** > **[!UICONTROL Scoring]** > **[!UICONTROL Propensity Score]**.

![](assets/propensity_visualization_GO.png)

La visualizzazione Propensity Scoring (Punteggio tendenza) include le seguenti funzionalità accessibili dalla barra degli strumenti:

| Funzione della barra degli strumenti | Descrizione |
|---|---|
| Go | Fare clic per eseguire il processo di punteggio dopo aver impostato i parametri. |
| Reset | Cancella tutte le impostazioni della visualizzazione. |
| Caricamento | Carica un oggetto ScoreDim creato in precedenza che consente di modificare e/o ricreare il modello di punteggio. |
| Salva | Salvate la visualizzazione Propensity Scoring (Punteggio tendenza) come file Dim a cui potete accedere e che potete aprire in base alle vostre esigenze. |
| Invia | Invia l’attività di punteggio per l’elaborazione sul lato server. |
| Opzioni | Impostate il Filtro formazione per limitare il sottoinsieme di visitatori. Il filtro predefinito è **[!UICONTROL Train on Everyone]** ma potete modificarlo effettuando selezioni dell’area di lavoro o creando un filtro utilizzando l’icona **[!UICONTROL Filter Editor]**. |
| Imposta destinazione | Impostare la variabile dipendente. |
| Metrica | Aggiungi metriche come variabili indipendenti. |
| Elementi | Trascina gli elementi Dimensione utilizzando i tasti `<Ctrl>` + `<Alt>` dalle tabelle Dimensioni. |

**Vedi anche**:

* I grafici [Guadagno e Lift](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-gain-lift-chart.md#concept-0d049f6baf534f7fb97f271843ba6c4a). Queste viste possono essere aperte da un modello di punteggio completo o da [!DNL Add Visualization> Predictive Analytics > Scoring.]
* Visualizzatore [](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-model-viewer.md#concept-d4fdf4b335c04b0ea07e70ab9a7ce9dd)modelli. Queste viste possono essere aperte da un modello di punteggio completo o da [!DNL Add Visualization> Predictive Analytics > Scoring.]
* Descrizione [filtro](../../../../home/c-get-started/c-analysis-vis/c-visitor-propensity/c-propensity-complex-filter.md#concept-f9c55e54837f4b5995a00bc950ce5dff) complesso.

## Utilizzo della visualizzazione Propensity Scoring (Punteggio tendenza) {#section-63ced03fa2eb44f2b8a98d61a6c88122}

* **Definite uno o più filtri per definire la popolazione di visitatori per il punteggio**. Questa opzione **[!UICONTROL Training Filter]** consente di eseguire il targeting dei visitatori in base a criteri selezionati. Se non viene applicato alcun filtro di formazione, tutti i visitatori vengono assegnati al punteggio. Se è impostato il Filtro formazione, il risultato del punteggio è significativo per la popolazione di visitatori definita, anche se a ogni visitatore sarà comunque assegnato un punteggio.
* **Identificare i visitatori** positivi. Per definire la variabile dipendente per specificare un filtro di destinazione che identifichi i visitatori positivi che corrispondono al risultato desiderato. Può trattarsi di un filtro semplice come Revenue (Entrate) > $10, o molto più complesso.
* **Il filtro Target non può essere uguale al filtro** Formazione. Logicamente, il filtro di destinazione deve essere un&#39;aggiunta al filtro formazione, dando luogo a un sottoinsieme positivo della popolazione di visitatori da sottoporre a valutazione.
* **Selezionate le variabili di interesse (variabili indipendenti) come input per l’algoritmo** Propensity Scoring (Punteggio tendenza). Può trattarsi di Metriche o di singoli elementi di una Dimensione. Il punteggio tendenza avvia la preelaborazione come nel [cluster](../../../../home/c-get-started/c-analysis-vis/c-visitor-cluster/c-visitor-cluster.md#concept-1c2406ef7b284a56a02daa38eaa2e73d)di visitatori. Il sistema inizia a catturare una certa quantità di campioni che corrispondono alla definizione del filtro di formazione precedentemente impostato (se presente). Attualmente, la dimensione del campione è impostata sul 10% della popolazione del punteggio (definita dal filtro di formazione), con un minimo di 20.000 e un massimo di 100.000, ed è associata alla dimensione della popolazione del punteggio.

* Una Dimensione punteggio presenta elementi compresi tra 0% e 100% che determinano la probabilità che i visitatori corrispondano alla variabile Target.

