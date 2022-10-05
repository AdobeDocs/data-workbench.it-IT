---
description: Glossario di Data Workbench
title: Glossario di Data Workbench
uuid: 1000c43d-383c-442d-bd09-de4f286ded31
exl-id: 29d6560a-0394-4031-8152-20f7ea0de00b
source-git-commit: e355e8df64f7d6f0c3900ba51b55b6cf509f0751
workflow-type: tm+mt
source-wordcount: '4201'
ht-degree: 88%

---

# Glossario di Data Workbench{#data-workbench-glossary}

{{eol}}

**Avviso**: All’interno di Data Workbench, indica un messaggio o un rapporto che viene attivato automaticamente quando una metrica raggiunge una soglia definita entro un intervallo di tempo specificato. Ad esempio, è possibile creare un avviso che invia un messaggio e-mail se il numero di visualizzazioni di pagina è superiore o inferiore a una quantità specificata nell’arco di un periodo di 24 ore.

**Analista**: Utente singolo utente che esegue analisi, definisce rapporti o utilizza in altro modo Data Workbench.

**Architetto**: Utente singolo che determina il modo in cui i dati verranno acquisiti, elaborati e organizzati a scopo di analisi e reporting. Questo individuo possiede in genere una notevole esperienza nella configurazione di Adobe® Platform per l’utilizzo da parte degli analisti.

**Grafico a barre**: Una forma di grafico che utilizza barre rettangolari di varie dimensioni per visualizzare i confronti tra due o più elementi.

**Benchmark**: Misura o standard che funge da punto di riferimento mediante il quale gli altri possono essere misurati o giudicati. All’interno di Data Workbench, il benchmark indica il confronto tra il valore associato a una selezione (un sottoinsieme selezionato) e il valore che verrebbe mostrato se tale la selezione non fosse effettuata.

**Cardinalità**: Numero di elementi in un set. Il numero di elementi in una dimensione dati Adobe è definito cardinalità della dimensione.

**Checkpoint (Punto di controllo)**: Data e ora in cui è stata scritta una copia di un set di dati Adobe a scopo di backup o ripristino. Il termine si riferisce anche al set di dati che viene scritto durante un’operazione checkpoint.

**Chi-square (Chi quadro)**: Un test statistico per determinare la probabilità che una deviazione osservata dall’evento o risultato previsto si sia verificata per caso. All’interno di Data Workbench, più il Chi square (Chi quadro) è vicino è al 100%, maggiore è la probabilità che tale deviazione si sia verificata solo per caso.

**Clickstream**: Termine informale che fa riferimento alla sequenza di pagine richieste da un utente durante la navigazione in un sito web. Le informazioni relative al clickstream possono aiutare i proprietari del sito a comprendere in che modo i visitatori lo utilizzano e quali pagine richiedono con maggiore frequenza. I proprietari del sito possono acquisire i clickstream dei visitatori sui propri siti, ma non possono acquisire i clickstream all’esterno del loro sito (salvo tramite uso di cookie o tag di pagina di terze parti), perché tali richieste sono registrate da server web esterni.

**Color Legend (Legenda colore)**: Una legenda all’interno di Data Workbench che visualizza la sfumatura di colore per una metrica selezionata. Le legende colore consentono la codifica colore delle visualizzazioni in base a diverse metriche. Le visualizzazioni con codifica colore semplificano l’individuazione di anomalie, eccezioni e tendenze.

**Color Ramp (Gradazione di colore)**: In una legenda colore, indica l’intervallo di colori utilizzato per rappresentare l’intervallo di valori possibili per una metrica. Quando una legenda colore viene applicata a una visualizzazione, gli elementi grafici della visualizzazione (ad esempio, le barre di un grafico a barre) vengono codificati in base ai valori rappresentati dalla gradazione di colore.

**Common Key (Chiave comune)**: Variabile comune che crea una relazione tra le righe in due set di dati tabulari. Ad esempio, un ID prodotto potrebbe fungere da chiave comune tra una tabella di variabili di stringa di query e una tabella di dati di prodotto da un sistema di gestione dell’inventario.

**Intervallo di affidabilità**: Un intervallo di valori con una specifica probabilità di contenere il tasso o la tendenza. Gli intervalli di affidabilità dell’80% (p-value = 0,20), del 95% (p-value = 0,05) e del 99% (p-value = 0,01) sono quelli più comunemente utilizzati. (Origine: `https://www.nci.nih.gov/statistics/glossary`)

**Livello di affidabilità**: La probabilità che l’errore di campionamento in un risultato di un sondaggio rientri in un intervallo specificato, solitamente espresso in termini di errori standard (ad esempio, 1 errore standard equivale a una probabilità del 68%, 2 errori standard a una probabilità del 95,4%). (Origine: `https://www.magazine.org/research/3410.cfm`)

**Mappa di conversione**: All’interno di Data Workbench, indica un tipo di visualizzazione in cui gli elementi vengono tracciati sull’asse x in base al valore della metrica di conversione.

**Tasso di conversione**: All’interno di Data Workbench, la percentuale di sessioni durante le quali si è verificato un evento di valore. Il tasso di conversione è calcolato dividendo il numero di sessioni in cui si è verificato un evento di valore per il numero totale di sessioni.

**Correlazione**: Misurazione numerica dell’intensità di una relazione lineare tra due variabili casuali. Le variabili che tendono a spostarsi insieme verso l’alto o verso il basso sono correlate in modo positivo, mentre le variabili che tendono a muoversi in direzioni opposte sono correlate in modo negativo. Vedi anche Coefficiente di correlazione.

**Coefficiente di correlazione**: Il valore numerico che indica l’intensità di una relazione lineare tra due variabili casuali. Vedi anche Correlazione.

**Dimensione conteggiata (Countable Dimension)**: Una dimensione in cui il numero di elementi contenuti può essere conteggiato in modo discreto. Le dimensioni conteggiate possono avere dimensioni secondarie dei seguenti tipi: Countable, Numeric, Simple, Many-to-Many e Denormal (Conteggiata, Numerica, Semplice, Molti-a-Molti e Anomalo).

**CrossRows Transformation (Trasformazione CrossRows)**: All’interno del server di Data Workbench, indica una trasformazione dati che consente di incorporare in un calcolo i dati provenienti da più record di eventi per un visitatore, i quali sono stati creati in momenti diversi.

**Crosstab**: All’interno di Data Workbench, indica una visualizzazione tabulare che visualizza le metriche associate alle intersezioni di due dimensioni.

**Cubo**: Struttura di dati multidimensionale o un gruppo di celle di dati disposti in base alle dimensioni dei dati. Ad esempio, un foglio di calcolo esemplifica un array bidimensionale con i dati disposti in righe e colonne. In un foglio di calcolo, ogni riga o colonna rappresenta una dimensione. Un array tridimensionale può essere visualizzato come un cubo dove ogni dimensione ne forma un lato, inclusa qualsiasi sezione parallela con tale lato. Gli array dimensionali più alti non dispongono di alcuna metafora fisica, ma possono essere utilizzati per organizzare i dati in modo che gli utenti pensino alla propria azienda. Noto anche come ipercubo, array multidimensionale o database multidimensionale.

**Dashboard**: Area di lavoro creata per la visualizzazione anziché per l’interazione. I dashboard forniscono lo stato panoramico attraverso la visualizzazione di indicatori delle prestazioni chiave adatti a un determinato manager o operatore che sovrintende a uno o più obiettivi aziendali. Vedi anche Area di lavoro.

**Data mining**: L’applicazione non guidata o interattiva di una raccolta di procedure matematiche ai dati aziendali cronologici nel tentativo di reperire insights sotto forma di correlazioni e altre relazioni statistiche.

**Sottoinsieme dati**: Funzione che consente agli utenti di selezionare facilmente un sottoinsieme di set di dati da utilizzare nell’analisi online o offline. Un sottoinsieme di dati è una parte del set di dati basato su un filtro.

**Data Warehouse**: Un database progettato per supportare il processo decisionale all’interno delle organizzazioni. In genere, un data warehouse contiene grandi quantità di dati non volatili, variabili nel tempo, orientati al soggetto, strutturati in base a query online rapide e a riepiloghi manageriali.

**Data Processing Unit (Unità di elaborazione dati)**: Tipo di server di Data Workbench che si occupa dell’elaborazione, della memorizzazione e dell’invio di dati da un set di dati di Adobe. Un’unità di elaborazione dati può anche memorizzare i file di registro VSL che contengono i dati di origine da cui proviene il set di dati o che può ricevere i dati da un’unità di file server (FSU) di Data Workbench. Un’unità di elaborazione dati rappresenta il tipo di server di Data Workbench con cui interagiscono direttamente i client di Data Workbench e Report®.

**Set di dati**: I dati caricati ed elaborati dal server di Data Workbench. I set di dati rappresentano i dati che possono essere trasmessi a Data Workbench o a Report a scopo di analisi, reporting e segnalazione. A livello fisico, il set di dati risiede nel file temp.db. Ogni computer server di Data Workbench (o cluster server di Data Workbench) gestisce un set di dati.

**Dataset Data (Dati del set di dati)**: I dati creati e memorizzati in un insieme di dati server di workbench dati. Include i dati evento e i dati di integrazione ammessi o creati nel set di dati. Inoltre, contiene tutte le informazioni derivate da tali dati, in base a quanto determinato dai file di configurazione che definiscono tale set di dati. I dati del set di dati possono essere ricreati elaborando nuovamente i dati di evento e di integrazione che utilizzano gli stessi file di configurazione o file di configurazione diversi. I file di configurazione sono file di sistema gestiti come parte di un profilo Adobe.

**Dataset Record (Record del set di dati)**: Tali record di dati evento sono stati ammessi in un set di dati Adobe dopo l’esecuzione di tutti i filtri e di altre elaborazioni. Sono denominati anche come voci di registro elaborate.

**Dataset Schema (Schema del set di dati)**: Visualizzazione di Data Workbench che mostra lo schema del set di dati che attualmente supporta il profilo selezionato.

**Spazio di archiviazione dei dati**: La quantità di dati (in byte) immessi o creati in un set di dati di Adobe. Questi dati vengono memorizzati dal set di dati in un file denominato Temp.db, il quale si trova in un computer server di Data Workbench. I dati di Temp.db sono transitori e possono essere ricreati con la rielaborazione dei dati di origine (ad esempio, dati di evento e dati di integrazione) mediante i file di configurazione appropriati.

**Decoder (Decodificatore)**: Il componente nel server di Data Workbench che legge i dati dell’evento provenienti da varie origini e genera i dati utilizzati per la produzione del set di dati. L’output di un decodificatore può essere utilizzato come input per qualsiasi funzionalità di elaborazione del registro nel server di Data Workbench. I tipi di decodificatore includono il Sensor decoder (per il caricamento di dati da varie versioni di Sensor), il Regular Expression decoder (per il caricamento di dati da file flat delimitati) e l&#39;ODBC decoder (per il caricamento di dati da origini dati ODBC).

**Dimensione**: Un insieme di elementi che vengono percepiti come tutti appartenenti a un tipo simile da parte dell’utente. Gli elementi definiscono un set di categorie in cui i dati possono essere raggruppati. Ad esempio, gli elementi Lunedì, Martedì, Mercoledì, Giovedì, Venerdì, Sabato e Domenica costituiscono una dimensione “Giorno feriale”.

**Elemento dimensione**: Una singola categoria all’interno di una dimensione. Ad esempio, una dimensione “Giorno feriale” conterrà i singoli elementi Lunedì, Martedì, Mercoledì, Giovedì, Venerdì, Sabato e Domenica.

**Legenda Dimensione**: All’interno di Data Workbench, la legenda che elenca le dimensioni definite nel set di dati (o derivate da esso). Quando una selezione viene effettuata in una visualizzazione, la legenda Dimensione identifica le dimensioni i cui valori differiscono dal valore di riferimento per una quantità significativa a livello statistico.

**Drill Up-Down**: Una tecnica analitica specifica in base alla quale l’utente naviga tra i livelli di dati più riepilogati (drill up) fino a quelli più dettagliati (drill down). Ad esempio, quando si visualizzano i dati di vendita per il Nord America, un’operazione drill-down nella dimensione Regione potrebbe visualizzare Canada, Stati Uniti e Messico. Un ulteriore drill-down sul Canada potrebbe mostrare Toronto, Vancouver, Montreal e così via.

**Event Data (Dati evento)**: I dati raccolti da Sensor o con altri strumenti (ad esempio, un file di registro del server web), che costituiscono l’input principale per il server di Data Workbench. Ciascun record di dati evento rappresenta un record di transazione o una singola istanza di un evento.

**Dimensione estesa**: Una dimensione basata su dati estesi. Per dati estesi si intendono tutti i dati che superano quelli minimi richiesti per la creazione di un record valido di dati evento. I dati estesi possono essere aggiunti a un record di dati dell’evento quando l’evento originale viene acquisito oppure possono essere incorporati da altre origini e inseriti nel record di dati dell’evento come dati di integrazione. Qualsiasi dimensione basata su questi dati aggiuntivi è considerata “estesa”.

**File Server Unit (FSU)**: Tipo di server di Data Workbench la cui funzione è unicamente quella di ricevere i dati evento da uno o più server Sensor o Repeater e di fornire i dati a una o più unità di elaborazione dati (DPU) del server di Data Workbench affinché siano utilizzati nella costruzione di set di dati Adobe. Le FSU ottimizzano il trasferimento dei dati evento alle DPU e risultano notevolmente più veloci rispetto ai normali file server. L’utilizzo di una FSU riduce i costi dell’hardware, consentendo la memorizzazione dei dati del registro su hardware archiviazione a basso costo e diminuendo la complessità amministrativa attraverso l’autorizzazione a più sensori di puntare a un singolo server di Data Workbench.

**Valutazione query incrementale**: Il processo brevettato con cui il server di Data Workbench fornisce risultati immediati di query a un utente in base a un campione casuale proiettato dell’intera popolazione. In questo processo, il server affina in modo incrementale la precisione della query prendendo in considerazione più dati fino a quando tutti i dati non li ha inclusi tutti e non si ottiene un conteggio esatto.

**Integration Data (Dati di integrazione)**: I dati di integrazione sono dati esterni provenienti da database aziendali o da file di ricerca che puoi combinare con i dati dell’evento per creare il set di dati. In generale, puoi utilizzare i dati di integrazione per migliorare i dati dell’evento acquisiti da Sensor. A livello concettuale, puoi utilizzare i dati di integrazione per compilare i record di dati evento con colonne di informazioni aggiuntive.

**Legend (Legenda)**: Una finestra di Data Workbench che fornisce dettagli esplicativi sulle visualizzazioni presenti nell’area di lavoro. I tipi di legende comprendono Color (a colori), Dimension (Dimensione) e Metric (metrica). Come qualsiasi finestra di Data Workbench, le finestre Legend possono essere generate e distribuite tramite Report.

**Line Graph (Grafico a linee)**: Tipo di visualizzazione di Data Workbench che esegue il grafico delle metriche per una dimensione specificata sotto forma di punti successivi sull’asse x di un grafico, quindi collega i punti con le linee. Un grafico a linee è un modo particolarmente efficace per visualizzare una metrica su una dimensione temporale.

**Condizione voce di registro (Log Entry Condition)**: Una condizione che determina se un record di dati evento (una voce di registro) sarà incluso nel set di dati. Ad esempio, una condizione per la voce di registro potrebbe specificare che solo i record di dati evento associati a un particolare sito web devono essere ammessi nel set di dati. Le condizioni della voce di registro sono specificate nel file di configurazione dell’elaborazione del registro che è presente nel server di Data Workbench.

**Many-to-Many Dimension (Dimensione da molti-a-molti)**: All’interno di Adobe Platform, indica una dimensione che presenta una relazione da molti-a-molti con una dimensione conteggiata superiore. Una dimensione da molti-a-molti rappresenta un insieme di valori per ciascun elemento della dimensione superiore. Ad esempio, nel sito, la dimensione della frase di ricerca presenta una relazione da molti-a-molti con quella superiore, ovvero la dimensione Session (Sessione). Dunque, una sessione può disporre di un numero qualsiasi di frasi di ricerca, e una frase di ricerca può avere un numero a piacere di sessioni.

**Masking (Mascheramento)**: Funzione di Data Workbench che consente agli analisti di nascondere temporaneamente gli elementi che non desiderano includere in un’analisi.

**Media**: Media aritmetica di un insieme di numeri. La somma dei dati divisa per la dimensione del campione.

**Median (Mediano)**: Numero che separa la metà più alta da quella più bassa di un campione, di una popolazione o di una distribuzione di probabilità. Metà della popolazione avrà valori inferiori o uguali al mediano, e metà della popolazione presenterà valori uguali o maggiori rispetto al mediano.

**Metrica**: All’interno di Adobe, rappresenta una formula denominata che descrive come calcolare un valore quantitativo a partire dai dati presenti nel set di dati. Nel sito, ad esempio, la metrica “Sessions per Visitor (Sessioni per visitatore)” rappresenta una formula che divide il conteggio delle sessioni per il numero di visitatori.

**Metric Legend (Legenda della metrica)**: Una finestra all’interno di Data Workbench che visualizza le metriche definite dal profilo attivo. Una legenda della metrica visualizza il valore di ogni metrica calcolata dal set di dati o dalla selezione corrente (se una selezione è attiva nell’area di lavoro, la legenda della metrica visualizza i valori per il sottoinsieme selezionato invece dell’intero set di dati). Come qualsiasi finestra di Data Workbench, le legende della metrica possono essere generate e distribuite tramite Report.

**Metric Worksheet (Foglio di lavoro della metrica)**: Una finestra all’interno di Data Workbench che consente agli analisti di definire le proprie metriche per un set di dati. Un foglio di lavoro della metrica è simile a un foglio di calcolo. Utilizzando la sintassi della formula di Data Workbench, gli analisti possono immettere espressioni che descrivono i valori quantitativi da ottenere dal set di dati. Ad esempio, un analista potrebbe definire una metrica che mostra la percentuale di visitatori che hanno visualizzato una pagina da un determinato dominio. Come per le metriche normali, le formule in un foglio di lavoro della metrica sul sottoinsieme selezionato quando una selezione è attiva nell’area di lavoro. Come qualsiasi finestra di Data Workbench, i foglio di lavoro della metrica possono essere generati e distribuiti tramite Report.

**Nuova condizione del visitatore (New Visitor Condition)**: La condizione che determina se si crea un nuovo ID di tracciamento quando al server di Data Workbench viene presentato un record di dati dell’evento.

**Nodo**: Un raggruppamento di uno o più elementi discreti in un’unica entità logica. In un file di configurazione (.cfg), un nodo è un elemento contenente i parametri correlati. Vedi anche Parametro e vettore. All’interno di Data Workbench, un nodo su una mappa del processo rappresenta una singola pagina o un gruppo definito di pagine.

**Numeric Dimension (Dimensione numerica)**: All’interno di Adobe Platform, indica una dimensione che ha valori numerici ordinati e con una relazione da uno-a-molti con una dimensione conteggiata superiore. In genere, una dimensione Numerica rappresenta una proprietà numerica degli elementi della dimensione superiore. Le dimensioni numeriche vengono spesso utilizzate per definire le metriche “sum” (somma).

**One-to-Many Relationship (Relazione da uno-a-molti)**: Una relazione tra due dimensioni dati in cui un singolo elemento in una dimensione è correlato a uno o più elementi nell’altra dimensione, o può esserlo.

**Ordinale**: Essere o denotare un ordine numerico in una serie. (Origine: `https://wordnet.princeton.edu/perl/webwn?s=ordinal`) Se una dimensione viene ordinata in modo ordinale all’interno di Dimension, gli elementi della dimensione vengono visualizzati nell’ordine in cui sono rappresentati internamente.

**Outlier**: In un set di dati, indicano un valore così lontano dagli altri all’interno della distribuzione che la sua presenza non può essere attribuita alla combinazione casuale di cause casuali.

**Sovrapposizione pagina**: Tipo di visualizzazione all’interno di Data Workbench che codifica a colori i collegamenti in un’immagine di una pagina web in base a una metrica specifica. Puoi utilizzare una visualizzazione di sovrapposizione pagina per identificare rapidamente quali collegamenti su una pagina attirano l’attenzione dei visitatori (e portarli ad altre pagine del sito) e quali no. Puoi anche utilizzarla per comprendere il “valore” (misurato in base agli eventi di valore) generato dai vari collegamenti di una pagina per il sito.

**Page View Condition (Condizione di Vista pagina)**: Un’opzione all’interno di una trasformazione del server di Data Workbench che consente di includere o escludere i record evento come viste pagina in base al tipo di contenuto o al contenuto effettivo. Puoi utilizzare questa opzione, ad esempio, per escludere i record evento relativi a richieste HTTP non riuscite (ad esempio, quelle che generano un codice di stato 404) o le richieste che restituiscono determinati tipi di contenuto (ad esempio, le richieste di immagini). Se un record di evento HTTP non viene escluso dall’opzione Condizione di vista pagina, tale record di evento rappresenterà una vista pagina nel set di dati.

**Path Browser Visualization (Visualizzazione browser del percorso)**: Tipo di visualizzazione all’interno di Data Workbench che consente a un analista di esplorare interattivamente una sequenza di eventi (come le Viste pagina) in una sessione visitatore o tra più sessioni.

**Server principale**: In un cluster di server di Data Workbench, il server di Data Workbench che gestisce le comunicazioni tra client (come Data Workbench e Report) e gli altri server del cluster. Il server principale funziona anche come punto focale amministrativo per il cluster. Utilizzando le funzionalità di sincronizzazione dei profili del server di Data Workbench, le modifiche apportate da un amministratore al server principale vengono propagate automaticamente agli altri server del cluster. Un server principale rappresenta una DPU del server di Data Workbench.

**Mappa del processo**: Tipo di visualizzazione di Data Workbench che consente a un analista di comprendere il flusso di traffico tra pagine o nodi di un sito web. Una mappa di processo mostra le informazioni relative a pagine specifiche (ad esempio il numero di sessioni durante le quali sono state visualizzate le pagine), indicando anche il volume di traffico tra le pagine o i nodi.

**Processing Server (Server di elaborazione)**: In un cluster di server di Data Workbench, indica i server di Data Workbench che sono controllati dalle informazioni di configurazione presenti sul server principale. Un server di elaborazione elabora i dati evento all’interno di un set di dati e risponde alle query dei client quali Data Workbench e Report. Nel rispondere a una query, un server di elaborazione divide (“partiziona”) la responsabilità per l’esecuzione della query tra i server del cluster. Quando gli altri server completano tre porzioni della query, il server di elaborazione combina (“departiziona”) i risultati e restituisce al client il risultato combinato.

**Profilo**: Un insieme di file di configurazione che contiene le regole per la creazione di un set di dati per uno scopo di analisi specifico. Un profilo definisce anche articoli quali metriche, dimensioni derivate, aree di lavoro, rapporti, visualizzazioni e legende, i quali consentono agli analisti di interagire con il set di dati e di reperire informazioni da esso. Un profilo può essere strutturato in modo generico per un sito web (come in un profilo per www.miosito.com) oppure può essere personalizzato per un particolare tipo di utente (come il profilo utente “Marketing” o “Finanza”).

**Profile Manager (Gestione profili)**: Strumento amministrativo interattivo presente all’interno di Data Workbench che consente a un amministratore o a un altro utente di gestire i file di configurazione associati a un profilo.

**Espressione regolare**: Formula che descrive o corrisponde a un set di stringhe in base a determinate regole di sintassi. Le espressioni regolari (spesso abbreviate come regexp, regex o regxp) sono utilizzate per cercare e manipolare i corpi di testo basati su determinati schemi. La notazione delle espressioni regolari ha avuto origine dai primi editor di Unix e si è diffusa in altre utilità Unix come vi e Perl. Oggi, le espressioni regolari sono supportate da molti editor di testo, linguaggi di script e altri strumenti di manipolazione del testo. Il server di Data Workbench include un motore con espressione regolari.

**Retention Map (Mappa di conservazione)**: Tipo di visualizzazione all’interno di Data Workbench che traccia gli elementi sull’asse x in base al valore della metrica Mantenimento.

**Dispersione**: Tipo di visualizzazione all’interno di Data Workbench che rappresenta i dati con due varianti sotto forma di punti su un grafico. Una dispersione presenta due parti di dati per ogni elemento oggetto da rappresentare nel grafico. Ad esempio, una dispersione delle metriche Tasso di conversione e Visitatori per un set di 10 pagine genererebbe 10 punti separati nel grafico.

**Selezione**: Funzione di Data Workbench che consente a un analista di limitare il set di dati recuperati e visualizzati a scopo di reporting o analisi. È possibile effettuare una selezione interattiva all’interno di Data Workbench facendo clic sugli elementi visualizzati in una o più dimensioni (con un clic con il pulsante sinistro del mouse si seleziona un elemento, un clic sul pulsante destro del mouse deseleziona un elemento). Le selezioni possono essere effettuate anche definendo i filtri che scelgano determinati elementi nelle dimensioni specificate.

**Simple Dimension (Dimensione semplice)**: All’interno di Adobe Platform, indica una dimensione che presenta una relazione da uno-a-molti con una dimensione conteggiata superiore. Ad esempio, Visitor Referrer (Referente visitatore) è una dimensione semplice la cui dimensione superiore conteggiata è Visitor (Visitatore). Un visitatore dispone di un solo referente visitatore. Tuttavia, un Referente visitatore può avere più Visitatori (un Referente Visitatore può essere correlato a più Visitatori).

**Smoothing (Anti-aliasing)**: Un’inferenza matematica di una curva su più punti in un grafico a linee, utilizzata per illustrare una linea di tendenza più significativa tra punti di dati relativamente sparsi.

**Origine**: Nel server di Data Workbench, indica una risorsa contenente i dati dell’evento che può essere utilizzata per creare un set di dati. I decodificatori di Adobe ricercano le origini dei dati dell’evento da decodificare che possono essere utilizzati da Data Workbench.

**Source Data (Dati origine)**: Sul server di Data Workbench, indica i dati che rappresentano l’input di uno dei suoi decoder. I dati di origine possono essere immessi nel Sensor decoder (che carica i dati di origine da varie versioni di Sensor), nel Regular Expression decoder (che carica i dati di origine da file flat delimitati) e nell’ODBC decoder (che carica i dati di origine da origini dati ODBC).

**Table Graph (Grafico a tabella)**: Tipo di visualizzazione di Data Workbench che visualizza i dati in formato tabulare. I valori delle metriche in un grafico a tabella possono essere espressi numericamente o rappresentati in formato a barre.

**Time Series (Serie temporali)**: Un grafico che mostra il modo in cui una determinata proprietà o valore cambia nel tempo.

**ID tracciamento**: Identificatore che distingue in modo univoco le entità principali analizzate in un set di dati di Adobe. Un ID di tracciamento può essere creato da varie fonti, tra cui un ID univoco da un cookie di un client web, un numero IP e un hash agente utente, oppure un nome x.509. Anche se si tratta di alcune origini comuni per un ID di tracciamento, è possibile utilizzare qualsiasi valore in grado di identificare in modo univoco le entità che popolano la dimensione Visitatore nel set di dati.

**Transformation (Trasformazione)**: Metodo per modificare il valore di una variabile utilizzando un’operazione matematica. Nel server di Data Workbench, ad esempio, gli analisti possono utilizzare la trasformazione divisa per suddividere le coppie nome-valore di una stringa query in singole variabili.

**Grafico a barre bidimensionale**: Tipo di visualizzazione di Data Workbench che visualizza in contemporanea due dimensioni e fino a due metriche in una visualizzazione grafica tridimensionale.

**Legenda valore**: Una finestra di Data Workbench che consente a un analista di associare un valore monetario a un evento selezionato e di visualizzare i risultati quando tale valore monetario viene sommato per tutte le istanze dell’evento selezionato nel set di dati.

**Visitatore**: La dimensione nel set di dati che identifica l’entità che ha generato l’evento. Ciascun membro della dimensione Visitatore è identificato da un ID di tracciamento univoco. In Site (Sito), ad esempio, l’ID di tracciamento viene in genere derivato da un ID univoco posto all’interno del cookie del client. In Call (Chiamata), l’ID di tracciamento potrebbe essere un numero di telefono del chiamante.

**Visitor Referrer (Referente visitatore)**: Il primo referente HTTP per un visitatore nell’intervallo di tempo di un set di dati Adobe.

**Divisione visitatori**: Funzione nel server di Data Workbench che consente ai visitatori con grandi quantità di dati evento di essere suddivisi tra due ID di tracciamento. La suddivisione del visitatore viene utilizzata per impedire che i dati dell’evento vengano filtrati dal set di dati quando un visitatore supera il numero massimo configurato di eventi per visitatore (un parametro impostato per garantire le corrette prestazioni del sistema). Anche se la suddivisione dei visitatori aumenta artificialmente il numero di visitatori nel set di dati, non incrementa il numero totale di record di eventi, il che assicura la precisione del numero totale di eventi numerabili (ad esempio, visualizzazioni di pagina, prenotazioni).

**VSL**: File di registro. Il tipo di file in cui il server Data Workbench memorizza i dati dell’evento ricevuti da Sensor. I file VSL sono compressi, ma possono essere inviati in formato non compresso utilizzando la funzionalità di trasformazione dei dati. VSL è l’estensione di file per un file di registro.

**What-If Analysis (Analisi What-If)**: Un tipo di analisi utilizzato per comprendere le conseguenze della modifica di determinate variabili all’interno di un modello dati, attraverso l’osservazione dell’effetto che le modifiche a tali variabili esercitano su altri dati nel modello.

**Area di lavoro**: All’interno di Data Workbench, un’area di lavoro è un contenitore per una particolare attività di analisi e visualizzazione. Un’area di lavoro può contenere più visualizzazioni, tutte basate su un set comune di dati (ovvero, tutte le visualizzazioni nell’area di lavoro eseguono il rendering dello stesso set di risultati della query). Quando un analista esegue un’operazione di creazione di un sottoinsieme, il sottoinsieme selezionato viene riflesso nell’intera area di lavoro.

**Worktop (Piano di lavoro)**: L’area “principale” all’interno dell’interfaccia utente di Data Workbench che consente di organizzare e accedere a tutte le aree di lavoro e ai rapporti. Consente inoltre di creare e salvare aree di lavoro e rapporti nuovi e aggiornati nel server di Data Workbench, in modo che altri utenti che utilizzano lo stesso profilo possano accedervi.
