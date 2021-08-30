---
description: Questa sezione spiega i diversi tipi di Dimension e come configurarli in DWB.
title: Impostazione della dimensione
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
exl-id: 04afd773-e938-49f7-83c9-1d706a6dc525
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 2%

---

# Impostazione della dimensione{#dimension-setup}

Questa sezione spiega i diversi tipi di Dimension e come configurarli in DWB.

## Dimension {#section-dac631943df24706827cedc6f0641543}

Al livello più semplice, le dimensioni sono categorie in cui i dati nel set di dati possono essere suddivisi.

Best practice: È possibile assegnare qualsiasi nome ai Dimension dello schema dati. I nomi dei Dimension utilizzati e spiegati in questo corso sono considerati una best practice. I Dimension possono essere denominati in modo diverso. Man mano che aumenti l’esposizione ad altri set di dati, inizierai a vedere le differenze nei set di dati. È importante comprendere lo scopo delle dimensioni piuttosto che il loro nome. Ad esempio, sia che si chiami &quot;Visitatore&quot;, &quot;Cliente&quot;, &quot;Persona&quot;, &quot;Consumatore&quot; o &quot;Utente&quot;, è importante comprendere che si tratta di termini comunemente utilizzati per fare riferimento alla dimensione conteggiata di livello più alto che viene utilizzata per raccogliere informazioni su una singola persona.

Per informazioni complete, consulta la guida [Configurazione set di dati](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/c-dataset-constr.html) .

## Tipi di Dimension in DWB {#section-a4fbb7bf2bde44528ac0f94a96465862}

Nella Data Workbench sono disponibili due tipi di dimensioni: Dimension estesi e Dimension derivati.

I Dimension estesi vengono creati dai campi nei file di dati &quot;non elaborati&quot;. Le dimensioni estese vengono utilizzate per classificare i dati &quot;grezzi&quot; e specificare le relazioni esistenti tra i dati. Le dimensioni estese vengono create da Data Workbench Architects.

I Dimension derivati vengono creati da un utente &quot;sul lato client&quot; dopo che il set di dati è stato elaborato utilizzando le definizioni di dimensioni estese esistenti. Ad esempio, in base alla dimensione URI esistente, un utente può scegliere di creare una dimensione Nome pagina derivata, che visualizza un nome pagina più semplice al posto di un determinato URI. Tutte le dimensioni sono costituite da elementi o elementi che sono stati organizzati (raggruppati) per formare la dimensione. Di seguito sono riportati tre dimensioni e i relativi elementi.

Molte dimensioni derivate vengono create automaticamente per determinare diversi tipi di visualizzazioni. Ad esempio, quando un utente crea una mappa del sito o del processo, i server DWB creano una dimensione Prefix. Altri, come le dimensioni dell’ora di reporting, sono definiti dai file nella directory dei Dimension di un profilo.

>[!NOTE]
>
>Gli elementi che compaiono in una data dimensione rifletteranno solo i valori esistenti nei record scelti per essere caricati nel set di dati. Ad esempio, se non sono presenti dati per &quot;12 maggio&quot;, tale mese non verrà visualizzato nella dimensione &quot;Mese&quot;.

## Dimensioni estese {#section-5fc51fa539034941a30a2df606f7d727}

Tipi di dimensioni estese

**1) Dimension conteggiabili**

Al livello più alto ci sono dimensioni conteggiate. Le dimensioni conteggiate servono due funzioni principali. Innanzitutto, si tratta di dimensioni di cui desideri conteggiare gli elementi. In altre parole, la funzione Countables risponde a domande quali:

* &quot;Quanti visitatori hanno visitato la tua homepage?&quot;
* &quot;Quante visite sono venute da google.com?&quot;

Per questo motivo, le countable vengono spesso utilizzate come blocco predefinito fondamentale di base per creare metriche.

La seconda funzione principale delle tabelle di conteggio è che formano la spina dorsale della struttura dello schema del set di dati. Lo schema dei dati e tutte le altre dimensioni sono organizzati in modo da essere raggruppati sotto e appartengono a una tabella numerabile. In altre parole, se consideriamo le dimensioni come &quot;categorie&quot;, allora le tabelle sono il modo in cui organizziamo queste &quot;categorie&quot; in gruppi.

Quando le dimensioni sono raggruppate sotto una dimensione numerabile, si dice che siano al &quot;livello&quot; della dimensione numerabile. Ad esempio, l’indirizzo e-mail può trovarsi a livello di Visitatore e il &quot;Browser&quot; a livello di Visita. Per &quot;Elemento padre&quot; e &quot;figlio&quot; si intende la relazione tra il numerabile e le dimensioni raggruppate al suo interno. Ad esempio, Visitatore è un &quot;padre&quot; dell’indirizzo e-mail. Al contrario, l’indirizzo e-mail è un &quot;figlio&quot; del visitatore.

**2) Dimension semplici**

Le dimensioni più comuni sono le dimensioni semplici. Le dimensioni semplici hanno una relazione uno-a-molti con una dimensione conteggiata superiore e sono comunemente utilizzate nelle visualizzazioni per poterne visualizzare gli elementi. Ciò significa che una dimensione numerabile può avere un valore per una dimensione semplice, ma la dimensione semplice può appartenere a una o più contee. Ad esempio, un cliente ha un nome di &quot;John&quot; - che il cliente può avere un solo nome, tuttavia, molti altri clienti possono avere il nome &quot;John;. Come altro esempio, solo un browser (ad esempio Firefox) può essere utilizzato per qualsiasi visita particolare a un sito web, ma tale browser può essere utilizzato per molte visite diverse.

Se le dimensioni numerabili rispondono &quot;Quante?&quot;, allora le dimensioni semplici rispondono &quot;Quali?&quot;. utilizzando lo stesso esempio sopra utilizzato nella sezione della dimensione numerabile; Nome pagina è la dimensione semplice. Utilizzando la tabella e la dimensione semplice Nome pagina, possiamo rispondere a domande quali:

* &quot;Quale pagina aveva il maggior numero di visualizzazioni di pagina?&quot;
* &quot;Di tutte le pagine del carrello acquisti, quale ha avuto più visite?&quot;.

**3) Molti-a-molti Dimension**

Le dimensioni da molti a molti hanno una relazione da molti a molti con una dimensione conteggiata superiore. Ad esempio, se una dimensione denominata Termine di ricerca esterna si trova a livello di visita; un determinato termine di ricerca esterna può essere utilizzato in una o più visite e una data visita può includere uno o più termini di ricerca esterna. Pertanto, il termine di ricerca esterno è una dimensione da molti a molti.

**4) Dimension numerici**

Le dimensioni numeriche sono un tipo di dimensione semplice con un valore numerico. Le dimensioni numeriche vengono spesso create per essere utilizzate nelle metriche. Esempi di dimensioni numeriche includono &quot;Entrate&quot;, &quot;Ordini&quot; e &quot;Unità&quot;. Nell’esempio precedente, &quot;Ordini cliente&quot; è una dimensione numerica.
**5)** Dimensioni normaliLe dimensioni normali sono dimensioni che hanno una relazione uno-a-uno con una dimensione conteggiata superiore. Le dimensioni denormali vengono spesso utilizzate con dimensioni che presentano un’elevata cardinalità (molti elementi unici) come i dati di identificazione. Ad esempio, un visitatore può avere un solo ID utente e un ID utente può appartenere a un solo visitatore. Quindi, questa è una relazione uno-a-uno e può essere una dimensione denormale.

Ad esempio, Geometrixx Web User ID è una dimensione standard a livello di cliente. Poiché è normale, ha una relazione uno-a-uno con la dimensione padre, il che significa che ogni ID utente web ha un cliente e ogni cliente ha un solo ID utente web. Pertanto, la metrica &quot;Clienti&quot; può essere solo &quot;1&quot; per ogni elemento di Geometrixx Web User ID.

**6) Dimension**

Le dimensioni temporali consentono di creare un set di dimensioni locali periodiche o assolute in base al campo di marca temporale specificato. Esempi di dimensioni temporali includono &quot;Day&quot;, &quot;Hour&quot;, &quot;Week&quot; e &quot;Hour of Day&quot;. Nell’esempio precedente, la tabella &quot;Ora del giorno&quot; mostra quante visite e visualizzazioni di pagina sono state ricevute nelle diverse ore dei giorni.

>[!NOTE]
>
>Gli escape % utilizzati per la formattazione della visualizzazione sono gli stessi della libreria C standard *strftime*.

## Definizione delle dimensioni estese {#section-38ee124ec74b43fb95f13194a9582b97}

Passaggi per definire il Dimension esteso:

1. Quando lavori nel tuo profilo di set di dati, apri Gestione profili e fai clic su Set di dati per visualizzarne il contenuto.
1. Apri il file Transformation.cfg o il file di inclusione del set di dati di trasformazione in cui desideri definire la dimensione estesa.
1. Fai clic con il pulsante destro del mouse su Trasformazioni e fai clic su Aggiungi nuovo > `<Extended dimension type>`.
1. Immetti le informazioni appropriate per la dimensione estesa. Per una descrizione dei tipi di trasformazione e informazioni sui relativi parametri, vedere le sezioni seguenti:

   * [Dimensioni conteggiate](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [Dimensioni semplici](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [Dimensioni Many-to-Many (Da molte-a-molte)](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [Dimensioni numeriche](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [Dimensioni anomale](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [Dimensioni temporali](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. Per qualsiasi dimensione estesa definita, è possibile aggiungere una o più righe di commento al parametro Comments per descrivere ulteriormente la dimensione o aggiungere note sul suo utilizzo. Per aggiungere un commento, fai clic con il pulsante destro del mouse sull&#39;etichetta *Commenti* e fai clic su* Aggiungi nuovo > Riga commento*.

1. Dopo aver definito le dimensioni estese nel file di configurazione, salva il file localmente e salvalo nel profilo del set di dati sul server DWB.

## Nascondere le dimensioni estese {#section-02339fb51658418eabc10186cd5957d7}

I Dimension estesi possono essere nascosti in modo che non vengano visualizzati nel menu Dimension nel DWB. Per nascondere la dimensione, impostare la proprietà Hidden su &quot;True&quot; nella definizione della dimensione.
