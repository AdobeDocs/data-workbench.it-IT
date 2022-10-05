---
description: Le metriche, le dimensioni e i filtri forniscono un framework all’interno del quale vengono effettuati i calcoli sui dati elaborati in un set di dati di Data Workbench.
title: Data Workbench metriche, Dimension e filtri
uuid: 3c0300a0-ae19-4817-aab8-7294e0eabdd9
exl-id: 687d9695-e70c-49ff-ac11-1537e6309e16
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '796'
ht-degree: 0%

---

# Data Workbench metriche, Dimension e filtri{#data-workbench-metrics-dimensions-and-filters}

{{eol}}

Le metriche, le dimensioni e i filtri forniscono un framework all’interno del quale vengono effettuati i calcoli sui dati elaborati in un set di dati di Data Workbench.

I risultati dei calcoli definiti utilizzando questo framework vengono visualizzati in aree di lavoro, dashboard, rapporti o altri output. In breve, qualsiasi numero visualizzato in o da un&#39;applicazione è il risultato di una query di un set di dati che coinvolge una metrica, una dimensione e un filtro.

Al livello più semplice, una metrica descrive cosa viene calcolato dal set di dati e relativo, una dimensione suddivide i dati nel set di dati in categorie e un filtro descrive una porzione o un sottoinsieme selezionato di dati nel set di dati.

Quando Data Workbench Server elabora i dati per creare un set di dati, le dimensioni dei dati vengono create e quindi aggiornate su base continuativa man mano che i nuovi dati vengono letti ed elaborati dal server. Le metriche e i filtri vengono calcolati a partire da queste dimensioni di dati.

>[!CAUTION]
>
>Se ridefinisci una metrica interna, il sistema si comporta in modo imprevisto a causa del valore errato. I rapporti non verranno generati a meno che una metrica non legga il 100%. È consigliabile non modificare le definizioni delle metriche.

## Esempio {#section-ecc465d1a5e34d559c1983e96fa409ec}

Immaginate un set di dati che contiene informazioni su tutte le persone nel mondo. Questo insieme di dati contiene, almeno, tutte le persone del mondo e delle loro età. Una metrica utile da calcolare da questo set di dati sarebbe Età media. La valutazione di questa metrica comporterebbe un numero: l’età media della popolazione mondiale.

L’aggiunta di una dimensione al set di dati rende queste informazioni più utili e gestibili. Se il set di dati contiene anche il paese di residenza di ogni persona, la definizione di una dimensione Paese consentirebbe di segmentare le persone in gruppi per ogni paese del mondo. La valutazione della metrica Età media sulla dimensione Paese comporterebbe un elenco di numeri, uno per ciascun paese, ciascuno dei quali rappresenta l’età media delle persone in quel paese.

L’applicazione di un filtro (o filtro di selezione) in una formula metrica può fornire informazioni più dettagliate o consentire la definizione di una nuova metrica basata su metriche e dimensioni esistenti. La valutazione della metrica Età media con un filtro &quot;dove paese è uguale a Svezia&quot; restituisce un numero: l&#39;età media delle persone in Svezia. Una metrica basata su questo filtro potrebbe essere Età media svedese.

Esempio:

```
Swedish_Average_Age=Average_Age[country = ‘Sweden’]
```

## Modalità di relazione tra metriche, Dimension e filtri {#section-28622596124140b280e6b993b174ef84}

In generale, la valutazione di una metrica su una dimensione fa sì che la metrica venga valutata per ogni elemento (o elemento) di dimensione. Nell’esempio precedente, la dimensione Paese presenta un elemento per ogni paese del mondo. La valutazione dell&#39;età media per paese produrrebbe l&#39;età media per ciascuno degli elementi (paesi), compreso l&#39;elemento Svezia.

È importante notare che quando valuti una metrica su una dimensione, riceverai lo stesso risultato numerico per un elemento dimensione specifico, indipendentemente dal fatto che la valuti per l’intera dimensione o che definisca un filtro corrispondente a tale elemento dimensione specifico. Utilizzando l&#39;esempio precedente, quando si cerca l&#39;età media delle persone in Svezia, uno dei seguenti metodi produrrebbe risultati identici:

* Valuta la metrica Età media sulla dimensione Paese, quindi osserva il numero per l’elemento dimensione Svezia.
* Valutare la metrica dell’età media con un filtro &quot;persone in Svezia&quot; (espresso come [!DNL Average_Age[Country='Sweden']]).

I filtri sono espressioni tattiche che fanno riferimento a una o più dimensioni ed elementi dimensionali. Come mostrato nell’esempio precedente, utilizzando l’espressione [!DNL [dimension=element]] è un modo semplice per specificare un filtro.

È altrettanto semplice applicare un filtro di questo tipo per definire una nuova metrica utilizzando un’espressione come [!DNL New_Metric=Metric[Filter]]. Tale filtro può essere utilizzato per definire una nuova metrica basata su un elemento dimensione specifico. Per utilizzare l&#39;esempio precedente: [!DNL Average_Age[Country='Sweden']]specifica una metrica per l’età media delle persone in Svezia. Se dovessimo assegnare un nome a questa metrica, ad esempio Svedese_Average_Age, potremmo usarla in altri calcoli come metrica. Ad esempio, la valutazione [!DNL Swedish_Average_Age/Average_Age] risulterebbe in un singolo numero: il rapporto tra l&#39;età media delle persone in Svezia e quella delle persone nel resto del mondo.

Se il set di dati con informazioni su tutte le persone nel mondo include anche una dimensione Colore occhi, l&#39;espressione [!DNL Swedish_Average_Age[Eye_Color='green']] risulterebbe nell&#39;età media degli svedesi con occhi verdi. Puoi anche ottenere lo stesso risultato senza utilizzare una definizione di metrica intermedia applicando un filtro diverso: [!DNL Average_Age[Country='Sweden' AND Eye_Color='green']]. In questo caso, il [!DNL AND] operatore specifica un&#39;espressione di filtro utilizzando altre due espressioni di filtro di base.
