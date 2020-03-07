---
description: Attribuzione adattamento ottimale è un approccio di machine-learning per assegnare i valori di attribuzione tra i diversi canali di un evento di conversione di successo. Workbench dati valuta automaticamente i contributi al successo in una finestra di tempo per canale, quindi crea un modello di attribuzione basato sui pattern di interazione effettivi dei clienti.
title: Attribuzione adattamento ottimale
uuid: 0c51beb3-8f74-4f8e-9722-0c885140c8ce
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Attribuzione adattamento ottimale{#best-fit-attribution}

Attribuzione adattamento ottimale è un approccio di machine-learning per assegnare i valori di attribuzione tra i diversi canali di un evento di conversione di successo. Workbench dati valuta automaticamente i contributi al successo in una finestra di tempo per canale, quindi crea un modello di attribuzione basato sui pattern di interazione effettivi dei clienti.

**[!UICONTROL Best Fit Attribution]** consente di confrontare le interazioni, o i tocchi, che hanno contribuito a una vendita di successo, l&#39;accesso alle e-mail o altri indicatori di prestazioni. L&#39;analisi di attribuzione assegna automaticamente peso ai tocchi più importanti e fornisce un modello di attribuzione per canale basato sui dati e reattivo al mercato e ai protocolli interni.

![](assets/attrib_windows_5.png)

Ad esempio, se un cliente visita il sito tramite una ricerca organica, si impegna con una campagna e quindi si registra un&#39;e-mail, Attribuzione [basata su](/help/home/c-get-started/c-attribution-profiles/c-rules-attrib/c-rules-attrib.md) regole identificherebbe il primo tocco o l&#39;ultimo tocco, o distribuisce uniformemente l&#39;attribuzione di successo a tutti i punti di contatto utilizzando modelli di attribuzione predefiniti. Quando l&#39;attribuzione basata su regole viene definita dall&#39;utente, gli attributi di adattamento ottimale impostano i valori attraverso un algoritmo calcolando la probabilità di una conversione in funzione dei punti di contatto osservati.

>[!NOTE]
>
>Per eseguire l&#39;attribuzione **** Adatta [!DNL .pem file]ottimale in Workbench dati, è necessario aggiornare il certificato server () per supportare Adobe Analytics Premium. È inoltre necessario aggiungere **Premium** al client [!DNL Profile.cfg] personalizzato e ricevere nuovi certificati da Adobe ClientCare per server e server di report.

## Configurazione di base {#section-db597eaee462412ea7280d1426366c61}

Per istruzioni dettagliate, consultate [Creare un&#39;attribuzione](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-building.md#concept-fede6fc4f592475fa8b351b1765a522d) di adattamento ottimale.

**Impostate la metrica** Success (Success) Definite una metrica che rappresenta un evento di successo.

![](assets/attrib_windows_1.png)

La metrica di successo è spesso *Ordini*, anche se è possibile utilizzare Workbench dati per definire una metrica di successo molto complicata insieme alla finestra di successo.

**Impostare la metrica** Touch (facoltativo)

Identificare le interazioni per tenere traccia che hanno portato a una conversione di successo, quindi impostare la metrica Touch su cui verrà calcolata l&#39;attribuzione.

>[!NOTE]
>
>L’impostazione di una metrica Touch è necessaria solo se viene utilizzata per derivare le metriche del canale da elementi Dimensione drag and drop invece di utilizzare le metriche del canale esistenti.

Se non disponete di una metrica definita per campagne o canali, ma le dimensioni rappresentano i canali, la funzione Attribuzione adattamento ottimale può essere creata automaticamente in base alla metrica Tocco.

Ad esempio, con la metrica Touch impostata come *Hits* e a cui è stata assegnata una dimensione denominata *Media Type* con elementi che includono *Email*, *Press Release*, *Print Ad***[!DNL Hits where Media Type = Email] e Social Media, la visualizzazione genererà metriche Channel del modulo quando si trascina e si rilasciano gli elementi sulla visualizzazione.

![](assets/attrib_windows_2.png)

La metrica Touch determina quindi l’allocazione dei punteggi di attribuzione per identificare le interazioni di marketing considerate importanti per il successo, consentendo di qualificare i tocchi di marketing per la popolazione identificata nella finestra Successo. Puoi impostare metriche quali Visualizzazioni *di* pagina o *Hit* oppure utilizzare metriche touch personalizzate in base alle tue esigenze.

In molti casi, la finestra Tocco deve includere la finestra Successo per valutare un lungo periodo di lead time nel ciclo di vendita.

**Impostare la metrica Revenue (Entrate).**

Puoi scegliere di identificare le entrate tra i punti di contatto impostando una metrica delle entrate appropriata. Se specificato, il modello mostrerà la distribuzione dei ricavi sui canali di input. ![](assets/attrib_windows_6.png)

Puoi impostare una metrica ricavi con tipi di dati valuta per allocare il successo a tutti i punti di contatto principali definiti e analizzati. Questa metrica ripartisce i ricavi di vendita finali e assegna in base alla ponderazione assegnata dall&#39;algoritmo.

**Impostare le finestre di successo e di tocco.**

La finestra Successo definisce la popolazione da esaminare e il periodo per gli eventi di successo, consentendo di indicare le finestre di tempo e l’ampiezza di popolazione da considerare per l’analisi attraverso una selezione di aree di lavoro. La finestra **Successo** definisce il periodo e la popolazione da esaminare per gli eventi di successo. La finestra **Touch** specifica il periodo di tempo storico da esaminare per le interazioni dei canali che conducono agli eventi di successo.

>[!NOTE]
>
>L’impostazione di una metrica touch è necessaria solo se si tenta di generare automaticamente metriche di successo trascinando gli elementi dimensionali sulla visualizzazione.

Puoi impostare un giorno, un mese, un anno o qualsiasi intervallo di tempo disponibile per limitare la valutazione degli eventi di successo e di contatto nell’intero ciclo di vendita o per audience specifiche che entrano nel sito. La creazione di finestre per limitare l’attribuzione consente di focalizzare l’analisi sui periodi di tempo rilevanti per le esigenze specifiche.

![](assets/attrib_windows_4.png)

In molti casi, la finestra Touch includerà la finestra Successo per consentire di estendere l&#39;analisi su un lungo periodo di tempo, in base alla finestra di vendita. Oppure puoi tenere traccia e analizzare i tocchi separatamente dall’evento di successo.

**Selezionate i canali.**

Quando si immettono i canali, sono disponibili due opzioni.

**Aggiungere la metrica Touch e gli elementi dimensionali ai canali**

In molti casi, è necessario suddividere i punti di contatto principali per elementi dimensionali per definire canali specifici. In base ai valori degli elementi, Attribuzione adattamento ottimale selezionerà automaticamente i primi esecutori e li classifica in base alla percentuale e li visualizzerà in una visualizzazione grafico.

![](assets/attrib_windows_7.png)

Un modello di attribuzione verrà creato disegnando i visitatori che hanno interagito durante la finestra Successo ed esaminando i tocchi del canale durante la finestra Tocco che ha prodotto o meno un evento di successo.

## Suddivisione per canali {#section-a30592b84bc84f57bd2b988824e852d4}

Quando immettete i canali, avete due opzioni:

* Aggiungi una metrica **** Touch e quindi elementi **** dimensionali per i canali.

   **o**

* Crea metriche che filtrano gli elementi del canale che desideri valutare.

**Opzione 1: Aggiungi una metrica touch e aggiungi elementi dimensione per canali**.

Questo è l&#39;approccio più semplice. Attribuzione adattamento ottimale crea automaticamente le metriche da valutare per l’attribuzione. Nell’esempio seguente, la metrica touch è ***Hit*** e i canali sono: Consente di ***visualizzare campagne***, campagne ***e-mail*** e campagne ***SEM***.

Con questo metodo, Attribuzione adattamento ottimale crea una metrica in background per la valutazione dell’attribuzione tra i canali (ma la metrica generata automaticamente non viene mai visualizzata e non viene salvata). Nell’esempio seguente, vengono create tre metriche in cui gli hit vengono filtrati per ciascuno dei tre canali (ad esempio, Campagne *di visualizzazione*, Campagne ** e-mail e Campagne *SEM*). Questo è il più semplice perché permette alla funzione Attribuzione adattamento ottimale di creare le metriche per voi.

![](assets/attrib_touch_add_dims.png)

**Opzione 2: Crea una metrica**.

Nella seconda opzione, potete creare e salvare le metriche per i canali che desiderate valutare filtrando un canale specifico. Di seguito è riportato un esempio di tale metrica.

![](assets/attrib_create_metric.png)

Quindi, invece di immettere una metrica touch e elementi dimensione per i canali, puoi fare clic sulla barra dei menu nella visualizzazione e selezionare **Input** > **Aggiungi canale** , quindi selezionare le metriche create.

![](assets/attrib_results_2.png)

Vedere l&#39;esempio del secondo metodo riportato di seguito. I risultati di entrambe le opzioni sono identici.
