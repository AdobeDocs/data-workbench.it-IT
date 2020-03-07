---
description: Una dimensione "molti-a-molti" ha una relazione molti-a-molti con la sua dimensione contabile padre.
solution: Analytics
title: Dimensioni molte-molte
topic: Data workbench
uuid: 42c909e8-1228-4210-9406-ffc0d92372fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensioni molte-molte{#many-to-many-dimensions}

Una dimensione &quot;molti-a-molti&quot; ha una relazione molti-a-molti con la sua dimensione contabile padre.

Potete considerare una dimensione da molti a molti come una rappresentazione di un insieme di valori per ogni elemento della dimensione padre. Ad esempio, la frase di ricerca di molte dimensioni è una dimensione a livello di sessione (ha un elemento padre della sessione). Rappresenta il set di frasi di ricerca associate a ciascuna sessione nella dimensione Sessione. Una singola frase di ricerca può essere utilizzata in qualsiasi numero di sessioni, e una singola sessione può includere zero o più frasi di ricerca. Pertanto, la dimensione Search Phrase ha una relazione molti-a-molti con la dimensione Session.

Le dimensioni molti-molti sono definite dai seguenti parametri:

<table id="table_A6D495008DFF4DD28A3ECD718D775E54"> 
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
   <td colname="col2"> Nome descrittivo della dimensione così come viene visualizzata all'utente nel workbench dati. Il nome della dimensione non può includere un trattino (-). </td> 
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
   <td colname="col2"> <p>Valore correlato alla dimensione padre (Parent). Se questo campo è un vettore di stringhe, ogni elemento del vettore ha una propria relazione con l'elemento padre. </p> <p> <p>Nota:  Se il valore di input per ogni voce di registro per un elemento della dimensione padre è vuoto, nessun elemento della dimensione molti-a-molti sarà correlato a tale elemento della dimensione padre. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elemento padre </td> 
   <td colname="col2"> Nome della dimensione padre. Qualsiasi dimensione numerabile può essere una dimensione padre. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Questo esempio illustra la definizione di una dimensione &quot;molti a molti&quot; utilizzando i dati evento raccolti dal traffico del sito Web. Questa dimensione a molti, denominata &quot;Prodotto selezionato&quot;, fa riferimento alle sessioni per i prodotti acquistati dal visitatore durante tale sessione. Il campo x-products contiene un vettore di valori, ciascuno dei quali è associato a una visualizzazione di pagina, che a sua volta è associata a una sessione.

![](assets/cfg_Transformation_Dim_ManytoMany.png)

Creando tale trasformazione, puoi creare una visualizzazione nel workbench dati che illustri la relazione tra la dimensione del prodotto selezionata e il numero di sessioni che coinvolgono ciascuno dei prodotti.
