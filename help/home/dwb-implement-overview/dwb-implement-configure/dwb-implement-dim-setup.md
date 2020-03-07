---
description: In questa sezione vengono descritti i diversi tipi di dimensioni e come impostarle in DWB.
title: Impostazione dimensione
uuid: 5b40cb43-7790-4b87-a0bb-be395a420157
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Impostazione dimensione{#dimension-setup}

In questa sezione vengono descritti i diversi tipi di dimensioni e come impostarle in DWB.

## Quali sono le dimensioni {#section-dac631943df24706827cedc6f0641543}

Al livello più basilare, le dimensioni sono categorie in cui i dati nel dataset possono essere suddivisi.

Best practice: È possibile assegnare qualsiasi nome alle dimensioni dello schema dati. I nomi delle dimensioni utilizzati e spiegati in questo corso sono considerati una best practice. Le dimensioni possono essere denominate in modo diverso. Quando si acquisisce un&#39;esposizione ad altri set di dati, si iniziano a vedere differenze nei set di dati. È importante comprendere lo scopo delle dimensioni piuttosto che il loro nome. Ad esempio, che si chiami &quot;Visitatore&quot;, &quot;Cliente&quot;, &quot;Persona&quot;, &quot;Consumatore&quot; o &quot;Utente&quot;, è importante comprendere che questi termini sono comunemente utilizzati per fare riferimento alla dimensione contabile di livello più elevato utilizzata per raccogliere informazioni su una singola persona.

Per informazioni complete, consultate la guida alla configurazione [del set di](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/c-dataset-constr.html) dati.

## Tipi di dimensioni in DWB {#section-a4fbb7bf2bde44528ac0f94a96465862}

In Workbench dati sono disponibili due tipi di dimensioni: Dimensioni estese e dimensioni derivate.

Dimensioni estese vengono create dai campi nei file di dati &quot;non elaborati&quot;. Le dimensioni estese vengono utilizzate per classificare i dati &quot;non elaborati&quot; e per specificare le relazioni esistenti tra i dati. Le dimensioni estese vengono create dagli architetti di Workbench dati.

Le dimensioni derivate vengono create da un utente &quot;sul lato client&quot; dopo che il set di dati è stato elaborato utilizzando le definizioni esistenti delle dimensioni estese. Ad esempio, in base alla dimensione URI esistente, un utente può scegliere di creare una dimensione Nome pagina derivata, in cui viene visualizzato un nome di pagina più facile da usare al posto di un determinato URI. Tutte le dimensioni sono costituite da elementi o elementi che sono stati classificati (raggruppati) insieme per formare la dimensione. Di seguito sono riportati tre dimensioni ed i relativi elementi.

Molte dimensioni derivate vengono create automaticamente per determinare diversi tipi di visualizzazioni. Ad esempio, quando un utente crea una mappa del sito o del processo, i server DWB creano una dimensione Prefix. Altri, come le dimensioni dell&#39;ora di reporting, sono definiti dai file nella directory Dimensions di un profilo.

>[!NOTE]
>
>Gli elementi che appaiono in una data dimensione rifletteranno solo i valori esistenti nei record scelti per essere caricati nel dataset. Ad esempio, se non sono presenti dati per &quot;12 maggio&quot;, tale mese non verrà visualizzato nella dimensione &quot;Mese&quot;.

## Dimensioni estese {#section-5fc51fa539034941a30a2df606f7d727}

Tipi di dimensioni estese

**1) Dimensioni numerabili**

Al livello più alto ci sono dimensioni numerabili. Le dimensioni contabili sono due funzioni principali. In primo luogo, si tratta di dimensioni di cui si desidera contare gli elementi. In altre parole, countables risponde alle domande quali:

* &quot;Quanti visitatori hanno visitato la vostra homepage?&quot;
* &quot;Quante visite sono arrivate da google.com?&quot;

Per questo motivo, le countable vengono spesso utilizzate come componente di base per la creazione di metriche.

La seconda funzione principale dei countables è che essi formano la spina dorsale della struttura dello schema del dataset. Lo schema di dati e tutte le altre dimensioni sono organizzati in modo che siano raggruppati e appartengano a una tabella contabile. In altre parole, se consideriamo le dimensioni come &quot;categorie&quot;, allora i conti sono il modo in cui organizziamo queste &quot;categorie&quot; in gruppi.

Quando le dimensioni sono raggruppate sotto una dimensione numerabile, si dice che siano al &quot;livello&quot; della dimensione numerabile. Ad esempio, &#39;Indirizzo e-mail&#39; può essere a livello di Visitatore e &quot;Browser&quot; a livello di Visita. Per &quot;Elemento padre&quot; e &quot;figlio&quot; si intende la relazione tra la tabella contabile e le dimensioni raggruppate al di sotto. Ad esempio, il visitatore è un &quot;padre&quot; di indirizzo e-mail. Al contrario, l&#39;indirizzo e-mail è un &quot;figlio&quot; del visitatore.

**2) Dimensioni semplici**

Le dimensioni più comuni sono Semplici. Le dimensioni semplici hanno una relazione uno-a-molti con una dimensione contabile padre e sono comunemente utilizzate nelle visualizzazioni in modo da poterne visualizzare gli elementi. Ciò significa che una dimensione numerabile può avere un valore per una dimensione semplice, ma la dimensione semplice può appartenere a una o più countable. Ad esempio, un cliente ha il nome &quot;John&quot;, che può avere un solo nome, ma molti altri clienti possono avere il nome &quot;John;. Come altro esempio, un solo browser (ad esempio Firefox) può essere utilizzato per qualsiasi visita particolare a un sito Web, ma tale browser può essere utilizzato per molte visite diverse.

Se le dimensioni calcolabili rispondono &quot;Quante?&quot;, allora le dimensioni semplici rispondono &quot;Quali?&quot;. utilizzando lo stesso esempio sopra utilizzato nella sezione delle dimensioni numerabili; Nome pagina è la dimensione semplice. Utilizzando la tabella e la dimensione semplice, Nome pagina, possiamo rispondere a domande come:

* &quot;Quale pagina aveva il maggior numero di visualizzazioni di pagina?&quot;
* &quot;Di tutte le pagine del carrello, quale ha avuto più visite?&quot;

**3) Dimensioni molte**

Le dimensioni molte-a-molti hanno una relazione molti-a-molti con una dimensione contabile padre. Ad esempio, se una dimensione denominata Termine di ricerca esterna si trova a livello di Visita; un determinato termine di ricerca esterna può essere utilizzato in una o più visite e una data visita può includere uno o più termini di ricerca esterna. Pertanto, Termine di ricerca esterna è una dimensione molti-a-molti.

**4) Dimensioni numeriche**

Le dimensioni numeriche sono un tipo di dimensione semplice con un valore numerico. Le dimensioni numeriche vengono spesso create per essere utilizzate nelle metriche. Esempi di dimensioni numeriche includono &quot;Revenue&quot;, &quot;Orders&quot; e &quot;Units&quot;. Nell&#39;esempio precedente, &quot;Ordini cliente&quot; è una dimensione numerica.
**5) Dimensioni** normali Le dimensioni normali sono dimensioni che hanno una relazione uno-a-uno con una dimensione calcolabile padre. Le dimensioni standard sono spesso utilizzate con dimensioni con elevata cardinalità (molti elementi unici) come i dati di identificazione. Ad esempio, un visitatore può avere un solo ID utente e un ID utente può appartenere a un solo visitatore. Quindi, questa è una relazione uno-a-uno e può essere una dimensione normale.

Ad esempio, l’ID utente Web Geometrixx è una dimensione standard a livello di cliente. Poiché è normale, ha una relazione uno-a-uno con la dimensione padre, il che significa che ogni ID utente Web ha un cliente e ogni cliente ha un solo ID utente Web. Pertanto, la metrica &quot;Customers&quot; può essere solo &quot;1&quot; per ogni elemento dell’ID utente Web Geometrixx.

**6) Dimensioni tempo**

Le dimensioni temporali consentono di creare un set di dimensioni temporali locali periodiche o assolute in base al campo di marca temporale specificato. Esempi di dimensioni temporali sono &#39;Day&#39;, &#39;Hour&#39;, &#39;Week&#39; e &#39;Hour of Day&#39;. Nell’esempio precedente, la tabella &quot;Ora del giorno&quot; mostra il numero di visite e di visualizzazioni di pagina ricevute nelle diverse ore dei giorni.

>[!NOTE]
>
>L&#39;escape % utilizzato per la formattazione della visualizzazione è uguale a quello standard della libreria C *strftime*.

## Definizione delle dimensioni estese {#section-38ee124ec74b43fb95f13194a9582b97}

Passaggi per definire la dimensione estesa:

1. Quando lavori nel profilo del set di dati, apri Gestione profili e fai clic su Set di dati per visualizzarne il contenuto.
1. Aprire il file Transformation.cfg o Transformation Dataset Include nel quale si desidera definire la dimensione estesa.
1. Fare clic con il pulsante destro del mouse su Trasformazioni e scegliere Aggiungi nuovo > `<Extended dimension type>`.
1. Inserite le informazioni appropriate per la dimensione estesa. Per una descrizione dei tipi di trasformazione e informazioni sui relativi parametri, vedere le sezioni seguenti:

   * [Dimensioni numerabili](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-count-dim.html)
   * [Dimensioni semplici](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-simple-dim.html)
   * [Dimensioni molte-molte](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-many-dim.html)
   * [Dimensioni numeriche](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-num-dim.html)
   * [Dimensioni standard](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-denormal-dim.html)
   * [Dimensioni tempo](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/extended-dimensions/extended-dimensions-types/c-time-dim.html)

1. Per qualsiasi dimensione estesa definita, potete aggiungere una o più righe di commento al parametro Commenti per descrivere ulteriormente la dimensione o aggiungere note sul suo utilizzo. Per aggiungere un commento, fare clic con il pulsante destro del mouse sull&#39;etichetta *Commenti* e scegliere* Aggiungi nuovo > Riga commento*.

1. Dopo aver definito le dimensioni estese nel file di configurazione, salvate il file localmente e salvatelo nel profilo del dataset sul server DWB.

## Nascondere le dimensioni estese {#section-02339fb51658418eabc10186cd5957d7}

Le dimensioni estese possono essere nascoste in modo che non vengano visualizzate nel menu Dimensione del DWB. Per nascondere la dimensione, impostare la proprietà Hidden su &quot;True&quot; nella definizione della dimensione.
