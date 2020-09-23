---
description: Questo file funziona non solo come un foglio di lavoro ma anche come un record delle vostre decisioni sull'esperimento.
solution: Analytics,Analytics
title: Foglio di calcolo di progettazione di esperimenti
topic: Data workbench
uuid: bcb11e39-9cbd-400c-af30-4b1c85e7f218
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 0%

---


# Foglio di calcolo di progettazione di esperimenti{#experiment-design-spreadsheet}

Questo file funziona non solo come un foglio di lavoro ma anche come un record delle vostre decisioni sull&#39;esperimento.

Se avete bisogno di aiuto nella progettazione dell&#39;esperimento, potete utilizzare il foglio di calcolo della progettazione dell&#39;esperimento (denominato VS Controlled Experiment Design.xls per impostazione predefinita) fornito da  Adobe.

Il foglio di calcolo della progettazione dell&#39;esperimento può fornire utili inferenze statistiche solo quando la metrica in questione è definita come percentuale di visitatori che soddisfano alcuni criteri. In altre parole, è utile solo quando si esegue il test di un&#39;ipotesi metrica basata sui visitatori.

**Per progettare l&#39;esperimento utilizzando il file di progettazione dell&#39;esperimento**

1. Se disponete dell&#39;accesso dell&#39;amministratore ai server Web o ai server applicazione, individuate la cartella di [!DNL Sensor] installazione su qualsiasi [!DNL Sensor] computer del cluster Web. Se non disponete dell&#39;accesso dell&#39;amministratore, contattate il vostro account manager  Adobe per richiedere il file.
1. Aprite il file VS Controlled Experiment Design.xls. Se lo desiderate, potete rinominare il file.

   Il foglio di calcolo riportato nella pagina seguente è un esempio di come si potrebbe completare il foglio di calcolo quando si prepara a testare le ipotesi di esempio utilizzate in questa guida.

   ![](assets/experimentdesigntop.png)

   ![](assets/experimentdesignmiddle.png)

   ![](assets/experimentdesignbottom.png)

1. Immettete il testo o i valori per tutti i campi in blu in questo file, descritti nella tabella seguente. I campi calcolati sono definiti nella seconda tabella.

<table id="table_C343F7A4BF3D4E0E9A5E9739EC7C2E10"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> In questo campo... </th> 
   <th colname="col2" class="entry"> Specifica </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Titolo esperienza </td> 
   <td colname="col2"> Un nome descrittivo per l'esperimento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Descrizione dell'esperimento </td> 
   <td colname="col2"> Una descrizione testuale dell’esperimento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metric in corso di studio </td> 
   <td colname="col2"> <p>Nome della metrica su cui si basa l’esperimento. </p> <p>Esempio: Conversione visitatori </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Definizione metrica </td> 
   <td colname="col2"> <p>La definizione della metrica su cui si basa l'esperimento. </p> <p>Formato: Visitatori[X]/Visitatori </p> <p>Esempio: <span class="filepath"> Visitatori[URI='conversionpage.asp']/Visitatori</span></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ora di inizio prevista </td> 
   <td colname="col2"> Data e ora in cui iniziare l'esperimento. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ora di fine prevista </td> 
   <td colname="col2"> Data e ora in cui si desidera che l’esperimento termini. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Selezioni applicabili </td> 
   <td colname="col2"> (Facoltativo) Il nome della dimensione e il set di elementi o l'intervallo per il quale desiderate segmentare ulteriormente il set di dati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> URI di prova </td> 
   <td colname="col2"> URI coinvolti nell'ipotesi. Definite gli URI correnti per il gruppo di controllo e gli URI alternativi creati o che verranno creati per i gruppi di test. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Metriche previste per le selezioni delle applicazioni </td> 
   <td colname="col2"> Intestazione per i valori di metrica previsti per il sito Web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numero medio di visitatori per giorno </td> 
   <td colname="col2"> Numero medio di visitatori al giorno nel sito Web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Conversione visitatori </td> 
   <td colname="col2"> Il tasso di conversione del visitatore medio per il sito Web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Sperimentazione Determinerà se il nome della metrica per i gruppi di test è ... </td> 
   <td colname="col2"> Intestazione per la modalità di confronto dei valori delle metriche. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Maggiore del valore per il gruppo di controllo? </td> 
   <td colname="col2"> Impostate questo campo su True se desiderate che sia possibile concludere che la metrica del gruppo di test è aumentata durante l'esperimento. Impostare questo campo su False per ridurre il numero di visitatori necessari per trarre delle conclusioni.  Adobe consiglia di impostarlo su True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Minore del valore per il gruppo di controllo? </td> 
   <td colname="col2"> Impostate questo campo su True se desiderate che la metrica del gruppo di test sia diminuita durante l'esperimento.  Adobe consiglia di impostarlo su True. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Di almeno (livello di rilevamento) </td> 
   <td colname="col2"> Percentuale in base alla quale si desidera che la metrica per il gruppo di test sia maggiore o minore di quella per il gruppo di controllo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Con un livello di confidenza di almeno </td> 
   <td colname="col2"> Livello di confidenza desiderato per i valori del gruppo di test. Il livello di confidenza determina il numero di falsi positivi per misurare la probabilità che l'aspettativa dichiarata sia vera. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> e un livello di potenza </td> 
   <td colname="col2"> Livello di potenza desiderato per i valori del gruppo di test. Il livello di potenza determina il numero di falsi negativi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> % dei visitatori </td> 
   <td colname="col2"> Indicato per la percentuale di visitatori. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gruppo di test </td> 
   <td colname="col2"> Percentuale di visitatori che desiderate includere nel gruppo di test. È possibile riprodurre con questo numero fino a quando il valore nel campo Totale (solitamente 100%) della sezione Visitatori è uguale o superiore al valore nel campo Minimo visitatori richiesti (Test+Gruppi di controllo), entrambi descritti nella tabella seguente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gruppo di controllo </td> 
   <td colname="col2"> Percentuale di visitatori che si desidera includere nel gruppo di controllo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Altre note di progettazione </td> 
   <td colname="col2"> Eventuali note da salvare come riferimento futuro. </td> 
  </tr> 
 </tbody> 
</table>

I campi rimanenti sono calcolati in base ai valori immessi e descritti nella tabella seguente.

| Campo | Descrizione |
|---|---|
| Metriche previste per le selezioni delle applicazioni | Intestazione per i valori di metrica previsti per il sito Web. |
| Visitatori previsti per periodo | Questo campo viene normalmente calcolato automaticamente dal foglio di calcolo. Si basa sul presupposto che nella maggior parte dei giorni il sito Web riceva più visitatori che visitatori di ritorno. In caso contrario, il calcolo di questa cella deve essere sovrascritto con il numero effettivo di visitatori previsto durante l’esperimento. |
| Valutazione Z calcolata per errore di tipo I | Il punteggio Z per un risultato falso positivo. Si tratta di un calcolo statistico intermedio. |
| Valutazione Z calcolata per errore di tipo II | Il punteggio Z per un risultato negativo falso. Si tratta di un calcolo statistico intermedio. |
| Visitatori minimi richiesti (Test+Gruppi Di Controllo) | Numero minimo di visitatori necessari per soddisfare il livello di confidenza, il livello di potenza e la valutazione Z specificati, espressi in percentuale del valore nel campo Visitatori previsti per periodo. |
| Visitatori minimi richiesti (Test+Gruppi Di Controllo) | Numero minimo di visitatori necessari all’esperimento per soddisfare il livello di confidenza, il livello di alimentazione e il punteggio Z specificati. Questo valore deve essere minore o uguale al valore nel campo Totale (solitamente 100%) della sezione Visitatori. |
| Tempo di sperimentazione minimo (giorni) | Numero minimo di giorni necessari per eseguire l&#39;esperimento per soddisfare il livello di confidenza, il livello di potenza e il punteggio Z specificati. Questo numero calcolato è soggetto agli stessi problemi discussi nel campo Visitatori previsti per periodo. Nel caso di un sito Web con molti visitatori di ritorno, il campo Tempo di sperimentazione minimo (Giorni) rappresenta il numero previsto di giorni necessari per visualizzare un numero di visitatori univoci uguale al valore nel campo Visitatori minimi richiesti. |
| Visitatori | Intestazione per i valori dei visitatori. |
| Gruppo di test | Numero di visitatori necessari nel gruppo di test. |
| Gruppo di controllo | Numero di visitatori necessari nel gruppo di controllo. |
| Totale (Solitamente 100%) | Numero totale di visitatori necessari per l’esperimento. Questo valore deve essere uguale o maggiore del valore nel campo Visitatori minimi richiesti (Test+Gruppi di controllo). |
| Precisione del gruppo di test (a livello di confidenza di Target) | Percentuale che indica che esiste una probabilità uguale al livello di confidenza specificato per cui il valore misurato della metrica calcolata per il gruppo di test sarà all&#39;interno di questa percentuale del suo valore reale. |
| Precisione del gruppo di controllo (a livello di confidenza di Target) | Percentuale che indica che esiste una probabilità pari al livello di confidenza specificato che il valore misurato della metrica calcolata per il gruppo di controllo sarà all&#39;interno di questa percentuale del suo valore reale. |
| Punteggio Z (a precisione di destinazione) | Numero di deviazioni standard un dato valore è dalla media di prova. |
| Livello di confidenza reale (a intervallo di destinazione) | Il livello di confidenza raggiunto per l&#39;esperimento. Il livello di confidenza misura la probabilità che l&#39;aspettativa dichiarata sia vera. |
| Intervallo effettivo (a livello di confidenza Target) | L&#39;intervallo di confidenza raggiunto per l&#39;esperimento, che fornisce un intervallo stimato di valori che probabilmente includerà un parametro popolazione sconosciuto. Questo intervallo viene calcolato da un dato insieme di dati di esempio. |

È necessario esaminare il valore nel campo Visitatori minimi richiesti (Test+Gruppi di controllo). . .

![](assets/Experiment_Design_Min_Visitors.png)

e confrontalo con il valore nel campo Totale della [!DNL Visitors] colonna.

![](assets/Experiment_Design_Total_Visitors.png)

Affinché l’esperimento sia statisticamente valido, il valore nel campo Totale (solitamente 100%) deve essere uguale o maggiore del valore nel campo Visitatori minimi richiesti (Test+Gruppi di controllo).

Dati gli input forniti, il foglio di lavoro di esempio mostra che 10.475 visitatori devono partecipare a questo esperimento per raggiungere il tasso di confidenza del 95% (che è la confidenza minima suggerita per qualsiasi esperimento controllato, anche se è possibile aumentare questo numero). L&#39;esperimento attualmente progettato include 30.000 visitatori, che supera di gran lunga il numero minimo di visitatori richiesto.

Se mantenete lo stesso numero di giorni, potete aumentare il livello di confidenza fintanto che il numero totale di visitatori continua a raggiungere o superare il minimo richiesto.

1. Salvate il file per i record e quindi utilizzate le informazioni del file per configurare l&#39;esperimento utilizzando il foglio di calcolo di configurazione dell&#39;esperimento. Per ulteriori informazioni su questo foglio di calcolo, consultate [Configurazione e distribuzione dell&#39;esperimento](../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).
