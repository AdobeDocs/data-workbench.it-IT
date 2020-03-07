---
description: Le note sulla versione di Workbench dati 6.1 includono nuove funzioni, requisiti per l'aggiornamento, correzioni di bug e problemi noti.
solution: Analytics
title: Note sulla versione di Workbench dati 6.1
topic: Data workbench
uuid: 5bfb558a-ce85-4b4a-95dc-ccef337c4d1b
translation-type: tm+mt
source-git-commit: 2cba66a160fec9154796f093d04a422a5b0da265

---


# Data Workbench 6.1 Release Notes{#data-workbench-release-notes}

Le note sulla versione di Workbench dati 6.1 includono nuove funzioni, requisiti per l&#39;aggiornamento, correzioni di bug e problemi noti.

## Nuove funzionalità {#section-1225066ea8f44cf68e42e019d0bca816}

Workbench dati 6.1 include le seguenti nuove funzioni:

| Funzioni  | Descrizione |
|--- |--- |
| Aggiornamento Windows a 64 bit | I componenti server workbench dati, server di report e client vengono aggiornati per essere eseguiti solo su sistemi operativi Windows a 64 bit. |
| Punteggio tendenza | Puntando il tuo pubblico puoi identificare la fidelizzazione del cliente e percepire statisticamente chi probabilmente converte una vendita o interagisce con una storia o una campagna. Il punteggio tendenza ora include queste visualizzazioni per visualizzare i modelli e mostrare la correlazione variabile delle metriche selezionate.<ul><li>Il Visualizzatore modelli esamina un modello di regressione logistica generato con Propensity Scoring (Punteggio tendenza), mostrando i pesi di coefficiente di ciascuna variabile di input (incluso il termine costante) e il relativo intervallo di errore statistico. </li><li>I grafici Solleva e Guadagno sono utilizzati per valutare il potenziale aumento di un modello dati con punteggio.</li><li>La matrice Confusione fornisce quattro conteggi per combinazione di Effettivo positivo (AP), Negativo effettivo (AN), Predicato positivo (PP) e Predicato negativo (PN).</li> <li>A partire da v6.1, ora è disponibile un&#39;opzione Salva per salvare i punteggi di propensione in base a due tipi: dimensioni o dimensioni e metriche.</li><li>Ora puoi fare clic su Ctrl+Alt e trascinare per aggiungere elementi in Propensity Scoring (Punteggio tendenza) e in Cluster Builder (Generatore cluster). Precedentemente per aggiungere elementi di tabella, era necessario trascinare dalla tabella alla casella Elementi.</li></ul> |
| Workbench dati ora in cinese | Workbench dati ora supporta il cinese semplificato per l&#39;applicazione client. Workbench dati supporta anche l&#39;IME (Input Method Editor) come processo di immissione di testo secondario per le lingue internazionali. |
| Funzioni matematiche | È ora possibile aggiungere funzioni matematiche alle metriche, alle trasformazioni matematiche e alle celle del foglio di lavoro per calcolare ulteriormente i set di dati. |
| Callout statistici | Le tabelle ora offrono una chiamata di riepilogo delle statistiche per le colonne delle metriche. Il call-out può visualizzare la media, la deviazione standard, i valori minimo e massimo, la varianza e il conteggio totale della colonna. Può essere preso in considerazione per qualsiasi selezione e valutazione. |
| Filtro matrice di correlazione | La matrice di correlazione è stata aggiornata con un filtro binario per limitare i valori di una o entrambe le metriche correlate, consentendo di mettere a fuoco meglio il confronto. È inoltre possibile aggiungere elementi Dimensione da una tabella Dimensione facendo clic su Ctrl + Alt e trascinando gli elementi nella colonna o riga della matrice da valutare. |
| Nascondi etichetta Abbandono nella visualizzazione funnel | Per alternare tra la visualizzazione e l’eliminazione delle etichette di abbandono in una visualizzazione Funnel, fai clic con il pulsante destro del mouse sul titolo e seleziona Nascondi abbandono. |

## Ordinamento colonne tabella{#sorting-table-columns}

Ordinare le colonne di una tabella in ordine alfabetico o per ordinali.

Per selezionare meglio gli elementi in una tabella Dimensioni, è possibile ordinare la prima colonna in ordine alfabetico o ordinali selezionando l&#39;opzione di **[!UICONTROL Sort]** menu.

Il carattere # viene visualizzato quando una colonna viene ordinata per ordinali (impostazione predefinita).

**Seleziona opzione di ordinamento**

Per modificare le opzioni di ordinamento tra ordinale e alfabeto, fare clic con il pulsante destro del mouse e selezionare **[!UICONTROL Sort]**. Fate clic sulla freccia per invertire l’ordine.

![](assets/sort_table_alpha.png)

>[!NOTE]
>
>Per ordinare le altre colonne in modo ordinale, fare clic sul nome della colonna.

## Nascondi etichette di fallout nel funnel

Consente di aprire le etichette di abbandono in una visualizzazione Funnel.

La visualizzazione Funnel identifica il punto in cui un cliente abbandona una campagna di marketing o si allontana da un percorso di conversione definito durante l&#39;interazione con il sito Web o una campagna su più canali. Il lato sinistro della visualizzazione Funnel visualizza i risultati di una visita o dei visitatori, mentre il lato destro mostra il &quot;Abbandono&quot; di coloro che abbandonano un percorso specificato.

![](assets/c_funnel_hide_fallout.png)

In una **[!UICONTROL Funnel]** visualizzazione, puoi fare clic con il pulsante destro del mouse sul titolo e scegliere **[!UICONTROL Hide Fallout]** dal menu per nascondere le etichette di abbandono.

## Problemi noti {#section-ff2180c6871c413480e15fa915c253b9}

* Durante l’importazione di un’area di lavoro, viene visualizzato un messaggio di errore anche se l’importazione è avvenuta correttamente.

   Soluzione: Fate clic su OK per ignorare l&#39;errore. L&#39;area di lavoro viene importata correttamente.

**Problemi Di Localizzazione Cinese Semplificati**

* Il titolo e il messaggio della finestra di dialogo visualizzati dopo aver fatto clic su &quot;Invia&quot; quando si imposta la destinazione nella visualizzazione Punteggio sono illeggibili.

   Soluzione: Nessuno.
* Quando si utilizza il ritorno a capo automatico nella visualizzazione Foglio di lavoro, le parole localizzate non vengono racchiuse correttamente. Alla stringa vengono aggiunti ulteriori caratteri indesiderati.

   Soluzione: None
* Impossibile avviare [!DNL Insight.exe] se la directory di installazione è denominata con caratteri non inglesi.

   Soluzione: Mantenete i nomi predefiniti o rinominate utilizzando solo i caratteri inglesi nel percorso della cartella per avviare i file eseguibili.
