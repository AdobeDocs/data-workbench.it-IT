---
description: Una dimensione standard ha una relazione uno-a-uno con la dimensione conteggiata superiore.
title: Dimensioni anomale
uuid: f172fbce-e967-41ce-9958-9062561ecbcc
exl-id: 0c4fad38-bc7c-4b63-98ec-c9121e576a36
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 2%

---

# Dimensioni anomale{#denormal-dimensions}

{{eol}}

Una dimensione standard ha una relazione uno-a-uno con la dimensione conteggiata superiore.

Puoi definire una dimensione normale ogni volta che la dimensione desiderata contiene un elemento univoco per ogni elemento del relativo elemento padre. Ad esempio: [!DNL EMail Address] è una dimensione standard con un elemento padre di Visitatore. Ogni visitatore ha un indirizzo e-mail e ogni elemento nella dimensione Indirizzo e-mail è l’indirizzo e-mail di un singolo visitatore. Anche se due visitatori hanno lo stesso indirizzo e-mail, gli indirizzi sono elementi distinti della dimensione Indirizzo e-mail.

Puoi utilizzare dimensioni comuni in qualsiasi visualizzazione di tabella, tabella di dettaglio o per creare filtri. Inoltre, puoi utilizzare dimensioni comuni con la funzionalità di esportazione del segmento del server di Data Workbench per esportare i valori dei campi (ad esempio [!DNL Tracking ID] o [!DNL EMail Address]) con molti valori. Poiché qualsiasi dato di segmento da esportare deve essere definito come una dimensione all’interno del profilo, devi creare una dimensione standard che memorizzi le stringhe non elaborate dei dati del campo.

>[!NOTE]
>
>Quando si utilizza una dimensione standard in una tabella o in un’altra visualizzazione che richiede una dimensione normale, viene creata automaticamente una dimensione standard derivata. La dimensione standard derivata ha una relazione uno-a-molti con la dimensione padre.

Per informazioni sulla visualizzazione della tabella di dettaglio e sui filtri, consulta il capitolo Visualizzazioni di analisi in *Guida utente di Data Workbench*. Per informazioni sull’esportazione dei segmenti, consulta il capitolo Configuring Interface and Analysis Features (Configurazione dell’interfaccia e delle funzioni di analisi) *Guida utente di Data Workbench*.

>[!NOTE]
>
>Le dimensioni standard possono essere molto costose in termini di tempo di query e spazio su disco. Una dimensione standard con padre [!DNL Page View]e una stringa di input media a 50 byte potrebbe aggiungere 25 GB di dati ai buffer in un set di dati tipico e di grandi dimensioni, equivalente a circa 13 dimensioni di visualizzazione di pagina semplice o numerica, o circa 125 dimensioni a livello di sessione. Non aggiungere mai una dimensione standard a un set di dati senza un’attenta valutazione dell’impatto sulle prestazioni.

Le dimensioni standard sono definite dai seguenti parametri:

<table id="table_532AD791E39B4CF296FFA1C33FB8302E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Impostazione predefinita </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descrittivo della dimensione così come viene visualizzata all’interno di Data Workbench. Il nome della dimensione non può includere un trattino (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla dimensione estesa. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione </td> 
   <td colname="col2"> Condizioni in cui creare la relazione tra l’elemento padre e il valore del campo di input. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascosto </td> 
   <td colname="col2"> Determina se la dimensione viene visualizzata nell’interfaccia di Data Workbench. Per impostazione predefinita, questo parametro è impostato su false. Se, ad esempio, la dimensione deve essere utilizzata solo come base di una metrica, puoi impostare questo parametro su true per nascondere la dimensione dalla visualizzazione di Data Workbench. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ingresso </td> 
   <td colname="col2"> Valore correlato alla dimensione padre (Parent). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elementi normalizzati </td> 
   <td colname="col2"> Parametro di ottimizzazione delle prestazioni che specifica il numero di elementi dimensionali i cui nomi devono essere memorizzati nella memoria del sistema. Se si imposta questo parametro su un valore più alto, una dimensione standard utilizza più RAM, ma si traduce in query più veloci. Il valore predefinito è 16383. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Funzionamento </td> 
   <td colname="col2"> <p>Le operazioni disponibili sono le seguenti: </p> <p> 
     <ul id="ul_CCDC45838A3941BD949B6D21EA0492B3"> 
      <li id="li_F33898192A82437692B5C15684EFCF64"> PRIMO NONBLANK: Viene utilizzato il primo valore di input non vuoto, indipendentemente dal fatto che provenga dalla prima voce di registro. Se <span class="wintitle"> Ingresso</span> è un campo vettoriale, viene utilizzata la prima riga nel vettore per la voce di registro pertinente. </li> 
      <li id="li_4ADD0A368BB74B64AD29126C8E7B333F"> PRIMA RIGA: Viene utilizzato il valore della prima voce di registro relativa all’elemento dimensione padre, anche se l’input è vuoto. Se <span class="wintitle"> Ingresso</span> è un campo vettoriale, viene utilizzata la prima riga nel vettore per la voce di registro pertinente. Se questo valore è vuoto o non è un numero, o se la voce di registro pertinente non soddisfa la condizione della dimensione, non viene utilizzato alcun valore. </li> 
      <li id="li_C93CA22ADA634F21A6488BB3BEE7CB23"> ULTIMO NONBLANK: Viene utilizzato l’ultimo valore di input non vuoto, indipendentemente dal fatto che provenga dall’ultima voce di registro. Se <span class="wintitle"> Ingresso</span> è un campo vettoriale, viene utilizzata la prima riga nel vettore per la voce di registro pertinente. </li> 
      <li id="li_2FFE585521B14FE5ABBF66AAC47F22C4"> ULTIMA RIGA: Viene utilizzato il valore per l’ultima voce di registro relativa all’elemento dimensione padre, anche se l’input è vuoto. Se <span class="wintitle"> Ingresso</span> è un campo vettoriale, viene utilizzata la prima riga nel vettore per la voce di registro pertinente. Se questo valore è vuoto o non è un numero, o se la voce di registro pertinente non soddisfa la condizione della dimensione, non viene utilizzato alcun valore. </li> 
     </ul> </p> <p> <p>Nota: Se Operation non produce alcun valore, viene utilizzato un valore vuoto (""). </p> </p> <p> È necessario specificare un’operazione per garantire che la dimensione sia definita come previsto. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elemento padre </td> 
   <td colname="col2"> Nome della dimensione padre. Qualsiasi dimensione conteggiata può essere una dimensione superiore. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

La dimensione standard mostrata in questo esempio prende tutti i dati del campo x-trackingid come input e li include in una dimensione denominata ID visitatore. Per un segmento di visitatori che hai creato, puoi esportare i dati nella dimensione ID visitatore (così come in qualsiasi altra dimensione definita).

![](assets/cfg_Transformation_Dim_Denormal.png)
