---
description: Una dimensione numerica è costituita da elementi numerici ordinati e presenta una relazione uno-a-molti con la dimensione conteggiata superiore.
title: Dimensioni numeriche
uuid: 19fab770-1535-41b2-bad1-811eba5f3575
exl-id: 69a4dfa6-8402-4c2b-8b04-e6e1a0fd5ccb
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '990'
ht-degree: 1%

---

# Dimensioni numeriche{#numeric-dimensions}

Una dimensione numerica è costituita da elementi numerici ordinati e presenta una relazione uno-a-molti con la dimensione conteggiata superiore.

È possibile considerare una dimensione numerica come una rappresentazione delle proprietà numeriche degli elementi della dimensione padre. Ad esempio, se lavori con i dati web, puoi definire la dimensione numerica Entrate sessione , che definisce una quantità di ricavi, in dollari, per ogni sessione nella dimensione Sessione. Ogni sessione ha un singolo importo di ricavi associati, ma diverse sessioni possono avere lo stesso importo di ricavi associati. Pertanto, la dimensione Ricavo sessione ha una relazione uno-a-molti con la dimensione Sessione.

Le dimensioni numeriche vengono spesso utilizzate per definire metriche che sommano valori, contano occorrenze di una condizione o individuano un valore minimo o massimo. Ad esempio, una metrica denominata &quot;Entrate&quot; può essere definita utilizzando la dimensione Ricavo sessione : sum(Session_Revenue, Session). Definita in questo modo, la metrica Ricavo fornisce l’importo totale dei ricavi per le sessioni selezionate.

Le dimensioni numeriche non possono essere elementi padre di altre dimensioni.

Le dimensioni numeriche sono definite dai seguenti parametri:

<table id="table_15B849DD0BFC4D57AD6CF28898901324"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> impostazione predefinita </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descrittivo della dimensione così come viene visualizzata all’interno di Data Workbench. Il nome della dimensione non può includere un trattino (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Valori clip </td> 
   <td colname="col2"> True o false. Specifica se il valore di input (dopo Operazione ) deve essere ritagliato tra i valori di Min e Max. Se Valori clip è true, il valore viene ritagliato in base a tale intervallo. Se Valori clip è false, non viene restituito alcun valore per l'elemento della dimensione padre. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla dimensione estesa. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione </td> 
   <td colname="col2"> Condizioni in cui il campo di input contribuisce alla creazione della dimensione numerica. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensione fissa </td> 
   <td colname="col2"> True o false. Controlla il numero di elementi in una dimensione (cardinalità). Se true, nella dimensione sono inclusi tutti gli elementi da Min a Max. Se false, le dimensioni della dimensione crescono man mano che vengono aggiunti i valori. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascosto </td> 
   <td colname="col2"> Determina se la dimensione viene visualizzata nell’interfaccia di Data Workbench. Per impostazione predefinita, questo parametro è impostato su false. Se, ad esempio, la dimensione deve essere utilizzata solo come base di una metrica, puoi impostare questo parametro su true per nascondere la dimensione dalla visualizzazione di Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresso </td> 
   <td colname="col2"> <p>Il valore da utilizzare con l'operazione specificata o il valore di input per il quale si desidera contare le occorrenze. </p> <p> Se questo campo è un vettore di stringhe, la valutazione si verifica per ogni elemento del vettore. Ad esempio, un vettore con lunghezza 3 e un'operazione di COUNT aggiunge 3 al conteggio. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Min </td> 
   <td colname="col2"> Limite inferiore al risultato della dimensione finale. </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Max </td> 
   <td colname="col2"> Limite superiore del risultato della dimensione finale. </td> 
   <td colname="col3"> 1e6 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Offset </td> 
   <td colname="col2"> Consultare Scala in questa tabella. </td> 
   <td colname="col3"> 0 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Funzionamento </td> 
   <td colname="col2"> <p>Le operazioni disponibili sono le seguenti: </p> <p> 
     <ul id="ul_E04733E5E8824A2BAAB90D9356078D99"> 
      <li id="li_CAEE9167D45540BEAC538345F250B509"> CONTEGGIO: Viene utilizzato il numero totale di valori non vuoti nel campo <span class="wintitle"> Input</span> in tutte le voci di registro che soddisfano la condizione della dimensione. Se il campo <span class="wintitle"> Input</span> è un campo vettoriale, viene conteggiato il numero totale di valori non vuoti in ciascuna voce di registro. </li> 
      <li id="li_64A4D671E78642BD9A9334F8098450B9"> PRIMO NONBLANK: Viene utilizzato il primo valore di input non vuoto, indipendentemente dal fatto che provenga dalla prima voce di registro. Se <span class="wintitle"> Input</span> è un campo vettoriale, viene utilizzata la prima riga del vettore per la voce di registro pertinente. Se il valore non è un numero, non viene utilizzato alcun valore. </li> 
      <li id="li_C967964729BD4A638FF78D8883CE513F"> PRIMA RIGA: Viene utilizzato il valore della prima voce di registro relativa all’elemento dimensione padre, anche se l’input è vuoto. Se <span class="wintitle"> Input</span> è un campo vettoriale, viene utilizzata la prima riga del vettore per la voce di registro pertinente. Se questo valore è vuoto o non è un numero, o se la voce di registro pertinente non soddisfa la condizione della dimensione, non viene utilizzato alcun valore. </li> 
      <li id="li_74171B17F480478B8547E1A361B22DA4"> ULTIMO NONBLANK: Viene utilizzato l’ultimo valore di input non vuoto, indipendentemente dal fatto che provenga dall’ultima voce di registro. Se <span class="wintitle"> Input</span> è un campo vettoriale, viene utilizzata la prima riga del vettore per la voce di registro pertinente. Se il valore non è un numero, non viene utilizzato alcun valore. </li> 
      <li id="li_1253ECF507BD4BBF97CBB2FA12915045"> ULTIMA RIGA: Viene utilizzato il valore per l’ultima voce di registro relativa all’elemento dimensione padre, anche se l’input è vuoto. Se <span class="wintitle"> Input</span> è un campo vettoriale, viene utilizzata la prima riga del vettore per la voce di registro pertinente. Se questo valore è vuoto o non è un numero, o se la voce di registro pertinente non soddisfa la condizione della dimensione, non viene utilizzato alcun valore. </li> 
      <li id="li_20819E3944544F98853D6A02814F47B2"> SOMMA: Viene utilizzato il totale di tutti i valori numerici nel campo <span class="wintitle"> Input</span> in tutte le voci di registro che soddisfano le condizioni della dimensione. Se non sono presenti voci di registro di questo tipo o non sono stati trovati valori numerici, viene utilizzato il valore numerico 0. </li> 
      <li id="li_086C2E57604B4645A9203A984C6F9A04">MIN o MAX: Viene utilizzato il valore numerico minimo o massimo trovato nel campo <span class="wintitle"> Input</span> in tutte le voci di registro che soddisfano le condizioni della dimensione. Se non ci sono voci di registro di questo tipo o se non ci sono valori numerici, non viene utilizzato alcun valore. </li> 
     </ul> </p> <p> <p>Nota:  È necessario specificare un’operazione per garantire che la dimensione sia definita come previsto. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elemento padre </td> 
   <td colname="col2"> Nome della dimensione padre. Qualsiasi dimensione conteggiata può essere una dimensione superiore. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Scala </td> 
   <td colname="col2"> <p>Per ottenere il valore ordinale della dimensione, il risultato dell'operazione viene trasformato come segue: </p> <p> (scala * input) + offset </p> </td> 
   <td colname="col3"> 1,0 </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Se [!DNL Operation] non restituisce alcun valore, o [!DNL Clip Values] è false e il valore non è compreso tra [!DNL Min] e [!DNL Max], nessun elemento della dimensione numerica è correlato all’elemento della dimensione padre.

Questo esempio illustra la definizione di una dimensione numerica utilizzando i dati evento raccolti dal traffico del sito web. Questa dimensione numerica, denominata &quot;Contatore visualizzazione annuncio&quot;, conta il numero di volte in cui il visitatore visualizza un annuncio durante una determinata sessione. Il presupposto è che tutte le risorse pubblicitarie siano richieste dal server web con ad= come parte della cs-uri-query. Nell’esempio, il numero di volte (COUNT) in cui al visitatore viene presentato un annuncio è il valore di interesse, non il valore effettivo nel campo .

![](assets/cfg_Transformation_Dim_Numeric.png)
