---
description: Una dimensione da molti a molti ha una relazione da molti a molti con la sua dimensione conteggiata padre.
title: Dimensioni Many-to-Many (Da molte-a-molte)
uuid: 42c909e8-1228-4210-9406-ffc0d92372fa
exl-id: 02d1a21c-a5b4-4b58-8089-9b9c68a7b1d1
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 3%

---

# Dimensioni Many-to-Many (Da molte-a-molte){#many-to-many-dimensions}

Una dimensione da molti a molti ha una relazione da molti a molti con la sua dimensione conteggiata padre.

È possibile considerare una dimensione da molti a molti come una rappresentazione di un insieme di valori per ogni elemento della dimensione padre. Ad esempio, la frase di ricerca molte-a-molte dimensioni è una dimensione a livello di sessione (ha un elemento padre di sessione). Rappresenta il set di frasi di ricerca associate a ogni sessione nella dimensione Sessione. Una singola frase di ricerca può essere utilizzata in qualsiasi numero di sessioni e una singola sessione può includere zero o più frasi di ricerca. Pertanto, la dimensione della frase di ricerca ha una relazione molti-a-molti con la dimensione Sessione.

Le dimensioni da molti a molti sono definite dai seguenti parametri:

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
   <td colname="col2"> Nome descrittivo della dimensione così come viene visualizzata all’utente all’interno di Data Workbench. Il nome della dimensione non può includere un trattino (-). </td> 
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
   <td colname="col2"> Determina se la dimensione viene visualizzata nell’interfaccia di Data Workbench. Per impostazione predefinita, questo parametro è impostato su false. Se, ad esempio, la dimensione deve essere utilizzata solo come base di una metrica, puoi impostare questo parametro su true per nascondere la dimensione dalla visualizzazione di Data Workbench. </td> 
   <td colname="col3"> false </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresso </td> 
   <td colname="col2"> <p>Valore correlato alla dimensione padre (Parent). Se questo campo è un vettore di stringhe, ogni elemento del vettore ha una propria relazione con l’elemento padre. </p> <p> <p>Nota:  Se il valore di input per ogni voce di registro per un elemento della dimensione padre è vuoto, nessun elemento della dimensione molti-a-molti si relazionerà a tale elemento della dimensione padre. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elemento padre </td> 
   <td colname="col2"> Nome della dimensione padre. Qualsiasi dimensione conteggiata può essere una dimensione superiore. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Questo esempio illustra la definizione di una dimensione da molti a molti utilizzando i dati evento raccolti dal traffico del sito web. Questa dimensione da molti a molti, denominata &quot;Prodotto selezionato&quot;, fa riferimento alle sessioni relative ai prodotti acquistati dal visitatore durante tale sessione. Il campo x-products contiene un vettore di valori, ciascuno dei quali è associato a una visualizzazione di pagina, che a sua volta è associata a una sessione.

![](assets/cfg_Transformation_Dim_ManytoMany.png)

Creando tale trasformazione, puoi creare una visualizzazione all’interno di Data Workbench che rappresenta la relazione tra la dimensione di prodotto selezionata e il numero di sessioni che coinvolgono ciascuno dei prodotti.
