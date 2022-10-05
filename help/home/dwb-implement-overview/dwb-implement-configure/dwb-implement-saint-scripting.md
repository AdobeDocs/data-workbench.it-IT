---
description: Questa sezione spiega lo script di Saint Scrubber.
title: Scripting per lo scorrimento SAINT
uuid: 2e5aa6f2-dadb-48a6-8443-69396530587c
exl-id: 5f6d92b1-baaa-4d67-a1c2-ce7d51affb17
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 1%

---

# Scripting per lo scorrimento SAINT{#scripting-for-the-saint-scrubber}

{{eol}}

Questa sezione spiega lo script di Saint Scrubber.

## Panoramica della classificazione SAINT {#section-b840a99f10684bb4b58e844a515d0d79}

La classificazione è nota anche dall’acronimo SAINT per lo strumento di importazione e denominazione degli attributi di SiteCatalyst .

Quando &quot;classifica&quot; una variabile di SiteCatalyst, stabilisci una relazione tra una variabile e metadati correlati a tale variabile. Le classificazioni vengono utilizzate più di frequente nell’area Campagne, per spiegarle con questo metodo. La maggior parte dei client invia il traffico della campagna al proprio sito utilizzando un codice di tracciamento. Questo codice di tracciamento è un identificatore che può rappresentare una parola chiave specifica acquistata su Google, ad esempio &quot;goog123&quot;. Questo identificatore viene passato nella variabile s.Campaigns per visualizzare gli eventi di successo del sito che si verificano dopo che i visitatori arrivano al tuo sito da quel codice della campagna.

Ma cosa succede se, invece di visualizzare le campagne solo tramite il codice di tracciamento, vuoi visualizzare i risultati delle campagne per motore di ricerca, parola chiave o canale della campagna? È necessario creare una nuova variabile di conversione per il motore di ricerca, un’altra per parola chiave e un’altra per il canale di campagna? In tal caso, utilizzerai molte delle tue cinquanta variabili solo su Campagne! Per fortuna, puoi utilizzare le classificazioni per semplificare la tua vita! Poiché ogni codice di tracciamento può avere un motore di ricerca, una parola chiave o un canale della campagna, puoi semplicemente creare tre classificazioni della variabile Campagne da rappresentare ciascuno. In sostanza stai dicendo al SiteCatalyst che esiste una relazione diretta tra la variabile Campagne e questi altri tre valori &quot;meta-dati&quot;. In questo modo, SiteCatalyst ti consentirà di suddividere gli eventi di successo del sito in base a tutte e quattro le variabili senza tag aggiuntivi.

## Script di scorrimento SAINT in DWB {#section-a42bb9236d7d49bfabdc48d39ece3c3b}

Questo script viene utilizzato quando si inseriscono dati di classificazione SAINT in DWB. Lo script *SaintScrubber.dat* è normalmente collocato sotto *\Script\Scripting* nella FSU.

Lo scopo principale di questo script è quello di rimuovere l’intestazione nel `<discoiqbr>` File di classificazione di SAINT. Inoltre, conta il numero se la colonna indicata nella riga di intestazione della colonna e controlla tutte le righe di dati. Se ci sono righe con un numero minore o maggiore di colonne, allora rimuove queste righe dal file.

La *SaintScrubber.dat* chiama internamente lo script *saint_scrubber.pl *. Di seguito sono riportati i dettagli di questo file di script:

Percorso: *E:\Scripts\Scripository\Library\Perl*

Argomenti script:

1. Cartella di input (obbligatoria): source_directory
1. Cartella di output (obbligatoria) : destination_directory
1. Delimitatore (obbligatorio) : delimitatore
1. Rifiuta cartella (facoltativo)(Il parametro può essere lasciato vuoto o omesso dalla riga di comando)
1. Cartella log (facoltativo)(Il parametro può essere lasciato vuoto o omesso dalla riga di comando)

Passaggi eseguiti nello script Perl:

1. Sostituire i feed di moduli con escape, le nuove righe, i ritorni a capo, le schede con gli spazi.
1. Rimuovere i byte doppi interpretati come carattere di controllo nel BMP UTF-8 (Piano multilingue di base) ad eccezione di:

   * 9 scheda orizzontale
   * 10 linee di avanzamento
   * 12 feed di modulo
   * 13 ritorno a capo
   * Utilizzare la parola chiave pipe, come delimitatore per | ad esempio: tubo di delimitazione
   * Rimuovi altri caratteri problematici
   * Dopo lo scorrimento precedente, rilasciare qualsiasi riga con un numero di colonne diverso dalla prima riga di dati (non vuoto o commento)
   * Supportare i file di rifiuto facoltativi per mantenere le righe rifiutate invece di ignorarle
   * Supporta la cartella di input ricorsiva; genera cartelle di output della stessa struttura
   * Sposta i file di input elaborati nelle sottocartelle elaborate in modo che lo script non ripeta l’operazione quando viene eseguito nuovamente sulla stessa cartella di input esistente
   * riconoscere la data nei nomi dei file di workbench; ordina l’elaborazione prima per data e poi per alfa, indipendentemente dal nome della cartella. Questo assicurerà che la sequenza sia corretta indipendentemente dal tipo di file di workbench (ecom, non ecom) o dall’ID suite di rapporti (se elabora più suite di rapporti in un singolo set di dati di Insight).
   * Avvisi e-mail di supporto `<discoiqbr>`
