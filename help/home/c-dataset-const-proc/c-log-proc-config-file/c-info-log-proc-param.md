---
description: Collegamenti a informazioni aggiuntive su parametri specifici nel file Log Processing.cfg.
solution: Analytics
title: Parametri di elaborazione del registro
topic: Data workbench
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Parametri di elaborazione del registro{#log-processing-parameters}

Collegamenti a informazioni aggiuntive su parametri specifici nel file Log Processing.cfg.

<!--
c_data_filters.xml
-->

## Filtri dati {#data-filters}

I filtri definiti nel [!DNL Log Processing.cfg] file includono quanto segue:

* Ora di fine
* Soglia hash
* Ora di inizio

Il filtraggio definito da questi parametri si verifica dopo che le voci di registro lasciano i decodificatori e dopo le trasformazioni, ma prima della loro valutazione da parte del [!DNL Log Entry Condition]. In generale, la modifica di uno di questi parametri determina modifiche alla composizione del set di dati.

La tecnica consigliata per utilizzare le origini [!DNL Sensor] dati per creare un dataset che copre un periodo di tempo specifico consiste nell&#39;utilizzare i parametri Ora di inizio e Ora di fine per il dataset.

L’utilizzo dei parametri Ora di inizio e Ora di fine è preferibile ad altre tecniche, ad esempio lo spostamento di file di registro per separarli in base alla directory. Impostando l&#39;ora di inizio e di fine per il dataset, il server workbench dati utilizza automaticamente solo le voci di registro che si sono verificate entro l&#39;intervallo specificato. Presupponendo che l&#39;ora di fine sia passata, il server workbench dati in genere aggiorna il dataset utilizzando lo stesso set di voci di registro, anche se il dataset viene aggiornato, ad esempio, aggiungendo una nuova trasformazione.

<!--
c_log_entry_con.xml
-->

## Voce di registro

In sostanza, si tratta di un processo di filtraggio sulle voci di registro disponibili. Se [!DNL Log Entry Condition] restituisce un valore false, la voce di registro viene filtrata fuori dal set di voci di registro disponibili.

La descrizione [!DNL Log Entry Condition] viene fornita mediante l&#39;utilizzo di operazioni di condizione (vedere [Condizioni](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) e può utilizzare uno qualsiasi dei campi di input raccolti da [!DNL Sensor] (vedere la *Guida[!DNL Sensor]di Workbench dati* ) o tutti i campi estesi generati dalle trasformazioni contenute nel [!DNL Log Processing.cfg] file per definire le condizioni di prova. [!DNL Log Entry] le condizioni vengono applicate durante l&#39;elaborazione del registro e, facoltativamente, possono essere applicate durante la trasformazione.

Questo esempio illustra l’utilizzo di [!DNL log entry condition] per i dati del sito Web. È possibile utilizzare [!DNL Log Entry Condition] per creare set di dati incentrati su una porzione specifica del sito Web o sui visitatori che eseguono determinate azioni specifiche sul sito.

In [!DNL Log Entry Condition] questo esempio viene creato un dataset che include solo le voci di registro che fanno parte dello store del sito. Utilizzando il [!DNL RECondition test] con il pattern corrispondente [!DNL "/store/.*"] e il [!DNL cs-uri-stem] campo come input per l&#39;espressione regolare, solo le pagine Web che iniziano con la stringa [!DNL "/store/"] sono incluse nel set di dati.

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## Divisione chiave {#key-split}

Il numero di ID di tracciamento nel set di dati viene aumentato artificialmente, ma il numero totale di voci di registro elaborate dal server workbench dati non viene aumentato artificialmente, mantenendo così il numero totale di eventi calcolabili nel set di dati. Dopo la suddivisione dei dati per un singolo elemento, i dati vengono associati per sempre a due ID di tracciamento diversi e non possono essere correlati.

Ad esempio, se lavori con dati Web, ogni ID di tracciamento rappresenta un visitatore univoco. Se abilitate la suddivisione delle chiavi, i visitatori nel set di dati con grandi quantità di dati evento vengono suddivisi in più visitatori. Mentre il numero di visitatori nel set di dati viene aumentato artificialmente, il numero totale di eventi numerabili, come visualizzazioni di pagina o prenotazioni, non viene aumentato artificialmente. Dopo la suddivisione, i dati per i sottovisitatori non possono essere correlati.

La divisione delle chiavi utilizza un algoritmo probabilistico. Di conseguenza, esiste un compromesso tra utilizzo della memoria, probabilità di errore, soglia di suddivisione chiave ( [!DNL Split Key Bytes]) e dimensione del set di dati. Con le impostazioni consigliate (elencate di seguito), la frequenza di errore è bassa. Di quegli elementi i cui dati di evento superano la soglia di suddivisione chiave, circa 1 su 22.000 (in genere meno di 1 per dataset) avranno alcuni dei loro dati troncati anziché suddivisi.

I valori consigliati per ciascun parametro (senza e con divisione chiave) sono riportati nella tabella seguente.

| Parametro | Nessuna divisione tasti | Suddivisione tasti |
|---|---|---|
| Numero massimo di byte chiave del gruppo | 1e6 | 2e6 |
| Dividi spazio parentesi | 6e6 | 6e6 |
| Dividi byte chiave | 0 | 1e6 |
| Rapporto spazio chiave | 10 | 10 |

[!DNL Group Maximum Key Bytes] specifica la quantità massima di dati evento che è possibile elaborare per un singolo ID di tracciamento. I dati che superano questo limite vengono filtrati dal processo di costruzione dell&#39;insieme di dati. [!DNL Split Key Bytes] rappresenta il numero di byte in cui un singolo ID di tracciamento viene diviso in più elementi. Gli elementi vengono suddivisi a circa questo numero di byte in base alla distribuzione delle probabilità. [!DNL Split Key Space Ratio] e [!DNL Split Key Bucket Space] controllare l&#39;utilizzo della memoria e il tasso di errore della suddivisione chiave.

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes], [!DNL Split Key Bytes], [!DNL Split Key Space Ratio]e [!DNL Split Key Bucket Space] tutti devono essere dichiarati per il corretto funzionamento della suddivisione delle chiavi. Non modificate i valori di questi parametri senza consultare Adobe.

