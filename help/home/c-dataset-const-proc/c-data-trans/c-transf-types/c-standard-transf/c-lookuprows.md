---
description: La trasformazione LookupRows cerca altre voci di registro con lo stesso ID di tracciamento e imposta il valore del campo di output sul valore di un campo specificato nella riga di input.
solution: Analytics
title: LookupRows
topic: Data workbench
uuid: 4cff7cf1-00c8-4ab1-8adc-3805518226d3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# LookupRows{#lookuprows}

La trasformazione LookupRows cerca altre voci di registro con lo stesso ID di tracciamento e imposta il valore del campo di output sul valore di un campo specificato nella riga di input.

Poiché la [!DNL LookupRows] trasformazione esegue la ricerca sulle voci di registro e non sui file di ricerca, è molto simile alla [!DNL CrossRows] trasformazione. Vedere [CrossRows](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-crossrows.md#concept-fcace08804f54db397ed631cc13ff4f2).

Per funzionare, la [!DNL LookupRows] trasformazione richiede che i dati siano ordinati nel tempo e raggruppati dall&#39;ID di tracciamento nei dati di origine. Pertanto, [!DNL LookupRows] funziona solo se definito nel [!DNL Transformation.cfg] file o in un [!DNL Transformation Dataset Include] file.

Durante la revisione delle descrizioni dei parametri nella tabella seguente, tenere presente quanto segue:

* La riga di output è la riga di dati su cui la trasformazione sta lavorando in un dato momento nel tempo.
* Le righe di input sono tutte le altre righe di dati (prima, dopo o inclusa la riga di output) i cui valori del campo di input fungono da input per la trasformazione.

<table id="table_AB68A89ECD5C45F39B8433F994BBD7D8"> 
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
   <td colname="col2"> Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla trasformazione. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione </td> 
   <td colname="col2"> Limita l'output della trasformazione a determinate voci di registro. Se la condizione non è soddisfatta per una particolare voce di registro, il campo nel parametro Output valore riga di output viene lasciato invariato. L'input può ancora essere utilizzato per influenzare altre voci di registro. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione di ingresso </td> 
   <td colname="col2">Accetta l'input per la trasformazione solo da determinate righe di input. Se la condizione di <span class="wintitle"> input</span> non è soddisfatta per una particolare riga di input, il campo di input di tale riga viene ignorato e non influisce sulle altre righe di output. Tuttavia, il campo di output di tale riga viene ancora modificato in base alla condizione specificata. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input chiave riga di input </td> 
   <td colname="col2"> Nome del campo da utilizzare come chiave per le righe di input. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input valore riga di input </td> 
   <td colname="col2"> Nome del campo nella riga di input il cui valore viene copiato nel campo nel parametro Output valore riga di output, se tutte le condizioni sono soddisfatte. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Funzionamento </td> 
   <td colname="col2"> <p>Operazione che, per ogni riga di output, viene applicata a tutte le righe di input che soddisfano tutte le condizioni definite dai parametri Input <span class="wintitle"> Condition e Input Key Input</span> Row per produrre un output: 
     <ul id="ul_16FB152CB558497794DDED72A2F05CDD"> 
      <li id="li_22DA9F814E4E42D0B21E90B63A2A7A0E"> FIRST genera il valore del campo nel parametro Input riga input dal primo riga di input corrispondente nei dati (non dalla prima riga corrispondente dopo la riga di output). </li> 
      <li id="li_45E00C3DE0494A1CB5C09B942088F161"> LAST genera il valore del campo nel parametro Input riga input dall'ultima riga di input nei dati (non l'ultima riga corrispondente prima della riga di output). </li> 
     </ul> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Input chiave riga di output </td> 
   <td colname="col2"> Nome del campo da utilizzare come chiave per la riga di output. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Output valore riga di output </td> 
   <td colname="col2">Nome del campo nella riga di output il cui valore viene copiato dal campo nel parametro Input Row Value Input se tutte le condizioni sono soddisfatte. Tutte le righe di output con gli stessi <span class="wintitle"> valori x-trackingid e </span>Output Row Key Input hanno lo stesso valore Output <span class="wintitle"> valore riga di</span> output. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

I parametri Input della chiave di input, Input del valore della riga di input e Condizione di input definiscono insieme il file di ricerca per ciascun ID di tracciamento, mentre i parametri Input della chiave di output, Input del valore della riga di output e Condizione controllano ciò che viene cercato nel file e il valore memorizzato nel campo specificato da Output del valore della riga di output.

Per comprendere meglio il funzionamento della trasformazione, prendere in considerazione il seguente profilo:

* Per ogni riga di output che soddisfa la condizione e contiene un input di chiave di output non vuoto:

   * Trova la riga di input FIRST o LAST in modo che

      * la riga di input soddisfa la condizione di input, e
      * la linea x-trackingid della riga di input è uguale alla linea x-trackingid della riga di output, e
      * l&#39;input della riga di input della riga di input è uguale a Output Row Key Input della riga di output,

* e impostare Output valore riga di output della riga di output su Input valore riga di input della riga di input.

Considerazioni [!DNL LookupRows]

* I valori delle chiavi vuote non corrispondono mai a nulla. Anche se sono presenti righe di input con chiavi vuote e valori non vuoti che corrispondono al [!DNL Input Condition], un valore [!DNL Output Row Key Input] di &quot;&quot; genererà sempre un valore [!DNL Output Row Value Output] di &quot;&quot;.

* Se non è vietato dall&#39; [!DNL Input Condition], una riga potrebbe cercare se stessa se i suoi [!DNL Input Row Key Input] e [!DNL Output Row Key Input] valori sono gli stessi.

Se si dispone di più valori chiave, è possibile combinarli utilizzando una [!DNL Format] trasformazione (vedere [Formato](../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-format.md#concept-3de04869181e4694ab072b092186684b)) prima di applicare una [!DNL LookupRows] trasformazione.

Supponete di avere un sito web che ha una pagina di registrazione animale domestico, dove il nome e la razza sono inseriti, e una pagina successiva &quot;buy giocattolo&quot; dove viene utilizzato solo il nome dell&#39;animale domestico. Desiderate essere in grado di collegare il nome dell&#39;animale con la razza animale domestico inserita nella pagina di registrazione. A tal fine, potete creare la seguente [!DNL LookupRows] trasformazione:

![](assets/cfg_TransformationType_LookupRows.png)

Analizziamo questo esempio utilizzando la struttura precedente:

* Per ogni riga di output che soddisfa un valore non vuoto di cs-uri-query(nome file):

   * Trova la riga di input LAST in modo che

      * la riga di input contiene un valore non vuoto di cs-uri-query(petbreed), e
      * la linea x-trackingid della riga di input è uguale alla linea x-trackingid della riga di output, e
      * il valore di cs-uri-query(nome-petro) della riga di input è uguale al valore di cs-uri-query(nome-petro) della riga di output,

* e impostare il valore di x-pet-breed della riga di output sul valore di cs-uri-query(petbreed) della riga di input.

La [!DNL LookupRows] trasformazione utilizza il nome animale domestico (la chiave) per assicurarsi che la razza animale sia collegata sia alle pagine di registrazione animale domestico e acquistare giocattoli in modo da poter analizzare i giocattoli acquistati per ogni razza di animale domestico, anche per i visitatori con più animali domestici.
