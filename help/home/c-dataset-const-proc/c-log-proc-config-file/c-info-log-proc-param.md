---
description: Collegamenti a informazioni aggiuntive su parametri specifici nel file Log Processing.cfg .
title: Parametri di elaborazione del registro
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
exl-id: f373e954-6827-4afa-9557-73e0a884a602
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 2%

---

# Parametri di elaborazione del registro{#log-processing-parameters}

Collegamenti a informazioni aggiuntive su parametri specifici nel file Log Processing.cfg .

<!--
c_data_filters.xml
-->

## Filtri dati {#data-filters}

I filtri definiti nel file [!DNL Log Processing.cfg] includono quanto segue:

* Ora di fine
* Soglia hash
* Ora di inizio

Il filtro definito da questi parametri si verifica dopo che le voci di registro lasciano i decoder e dopo le trasformazioni ma prima della loro valutazione da parte di [!DNL Log Entry Condition]. In generale, la modifica di uno qualsiasi di questi parametri determina modifiche alla composizione del set di dati.

La tecnica consigliata per l’utilizzo delle origini dati [!DNL Sensor] per la creazione di un set di dati che copre un periodo di tempo specifico consiste nell’utilizzare i parametri Ora di inizio e Ora di fine per il set di dati.

L’utilizzo dei parametri Ora di inizio e Ora di fine è preferibile ad altre tecniche, ad esempio lo spostamento dei file di registro per separarli in base alla directory. Impostando l’ora di inizio e di fine del set di dati, il server di Data Workbench utilizza automaticamente solo le voci di registro che si sono verificate nell’intervallo specificato. Presupponendo che l’ora di fine sia passata, il server di Data Workbench in genere aggiorna il set di dati utilizzando lo stesso set di voci di registro, anche se il set di dati viene aggiornato, ad esempio, aggiungendo una nuova trasformazione.

<!--
c_log_entry_con.xml
-->

## Voce di registro

In sostanza, si tratta di un processo di filtraggio sulle voci di registro disponibili. Se [!DNL Log Entry Condition] restituisce un valore false, la voce di registro viene filtrata dal set di voci di registro disponibili.

Il [!DNL Log Entry Condition] è descritto tramite l&#39;uso di operazioni di condizione (vedere [Condizioni](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) e può utilizzare uno qualsiasi dei campi di input raccolti da [!DNL Sensor] (vedere la *Data Workbench [!DNL Sensor] Guide* ) o tutti i campi estesi prodotti dalle trasformazioni contenute nel file [!DNL Log Processing.cfg] per definire le condizioni di prova. [!DNL Log Entry] le condizioni vengono applicate durante l&#39;elaborazione del registro e, facoltativamente, possono essere applicate durante la trasformazione.

Questo esempio illustra l’utilizzo di [!DNL log entry condition] per i dati dei siti web. Puoi utilizzare [!DNL Log Entry Condition] per creare set di dati che si concentrano su una parte specifica del sito web o sui visitatori che eseguono alcune azioni specifiche sul sito.

In questo esempio [!DNL Log Entry Condition] viene creato un set di dati che include solo le voci di registro che fanno parte dell’archivio del sito. Utilizzando il [!DNL RECondition test] con il pattern corrispondente [!DNL "/store/.*"] e il campo [!DNL cs-uri-stem] come input per l’espressione regolare, nel set di dati vengono incluse solo le pagine web che iniziano con la stringa [!DNL "/store/"].

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## Divisione chiave {#key-split}

Il numero di ID di tracciamento nel set di dati viene aumentato artificialmente, ma il numero totale di voci di registro elaborate dal server di Data Workbench non viene aumentato artificialmente, mantenendo così il numero totale di eventi numerabili nel set di dati. Dopo la suddivisione dei dati per un singolo elemento, i dati sono associati per sempre a due ID di tracciamento diversi e non possono essere correlati.

Ad esempio, se lavori con dati web, ogni ID di tracciamento rappresenta un visitatore univoco. Se abiliti la suddivisione chiave, i visitatori nel set di dati con grandi quantità di dati evento vengono suddivisi in più visitatori. Mentre il numero di visitatori nel set di dati viene aumentato artificialmente, il numero totale di eventi numerabili come le visualizzazioni di pagina o le prenotazioni non viene aumentato artificialmente. Dopo la suddivisione, i dati per i sottovisitatori non possono essere correlati.

La suddivisione delle chiavi utilizza un algoritmo probabilistico. Di conseguenza, esiste un compromesso tra l’utilizzo della memoria, la probabilità di errore, la soglia di suddivisione chiave ( [!DNL Split Key Bytes]) e la dimensione del set di dati. Con le impostazioni consigliate (come indicato di seguito), il tasso di errore è basso. Di quegli elementi i cui dati evento superano la soglia di suddivisione chiave, circa 1 su 22.000 (di solito meno di 1 per set di dati) avranno alcuni dei loro dati troncati anziché suddivisi.

I valori consigliati per ciascun parametro (senza e con suddivisione chiave) sono riportati nella tabella seguente.

| Parametro | Nessuna divisione tasti | Divisione tasti |
|---|---|---|
| Byte chiave massimi del gruppo | 1e6 | 2e6 |
| Spazio a blocchi della chiave di divisione | 6e6 | 6e6 |
| Byte chiave divisi | 0 | 1e6 |
| Rapporto spazio chiave diviso | 10 | 10 |

[!DNL Group Maximum Key Bytes] specifica la quantità massima di dati evento che è possibile elaborare per un singolo ID di tracciamento. I dati che superano questo limite vengono filtrati dal processo di costruzione del set di dati. [!DNL Split Key Bytes] rappresenta il numero di byte in cui un singolo ID di tracciamento viene suddiviso in più elementi. Gli elementi vengono suddivisi a circa questo numero di byte in base a una distribuzione di probabilità. [!DNL Split Key Space Ratio] e  [!DNL Split Key Bucket Space] controllare l&#39;utilizzo della memoria e la frequenza di errore della suddivisione chiave.

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes],  [!DNL Split Key Bytes],  [!DNL Split Key Space Ratio] e  [!DNL Split Key Bucket Space] tutti devono essere dichiarati per il corretto funzionamento della suddivisione delle chiavi. Non modificare i valori di questi parametri senza consultare un Adobe.
