---
description: In questa sezione viene illustrato lo script Saint Scrubber.
title: Scripting per lo scorrimento SAINT
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Scripting per lo scorrimento SAINT{#scripting-for-the-saint-scrubber}

In questa sezione viene illustrato lo script Saint Scrubber.

## Panoramica della classificazione SAINT {#section-b840a99f10684bb4b58e844a515d0d79}

La classificazione è nota anche dall&#39;acronimo SAINT per lo strumento SiteCatalyst per l&#39;importazione e la denominazione di attributi.

Quando si &quot;classifica&quot; una variabile di SiteCatalyst, viene stabilita una relazione tra una variabile e i metadati correlati a tale variabile. Le classificazioni vengono utilizzate più di frequente nell&#39;area Campagne e quindi lo utilizzerò per spiegarle. La maggior parte dei client invia il traffico delle campagne al proprio sito utilizzando un codice di tracciamento. Questo codice di tracciamento è un identificatore che può rappresentare una parola chiave specifica acquistata su Google, ad esempio &quot;goog123&quot;. Questo identificatore viene passato nella variabile s.campaign in modo da poter vedere gli eventi di successo del sito che si verificano dopo che i visitatori arrivano sul sito dal codice della campagna.

Ma cosa succede se, invece di visualizzare le campagne solo in base al codice di tracciamento, si desidera visualizzare i risultati delle campagne in base al motore di ricerca o alla parola chiave o al canale della campagna? È necessario creare una nuova variabile di conversione per Motore di ricerca, un&#39;altra per Parola chiave e un&#39;altra per Canale campagna? In tal caso, potete utilizzare molte delle cinquanta variabili solo per Campagne! Per fortuna, puoi utilizzare le classificazioni per rendere la tua vita più facile! Poiché ogni codice di tracciamento può avere un motore di ricerca, una parola chiave o un canale di campagna, potete semplicemente creare tre classificazioni della variabile Campagne per rappresentarle. In sostanza state dicendo a SiteCatalyst che esiste una relazione diretta tra la variabile Campagne e questi tre altri valori &quot;meta-dati&quot;. Con questa operazione, SiteCatalyst consente di suddividere in sezioni ed eliminare eventi di successo del sito con tutte e quattro le variabili senza tag aggiuntivi.

## Script di scorrimento SAINT in DWB {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

Questo script viene utilizzato quando si inseriscono dati di classificazione SAINT in DWB. Lo script *SaintScrubber.dat* si trova normalmente nella cartella *\Scripts\Scripository* dell&#39;FSU.

Lo scopo principale di questo script è quello di rimuovere l&#39;intestazione nei file di classificazione `<discoiqbr>` SAINT. Inoltre, conteggia il numero se la colonna indicata nella riga di intestazione della colonna e controlla tutte le righe di dati. Se ci sono righe con un numero di colonne inferiore o superiore, le righe vengono rimosse dal file.

Lo script *SaintScrubber.dat* chiama internamente lo script *saint_scrubber.pl *. Di seguito sono riportati i dettagli per questo file di script:

Percorso: *E:\Scripts\Scripository\Library\Perl*

Argomenti script:

1. Cartella di input (obbligatoria): source_directory
1. Cartella di output (obbligatoria): directory_destinazione
1. Delimitatore (obbligatorio): delimiter
1. Rifiuta cartella (facoltativo)(il parametro può essere lasciato vuoto o omesso dalla riga di comando)
1. Cartella di registro (facoltativo) (il parametro può essere lasciato vuoto o omesso dalla riga di comando)

Passaggi eseguiti nello script Perl:

1. Sostituire feed di modulo con escape, linee nuove, ritorni a capo, tabulazioni con spazi.
1. Rimuovete i doppi byte che vengono interpretati come un carattere di controllo nel BMP UTF-8 (Piano multilingue di base) ad eccezione di:

   * 9 schede orizzontali
   * Alimentazione a 10 righe
   * 12 feed modulo
   * 13 ritorno a capo
   * Utilizzate la parola chiave pipe, come delimitatore per| ad esempio: tubo di delimitazione
   * Rimuovere altri caratteri problematici
   * Dopo il passaggio del mouse sopra, rilasciare qualsiasi riga con un numero di colonne diverso dalla prima riga di dati (non vuoto o commento)
   * Supportare i file di rifiuto facoltativi per mantenere le righe rifiutate invece di semplicemente ignorarle
   * Supportare la cartella di input ricorsiva; genera cartelle di output della stessa struttura
   * Spostare i file di input elaborati nelle sottocartelle elaborate in modo che lo script non ripeta lo sforzo quando viene eseguito nuovamente sulla stessa cartella di input esistente
   * riconoscere la data nei nomi dei file workbench; ordinate prima l&#39;elaborazione in base alla data e poi all&#39;alfa, indipendentemente dal nome della cartella. Questo garantisce che la sequenza sia corretta indipendentemente dal tipo di file workbench (ecom, non ecom) o dall&#39;ID suite di rapporti (se state elaborando più suite di rapporti in un unico set di dati Insight).
   * Avvisi e-mail di supporto `<discoiqbr>`

