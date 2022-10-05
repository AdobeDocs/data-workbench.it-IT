---
description: I diversi tipi di Dimension derivati (lato client) e come impostarli in Data Workbench.
title: Impostazione delle dimensioni derivate
uuid: 9d2416fb-1c29-45a8-91d0-ddca575224ad
exl-id: 79c72135-e527-4755-b43f-eacc63d765aa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '2100'
ht-degree: 0%

---

# Impostazione delle dimensioni derivate{#derived-dimensions-setup}

{{eol}}

I diversi tipi di Dimension derivati (lato client) e come impostarli in Data Workbench.

## Tipi di Dimension derivati {#section-33e6dcc9ab9745de9b830cecb2427ca3}

**Dimension delle metriche**

Il Dimension della metrica consente di raggruppare i conteggi delle metriche per un livello specifico. Consente inoltre di raggruppare i conteggi delle metriche per un livello specifico. Una volta creato un Dimension di metriche, puoi segmentare i dati in base al valore della metrica.

Esempio 1: Sei una società di viaggi e vuoi capire la differenza di attività comportamentali sul sito web tra i tuoi frequenti volantini e i clienti che hanno prenotato un volo meno di 5 volte-come faresti?

Tutto quello che hai è il conteggio delle prenotazioni come metrica, come segmenterai i clienti in base a una metrica - qui, prenotazione - per capire il loro comportamento sul sito web?

Esempio 2: Sei una Financial Bank e vuoi raggruppare i tuoi clienti in base al numero di CD in cui hanno investito. Vuoi segmentare i tuoi clienti in 3 livelli. Livello 1 - Clienti con oltre 10 CD, livello 2 - Clienti con >5 e &lt;10 CD e livello 3 - Clienti con >0 e &lt;5 CD

Le informazioni disponibili sono metriche che ti forniscono i conteggi degli investimenti in CD. Come creerai i segmenti cliente stanchi per la tua analisi?

*Creazione di un Dimension di metriche - tramite Workstation*

Contrassegna una delle dimensioni della metrica OOB come locale e rinomina tale dimensione con un nome personalizzato / Crea una copia locale dell’esempio RenameDim.example e rinominala nel nome della dimensione corretto con estensione .dim

Apri la nuova dimensione creata nella workstation per apportare modifiche. Modifica i seguenti parametri della dimensione metrica in base ai requisiti: ![](assets/dwb_impl_derived_dims1.png)

Metrica - Metrica da raggruppare

Livello a cui verranno raggruppate le metriche

Avvio a intervalli - Elemento iniziale del Dimension di metriche. Immettere lo stesso valore in offset.

Dimensione intervalli : consente di raggruppare le dimensioni della metrica. Inserisci lo stesso valore in scala

Conteggio intervalli - Numero massimo di elementi da visualizzare nella dimensione

Salva la dimensione appena creata sul server se desideri condividerla con altri.

**Dimension prefisso**

Lo scopo principale della dimensione Prefisso è quello di raggruppare gli elementi della dimensione originale e di fornire nomi descrittivi agli elementi raggruppati.

Ad esempio, possedete un sito di vendita al dettaglio e il vostro sito ha varie sezioni del sito come Abbigliamento Donna, Abbigliamento Uomo, Giocattoli e Giochi, Inizio Decor, ecc e ognuna di queste sezioni del sito ha diverse pagine associate ad esso. Vuoi eseguire un’analisi dei percorsi e ottenere informazioni sul traffico che va da una sezione del sito all’altra e così via. Se utilizzi una dimensione URI, dovrai estrarre ogni pagina di ciascuna sezione del sito nel browser percorsi o nella mappa del processo e continuare l’analisi.

La stessa analisi può essere eseguita facilmente se esiste una dimensione Prefix che ha pagine di una sezione del sito raggruppate come un singolo elemento.

Creazione di un Dimension di prefisso:

Apri una mappa del processo 2D dal menu Visualizzazione.

Modifica i seguenti parametri della dimensione del prefisso in base ai requisiti.

Cambia Dimension mappa - Il Dimension che si desidera utilizzare per la mappa del processo 2D (es: Tipologia SMS)

Cambia Dimension a livello di mappa - Livello della dimensione di cui sopra

Cambia Dimension di clip mappa - Il livello numerabile in cui si desidera esaminare i dati.

Cambia metrica mappa - La metrica da esaminare.

Una volta impostata la mappa del processo 2D, apri la dimensione indicata nel parametro Cambia Dimension mappa.

Seleziona gli elementi da raggruppare. Usa CTRL+ALT e trascina e rilascia gli elementi su per elaborare la mappa.

Fai clic con il pulsante destro del mouse sul punto visualizzato e rinomina il nome del gruppo. Se hai selezionato 3 elementi da raggruppare, il nome predefinito sarà 3 Selezionato.

Fai clic con il pulsante destro del mouse sul contorno della visualizzazione e salva la dimensione dal menu visualizzato.

**Rinomina Dimension**

I Dimension di ridenominazione vengono creati da una dimensione preesistente. Lo scopo principale della dimensione di ridenominazione è quello di fornire nomi descrittivi agli elementi della dimensione. La dimensione Rinomina predefinita è la dimensione Pagina creata dalla dimensione URI. La dimensione URI può confondere una persona che non conosce i nomi tecnici delle pagine ed è per questo che la dimensione Pagina consente di rinominare gli elementi della dimensione URI.

CREAZIONE DI DIMENSION DI RINOMINAZIONE PERSONALIZZATI:

Gli elementi della dimensione rinominata presentano una mappatura uno-a-uno con gli elementi della dimensione di base originale. Per verificarlo, apri il file .dim del Dimension Rinomina nel riquadro Workstation/Note. Noterai che ogni elemento della dimensione originale ha un solo valore (Rinomina stringa) rispetto a esso nel file .

Se si dispone di meno elementi per lo scopo di ridenominazione, puoi creare un file .dim nella workstation e rinominare ogni singolo elemento seguendo i passaggi descritti di seguito.

Passaggi per creare un file .dim per un Dimension Rinomina- Utilizzo della workstation

Utilizza questa opzione se i numeri di elementi da rinominare sono inferiori.

1. Apri un’area di lavoro vuota e apri Gestione Dimension. Fai clic con il pulsante destro del mouse su Amministratore>Profilo>Gestione profili.
1. Espandi la cartella Dimension nella colonna File.
1. Espandi la cartella di pagina nella colonna File e fai clic con il pulsante destro del mouse sul file Page.dim nella colonna Second to Last (Questa colonna in genere rappresenta il nome del profilo) e fai clic sull’opzione &quot;Make Local&quot; (Rendi locale).
1. Fai clic con il pulsante destro del mouse su Page.dim nella colonna &quot;Utente&quot; e fai clic sull&#39;opzione Copia e incolla il file .dim copiato nella cartella desiderata sotto la directory dei Dimension.
1. Fai clic su OK sul messaggio di errore.
1. Ora, noterai che ci sono due file Page.dim sotto la cartella Dimension. Uno è il file originale sotto la directory Dimension\Pagina e il secondo è quello che hai appena copiato incollato al punto 4.
1. Fai clic con il pulsante destro del mouse sul file Page.dim incollato di recente sotto la colonna Utente e fai clic sulla casella di input blu/grigio che riporta Page.dim. La casella di input diventa verde quando il cursore lampeggia e indica che può essere modificato. Digitare il nome della dimensione Rinomina che si desidera creare.
1. Noterai che il file Page.dim nella Colonna file è stato modificato nel nuovo nome file assegnato nel passaggio 7. Fai clic con il pulsante destro del mouse sul file new.dim nella colonna Utente (Ultima colonna) e seleziona Apri>In Workstation.
1. Una volta aperto il file .dim nella workstation; fai clic sul segno più (+) accanto all’entità ed espandila. Osserva il valore presente nel campo &quot;Padre&quot; e riflette la dimensione &quot;URI&quot;. Mostra &quot;wdata/model/dim/URI&quot; Fare clic sulla casella di input blu/grigio per modificare l’URI con il nome della dimensione di cui si desidera rinominare gli elementi.
1. Assicurati che la dimensione da rinominare esista nel set di dati. I nomi dei Dimension sono sensibili all’uso di maiuscole e minuscole, pertanto conservano le lettere maiuscole in minuscole e viceversa nella dimensione originale.
1. Osserva la visualizzazione &quot;modificato&quot; accanto al nome della dimensione. Indica che la dimensione originale è stata modificata. Sostenere le modifiche apportate al punto 9; Fai clic con il pulsante destro del mouse su new.dim (modificato) e fai clic sull&#39;opzione &quot;Salva con nome&quot;.
1. Una volta salvata la dimensione al passaggio 10, la nuova dimensione di ridenominazione per le campagne è ora disponibile per la ridenominazione. È disponibile solo localmente.
1. Affinché altri possano vedere la dimensione creata da te, è necessario salvarla sul profilo. Fai clic con il pulsante destro del mouse sul file .dim della nuova dimensione nella colonna &quot;Utente&quot; (Ultima colonna) e fai clic su &quot;Salva su>Nome profilo&quot; in cui desideri salvare la dimensione.
1. Dopo aver salvato il file nel profilo, tutti gli utenti di Workstation che hanno accesso a questo profilo potranno visualizzare la dimensione di ridenominazione per le campagne.

Strumento per la creazione di contenuti con prefisso e ridenominazione

Adobe dispone di uno strumento Excel per generare Dimension Prefix e Rinomina.

Di seguito sono riportati i passaggi per generare le dimensioni Prefisso/Rinomina utilizzando lo strumento:

1. Salva lo strumento Excel *Adobe_DWB_Dimension_Generator.xlsm* in una cartella. Contatta l’Assistenza clienti Adobe per scaricare lo strumento.
1. Apri lo strumento e abilita le macro: ![](assets/dwb_impl_derived_dims2.png)

1. Compila il foglio dati con i valori da utilizzare.

   Ad esempio, stiamo creando la dimensione Prefisso marchio prodotto in base al Dimension di prodotti. Nella scheda dati vengono acquisite le seguenti informazioni: ![](assets/dwb_impl_derived_dims3.png)

   Ciascun prodotto viene assegnato a un marchio nel foglio dati.

1. Nella scheda Configurazione , compila le informazioni relative alla dimensione da creare. Per i dati di esempio di cui sopra sono inserite le informazioni seguenti: ![](assets/dwb_impl_derived_dims4.png)

   Nome: Nome della dimensione Prefisso/Rinomina

   Tipo: Prefisso/Rinomina

   Dim origine: Dimension originale

   Colonna di corrispondenza: Colonna da abbinare

   Colonna dei risultati: Valore da utilizzare per la nuova dimensione.

1. Fai clic sul pulsante con titolo *Fai clic qui*. ![](assets/dwb_impl_derived_dims5.png)

1. Il file dim verrà generato nella stessa cartella in cui è stato salvato lo strumento. ![](assets/dwb_impl_derived_dims6.png)

   Utilizzando Profile Manager (Gestione profili), salva il file dim nella cartella del Dimension.

**Dimension di spostamento**

Le dimensioni di spostamento consentono di esaminare l’elemento Nth di qualsiasi dimensione all’interno di un particolare Dimension Countable.

Ti danno anche la possibilità di guardare indietro -Nth elemento di qualsiasi dimensione all&#39;interno di un particolare Dimension Contabile

Esempio 1:

* Nth page within a session - Next Page Dimension
* Nth page for a visitor -Next Page for Visitor (ennesima pagina per un visitatore - Pagina successiva per il visitatore) in tutte le sessioni
* Nth call per un utente

Perché è importante conoscere Nth elemento della dimensione numerabile?

* Vuoi conoscere la 5a pagina visualizzata in una sessione.
* Vuoi eseguire percorsi su Campagne per capire quale campagna è stata visualizzata dopo la visualizzazione della campagna &quot;Free Check Account&quot;?
* Vuoi capire quale link ha cliccato il visitatore prima di fare clic sul link &quot;Chat with an Agent&quot;? ![](assets/dwb_impl_derived_dims7.png)

L’URI successivo è una delle dimensioni OOB Shift che possono essere utilizzate come modello. L’esempio precedente fornisce l’elemento 2nd(Offset = 1) della campagna (Dim = Campaign) nell’evento di coinvolgimento (Clip = evento di coinvolgimento)

In questo caso l&#39;offset 1 significa guardare verso destra in avanti nell&#39;evento

Altri Dimension OOB Shift

*Pagina successiva:*

La pagina successiva visualizzata in una sessione dopo la selezione corrente di Pagina nel Dimension Pagina

L&#39;offset qui è 1, il livello è visualizzazione pagina, il valore di attenuazione è pagina e il clip è sessione

*Pagina precedente:*

La pagina precedente è stata visualizzata in una sessione prima della selezione di Pagina nel Dimension Pagina

Qui l&#39;offset è -1, il livello è Visualizzazione pagina, il valore Dim è Pagina e il clip è Sessione

Quale sarà la campagna precedente visualizzata prima della campagna attualmente selezionata da un visitatore?

Qui l&#39;offset è -1, il livello è la risposta della campagna, il valore dell&#39;attributo di risposta della campagna e la clip è il visitatore

*Creazione di un Dimension di spostamento - Tramite Workstation*

* Contrassegna una dimensione di spostamento OOB come locale
* Rinomina la dimensione con un nome personalizzato
* Apri una nuova dimensione creata nella workstation per apportare modifiche
* Modifica i seguenti parametri della dimensione metrica in base ai requisiti.

   * Dimensione conteggiata a livello
   * Offset-Si desidera guardare avanti rispetto all&#39;indietro
   * Dim -Dimension di cui analizzare gli elementi
   * Conteggio clip in cui si desidera visualizzare.

* Salva la dimensione appena creata sul server se desideri condividerla con altri.

**Ultimo Dimension N**

Gli ultimi N Dimension operano solo sul Dimension di tempo e su A del tempo del sistema. Le dimensioni orarie OOB sono Giorno, Settimana, Ora e Mese. Puoi creare l’ultima dimensione N per ciascuna di queste dimensioni di base quali Ultimi 10 giorni, Ultimi 72 ore, Ultime 8 settimane, Ultimi 6 mesi, ecc. L&#39;ultimo Dimension N calcola l&#39;ultima N in base all&#39;attuale &quot;Metrica del tempo di rapporto&quot; o a partire dall&#39;ora del sistema. ![](assets/dwb_impl_derived_dims8.png)

Conteggio - Numero totale di elementi da visualizzare nella dimensione

Offset intervallo - Valore di offset per indicare il punto iniziale (Giorno/Settimana) per calcolare l’ultimo N giorno/settimana.

**None.dim**

None.dim è una dimensione Alias. Viene utilizzato per creare alias dalle dimensioni estese.

Esempio:

In None.dim l’entità è definita come &quot;wdata/model/dim/Parent/+name&quot; (può essere modificato), il che significa creare la dimensione in base al nome del file di dimensione. Quindi, se creiamo una copia del file None.dim nella cartella del Dimension (per questo esempio, copiando e rinominando il file None.dim nella cartella Profilo visitatore) e lo rinomina in &quot;Log Source ID.dim&quot;, nel menu sotto Profilo visitatore verrà visualizzata una nuova dimensione derivata con Log Source ID come mostrato di seguito:

Prima delle modifiche: ![](assets/dwb_impl_derived_dims9.png)

Dopo la modifica di None.dim: ![](assets/dwb_impl_derived_dims10.png)

L’entità può essere modificata con il nome della dimensione estesa, in questo caso un’altra dimensione con un altro nome che punta alla stessa dimensione come mostrato di seguito:

In questo esempio il contenuto di &quot;Source Name.dim&quot; è il seguente: ![](assets/dwb_impl_derived_dims11.png)

Verrà quindi visualizzato un altro Nome origine Dimension che punta all&#39;ID origine registro. ![](assets/dwb_impl_derived_dims12.png)

**Nascondere Dimension derivati**

Per nascondere il Dimension derivato, imposta il *Mostra* su &quot;false&quot;. ![](assets/dwb_impl_derived_dims13.png)
