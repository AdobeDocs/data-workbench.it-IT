---
description: Una dimensione semplice ha una relazione uno-a-molti con la sua dimensione contabile padre.
solution: Analytics
title: Dimensioni semplici
topic: Data workbench
uuid: 3bca2354-02c4-4739-a7da-acccdb0efdfd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensioni semplici{#simple-dimensions}

Una dimensione semplice ha una relazione uno-a-molti con la sua dimensione contabile padre.

Una dimensione semplice è sempre figlia di una dimensione numerabile. È possibile considerare una dimensione semplice come una rappresentazione di una proprietà degli elementi nella dimensione padre. Ad esempio, se lavori con dati Web, puoi definire la dimensione Referente visitatore, che è una dimensione semplice con una dimensione padre del Visitatore. Rappresenta il primo referente HTTP per ogni visitatore nella dimensione Visitatore. Ogni visitatore nella dimensione Visitatore dispone di un solo referente, ma molti possono avere lo stesso referente visitatore. Pertanto, la dimensione Referente visitatore ha una relazione uno-molti con la dimensione Visitatore.

Le dimensioni semplici sono definite dai seguenti parametri:

<table id="table_E6F729DFA226459DBFC1776CE8CB81F8"> 
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
   <td colname="col2"> Nome descrittivo della dimensione così come viene visualizzata nel workbench dati. Il nome della dimensione non può includere un trattino (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla dimensione estesa. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione </td> 
   <td colname="col2"> Condizioni in cui creare la relazione tra il padre e il valore del campo di input. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascosto </td> 
   <td colname="col2"> Determina se la dimensione viene visualizzata nell'interfaccia workbench dati. Per impostazione predefinita, questo parametro è impostato su false. Se, ad esempio, la dimensione deve essere utilizzata solo come base di una metrica, è possibile impostare questo parametro su true per nascondere la dimensione dalla visualizzazione del workbench dati. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresso </td> 
   <td colname="col2"> Campo di valori correlato alla dimensione padre (Parent). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Carica file </td> 
   <td colname="col2"> <p>Facoltativo. Un file di valori disponibili per la relazione. Potete utilizzare un file di caricamento quando si applica una delle seguenti condizioni: </p> <p> 
     <ul id="ul_056C4A8E46AA479397DC63173C035D5C"> 
      <li id="li_C26EB5A4AB3C4BEB8EB3A217A5A2377E"> I valori hanno un ordinamento specifico che si desidera mantenere nella visualizzazione del workbench dati. Ad esempio, potrebbe essere utile creare una dimensione Trimestre i cui elementi (i trimestri dell'anno) vengono sempre visualizzati in ordine cronologico. </li> 
      <li id="li_5D4DF56BC6124D038A7260131B1F3DB3"> Si desidera creare dei segnaposto per i valori che potrebbero non essere presenti nei dati ma che devono essere visualizzati nella visualizzazione del workbench dati. </li> 
     </ul> </p> <p> Se viene rilevato un valore che non è presente nel file, viene aggiunto alla fine dei valori quando viene visualizzato nel workbench dati. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Funzionamento </td> 
   <td colname="col2"> <p>Le operazioni disponibili sono le seguenti: </p> <p> 
     <ul id="ul_88AE4279413C42609D8B53EC64B5E913"> 
      <li id="li_DD9623D006844BC28B2AAA8E12AA04E1"> PRIMO NONBLANK: Viene utilizzato il primo valore di input non vuoto, indipendentemente dal fatto che provenga dalla prima voce di registro. Se Input è un campo vettoriale, viene utilizzata la prima riga del vettore per la voce di registro corrispondente. </li> 
      <li id="li_0FBE7F0B7B9744D994ECEDAA08F0045C"> PRIMA RIGA: Viene utilizzato il valore per la prima voce di registro relativa all’elemento dimensione padre, anche se l’input è vuoto. Se Input è un campo vettoriale, viene utilizzata la prima riga del vettore per la voce di registro corrispondente. Se questo valore è vuoto o non è un numero, o se la voce di registro pertinente non soddisfa la condizione della dimensione, non viene utilizzato alcun valore. </li> 
      <li id="li_C17190BC699D4A099DC5326C07D1044D"> ULTIMO NONBLANK: Viene utilizzato l’ultimo valore di input non vuoto, indipendentemente dal fatto che provenga dall’ultima voce di registro. Se Input è un campo vettoriale, viene utilizzata la prima riga del vettore per la voce di registro corrispondente. </li> 
      <li id="li_00BAE86F12004C098F6A455908DB7062"> ULTIMA RIGA: Viene utilizzato il valore per l’ultima voce di registro relativa all’elemento dimensione padre, anche se l’input è vuoto. Se Input è un campo vettoriale, viene utilizzata la prima riga del vettore per la voce di registro corrispondente. Se questo valore è vuoto o non è un numero, o se la voce di registro pertinente non soddisfa la condizione della dimensione, non viene utilizzato alcun valore. </li> 
     </ul> </p> <p> <p>Nota:  Se l'operazione non genera alcun valore o un valore vuoto per una particolare voce di registro, l'elemento corrispondente della dimensione padre si relazionerà all'elemento "None" della dimensione semplice. </p> </p> <p> È necessario specificare un'operazione per garantire che la dimensione sia definita come previsto. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elemento padre </td> 
   <td colname="col2"> Nome della dimensione padre. Qualsiasi dimensione numerabile può essere una dimensione padre. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Questo esempio illustra la definizione di una dimensione semplice utilizzando i dati evento raccolti dal traffico del sito Web e da un file di caricamento.

Considerate l&#39;esempio di un sondaggio dei cookie Girl Scout preferiti dai visitatori del sito. Una pagina Web acquisisce questo voto e lo restituisce al server Web nel cookie della coppia nome-valore. Viene contato solo un voto per visitatore, ma i visitatori possono cambiare idea e votare di nuovo, se lo desiderano. Si tratta di una relazione uno-a-molti: un visitatore può avere molti voti, ma ogni voto è associato a un solo visitatore. Pertanto, il padre della dimensione è il visitatore (solo un voto per visitatore) e l&#39;operazione è LAST ROW (in modo che possano cambiare idea e votare di nuovo).

I segnaposti devono esistere per tutti i tipi di cookie in modo che i cookie che non ricevono voti siano visualizzati nel workbench dati. Per questi motivi, è stato definito un file di caricamento che contiene l&#39;elenco dei tipi di cookie che possono essere selezionati. Il contenuto di questo file, salvato in un file denominato [!DNL cookietypes.txt], ha un aspetto simile al seguente:

Tesori animali

Caramel Delights

Pasticceria Limone

Patatine al burro di arachidi

Tasti di scelta rapida

Punte sottili

La dimensione finale è definita come illustrato di seguito:

![](assets/cfg_Transformation_Dim_Simple.png)

