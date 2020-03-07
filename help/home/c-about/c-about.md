---
description: Metriche, dimensioni e filtri forniscono un framework all'interno del quale vengono eseguiti i calcoli relativi ai dati elaborati in un dataset workbench dati.
solution: Analytics
title: Metriche, dimensioni e filtri di Workbench dati
topic: Data workbench
uuid: 3c0300a0-ae19-4817-aab8-7294e0eabdd9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Metriche, dimensioni e filtri di Workbench dati{#data-workbench-metrics-dimensions-and-filters}

Metriche, dimensioni e filtri forniscono un framework all&#39;interno del quale vengono eseguiti i calcoli relativi ai dati elaborati in un dataset workbench dati.

I risultati dei calcoli definiti con questo framework sono visualizzati in aree di lavoro, dashboard, rapporti o altri output. In breve, qualsiasi numero visualizzato in o da un&#39;applicazione è il risultato di una query di un set di dati che include una metrica, una dimensione e un filtro.

Al livello più basilare, una metrica descrive ciò che viene calcolato dal e sul set di dati, una dimensione suddivide i dati nel set di dati in categorie e un filtro descrive una porzione o un sottoinsieme selezionato di dati nel set di dati.

Quando il server Workbench dati elabora i dati per creare un dataset, le dimensioni dei dati vengono create e quindi aggiornate su base continuativa man mano che i nuovi dati vengono letti ed elaborati dal server. Metriche e filtri sono calcolati a partire da queste dimensioni di dati.

>[!CAUTION]
>
>Se si ridefinisce una metrica interna, il sistema si comporta in modo imprevisto a causa del valore errato. I rapporti non verranno generati a meno che una metrica non legga il 100%. È consigliabile non modificare le definizioni delle metriche.

## Esempio {#section-ecc465d1a5e34d559c1983e96fa409ec}

Immaginate un set di dati che contiene informazioni su tutte le persone del mondo. Questa serie di dati contiene, almeno, tutte le persone del mondo e delle loro età. Una metrica utile da calcolare da questo set di dati sarebbe Età media. La valutazione di questa metrica comporterebbe un numero: l’età media della popolazione mondiale.

L&#39;aggiunta di una dimensione al dataset rende queste informazioni più utili e gestibili. Se l’insieme di dati contiene anche il paese di residenza di ogni persona, la definizione di una dimensione Paese potrebbe fornire un modo per segmentare le persone in gruppi per ogni paese del mondo. La valutazione della metrica Età media sulla dimensione Paese comporterebbe un elenco di numeri, uno per ciascun paese, ognuno dei quali rappresenta l&#39;età media delle persone in quel paese.

L&#39;applicazione di un filtro (o filtro di selezione) in una formula metrica può fornire informazioni più dettagliate o consentire la definizione di una nuova metrica in base alle metriche e dimensioni esistenti. La valutazione della metrica Età media con un filtro &quot;dove paese è uguale alla Svezia&quot; restituisce un numero: l&#39;età media delle persone in Svezia. Una metrica basata su questo filtro potrebbe essere Età media svedese.

Ad esempio:

```
Swedish_Average_Age=Average_Age[country = ‘Sweden’]
```

## Modalità di relazione tra metriche, dimensioni e filtri {#section-28622596124140b280e6b993b174ef84}

In generale, la valutazione di una metrica su una dimensione determina la valutazione di tale metrica per ciascun elemento dimensione (o elemento). Nell&#39;esempio precedente, la dimensione Paese ha un elemento per ciascun paese del mondo. La valutazione dell&#39;età media rispetto al paese produrrebbe l&#39;età media per ciascuno degli elementi (paesi), compreso l&#39;elemento Svezia.

È importante notare che quando si valuta una metrica su una dimensione, si riceverà lo stesso risultato numerico per un elemento dimensione specifico, indipendentemente dal fatto che si valuti la metrica per l&#39;intera dimensione o che si definisca un filtro corrispondente a tale elemento dimensione specifico. Utilizzando l&#39;esempio precedente, quando si cerca l&#39;età media delle persone in Svezia, uno dei seguenti metodi darebbe risultati identici:

* Valutare la metrica Età media sulla dimensione Paese, quindi vedere il numero per l&#39;elemento dimensione Svezia.
* Valutare la metrica Età media con un filtro di &quot;persone in Svezia&quot; (espresso come [!DNL Average_[AgeCountry=&#39;Svezia&#39;]]).

I filtri sono espressioni sintattiche che fanno riferimento a una o più dimensioni ed elementi dimensionali. Come illustrato nell&#39;esempio precedente, l&#39;utilizzo dell&#39;espressione [!DNL [Dimension=element]] è un modo semplice per specificare un filtro.

È altrettanto semplice applicare un filtro di questo tipo per definire una nuova metrica utilizzando un&#39;espressione come [!DNL New_Metric=[MetricFilter]]. Tale filtro può essere utilizzato per definire una nuova metrica basata su un elemento dimensione specifico. Per utilizzare l&#39;esempio precedente, [!DNL Average_[AgeCountry=&#39;Sweden&#39;]] specifica una metrica per l&#39;età media delle persone in Svezia. Se dovessimo assegnare a questa metrica un nome, come Svedese_Average_Age, potremmo usarla in altri calcoli come metrica. Ad esempio, la valutazione [!DNL Swedish_Average_Age/Average_Age] comporterebbe un singolo numero: il rapporto tra l&#39;età media delle persone in Svezia e quella delle persone nel resto del mondo.

Se il set di dati con informazioni su tutte le persone nel mondo include anche una dimensione Colore occhio, l&#39;espressione [!DNL Svedese_Average_[AgeEye_Color=&#39;green&#39;]] risulterebbe nell&#39;età media degli svedesi con occhi verdi. È inoltre possibile ottenere lo stesso risultato senza utilizzare una definizione di metrica intermedia applicando un filtro diverso: [!DNL Average_[AgeCountry=&#39;Sweden&#39; AND Eye_Color=&#39;green&#39;]]. In questo caso, l&#39; [!DNL AND] operatore specifica un&#39;espressione di filtro utilizzando altre due espressioni di filtro di base.
