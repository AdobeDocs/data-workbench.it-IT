---
description: Le note sulla versione di Data Workbench 6.1 includono nuove funzioni, requisiti di aggiornamento, correzioni di bug e problemi noti.
title: Note sulla versione di Data Workbench 6.1
uuid: 5bfb558a-ce85-4b4a-95dc-ccef337c4d1b
exl-id: ed37a00f-b4cd-428e-abb7-7c52d5cfd2f9
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 2%

---

# Note sulla versione di Data Workbench 6.1{#data-workbench-release-notes}

Le note sulla versione di Data Workbench 6.1 includono nuove funzioni, requisiti di aggiornamento, correzioni di bug e problemi noti.

## Nuove funzionalità {#section-1225066ea8f44cf68e42e019d0bca816}

La Data Workbench 6.1 include le seguenti nuove funzioni:

| Funzioni | Descrizione |
|--- |--- |
| Aggiornamento di Windows a 64 bit | I componenti server, server di report e client di Data Workbench vengono aggiornati in modo da essere eseguiti solo su sistemi operativi Windows a 64 bit. |
| Punteggio tendenza | Il punteggio del pubblico ti consente di identificare la fidelizzazione del cliente e di percepire statisticamente chi è in grado di convertire una vendita o interagire con una storia o una campagna. Il punteggio tendenza ora include queste visualizzazioni per visualizzare i modelli e mostrare la modifica della correlazione delle metriche selezionate.<ul><li>Il Visualizzatore modelli esamina un modello di regressione logistica generato con Propensity Scoring (Punteggio tendenza), mostrando i pesi del coefficiente di ciascuna variabile di input (compreso il termine costante) e il relativo intervallo di errori statistici. </li><li>I grafici Incremento e Guadagno vengono utilizzati per valutare il potenziale aumento di un modello dati con punteggio.</li><li>La matrice di confusione fornisce quattro conteggi per combinazione di Positivo Effettivo (AP), Negativo Effettivo (AN), Positivo Previsto (PP) e Negativo Predetto (PN).</li> <li>A partire dalla versione v6.1, ora è disponibile un’opzione Salva per salvare i punteggi di propensione in base a due tipi: dimensioni o dimensioni e metriche.</li><li>Ora puoi fare clic su Ctrl+Alt e trascinare per aggiungere elementi nel Punteggio tendenza e nel Generatore di cluster. In precedenza, per aggiungere elementi di tabella, era necessario trascinare dalla tabella alla casella Elementi.</li></ul> |
| Data Workbench ora in cinese | Data Workbench ora supporta il cinese semplificato per l’applicazione client. Data Workbench supporta inoltre Input Method Editor (IME) come processo di immissione di testo secondario per le lingue internazionali. |
| Funzioni matematiche | È ora possibile aggiungere funzioni matematiche alle metriche, alle trasformazioni matematiche e alle celle del foglio di lavoro per calcolare ulteriormente i set di dati. |
| Callout statistici | Le tabelle ora offrono una chiamata di riepilogo delle statistiche per le colonne di metrica. Il call-out può visualizzare la media, la deviazione standard, i valori minimo e massimo, la varianza e il conteggio totale per la colonna. Può essere preso in considerazione in qualsiasi selezione e valutazione. |
| Filtro matrice di correlazione | La matrice di correlazione è stata aggiornata con un filtro binario per consentirti di vincolare i valori per una o entrambe le metriche correlate, in modo da rendere più mirato il confronto. Inoltre, è ora possibile aggiungere elementi di Dimension da una tabella di Dimension facendo clic su Ctrl + Alt e trascinando gli elementi nella colonna o nella riga della matrice da valutare. |
| Nascondere l’etichetta Abbandono nella visualizzazione funnel | Per passare dalla visualizzazione e nascondere le etichette di abbandono in una visualizzazione Funnel, fai clic con il pulsante destro del mouse sul titolo e seleziona Nascondi abbandono. |

## Ordinamento colonne tabella{#sorting-table-columns}

Ordina le colonne della tabella in ordine alfabetico o ordinale.

Per selezionare meglio gli elementi di una tabella di Dimension, è possibile ordinare alfabeticamente la prima colonna o ordinando gli ordinali selezionando l’opzione di menu **[!UICONTROL Sort]**.

Il carattere # viene visualizzato quando una colonna viene ordinata per ordinali (impostazione predefinita).

**Seleziona opzione di ordinamento**

Per modificare le opzioni di ordinamento tra ordinale e alfabeto, fare clic con il pulsante destro del mouse e selezionare **[!UICONTROL Sort]**. Fai clic sulla freccia per invertire l’ordine.

![](assets/sort_table_alpha.png)

>[!NOTE]
>
>Per ordinare le altre colonne in base al numero ordinale, fai clic sul nome della colonna.

## Nascondere le etichette di abbandono nell&#39;imbuto

Consente di aprire le etichette di abbandono in una visualizzazione Funnel.

La visualizzazione funnel indica dove un cliente abbandona una campagna di marketing o devia da un percorso di conversione definito durante l’interazione con il sito web o una campagna su più canali. Il lato sinistro della visualizzazione Funnel mostra i risultati di una visita o dei visitatori, mentre il lato destro mostra l’abbandono di un percorso specifico da parte di coloro che abbandonano un percorso specifico.

![](assets/c_funnel_hide_fallout.png)

In una visualizzazione **[!UICONTROL Funnel]**, puoi fare clic con il pulsante destro del mouse sul titolo e selezionare **[!UICONTROL Hide Fallout]** dal menu per nascondere le etichette di abbandono.

## Problemi noti {#section-ff2180c6871c413480e15fa915c253b9}

* Durante l’importazione di un’area di lavoro, viene visualizzato un messaggio di errore anche se l’importazione è riuscita.

   Soluzione: Fare clic su OK per ignorare l&#39;errore. Importazione dell&#39;area di lavoro completata.

**Problemi di localizzazione semplificata in cinese**

* Il titolo e il messaggio della finestra di dialogo visualizzato dopo aver fatto clic su &quot;Invia&quot; quando si imposta il target nella visualizzazione Punteggio sono illeggibili.

   Soluzione: Nessuno.
* Quando si utilizza il ritorno a capo automatico nella visualizzazione Foglio di lavoro, le parole localizzate non vengono racchiuse correttamente. Alla stringa vengono aggiunti caratteri spazzatura supplementari.

   Soluzione: Nessuno
* Impossibile avviare [!DNL Insight.exe] se la directory di installazione è denominata con caratteri non inglesi.

   Soluzione: Mantieni nomi predefiniti o rinomina utilizzando solo caratteri inglesi nel percorso della cartella per avviare eseguibili.
