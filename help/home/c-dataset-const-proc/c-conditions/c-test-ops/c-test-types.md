---
description: La condizione Confronta e Intervallo richiedono di specificare il tipo di confronto da eseguire per la condizione.
title: Tipi di test per le operazioni di test
uuid: dc0433dd-a35e-472e-8975-f58347512c11
exl-id: 8abed46e-e76d-47c0-bbe9-cf98cf2d61e8
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 2%

---

# Tipi di test per le operazioni di test{#test-types-for-test-operations}

La condizione Confronta e Intervallo richiedono di specificare il tipo di confronto da eseguire per la condizione.

La tabella seguente descrive i tipi disponibili ( [!DNL LEXICAL], [!DNL NUMERIC] e [!DNL DATETIME]).

<table id="table_1B3AD8BDF0414D0AB8EE0E6D1B53E2CE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di test </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Note </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> INTERO</span> </p> </td> 
   <td colname="col2"> <p>In primo luogo, trasforma il campo di input in un numero intero. Se ciò non è possibile, viene utilizzato un valore pari a zero. Il test restituisce true solo se il valore intero risultante è maggiore o uguale al valore minimo specificato e minore o uguale al valore massimo specificato. </p> </td> 
   <td colname="col3"> <p>Se uno dei campi minimo o massimo è lasciato vuoto, il sistema utilizza il valore minimo o massimo appropriato disponibile per i numeri interi firmati a 64 bit. </p> <p> Se il valore minimo o massimo specificato nella condizione non viene analizzato correttamente in un valore intero, il sistema sostituisce zero e non interrompe l’elaborazione del set di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> DATETIME</span> </p> </td> 
   <td colname="col2"> <p>In primo luogo, trasforma il campo di input in una data. Se il campo di input non può essere trasformato in una data valida, il test della condizione restituisce false. Se il campo può essere trasformato in una data, il test restituisce true solo se la data di input cade alla data minima specificata o dopo quella specificata e in corrispondenza o prima della data massima specificata. </p> </td> 
   <td colname="col3"> <p>Se le date minima e massima non sono valide, il set di dati non è costruito. </p> <p> Se non vengono fornite le date minime o massime, il sistema sostituisce opportunamente la data minima (Jan 1, 1600) o la data massima (in qualche momento nel 24esimo secolo). </p> <p> L'Adobe consiglia di utilizzare uno dei seguenti formati per <span class="wintitle"> DATETIME</span>: </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> 1 gennaio 2013 HH:MM:SS EDT </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> 1 gennaio 2013 OH:MM:SS GMT </li> 
    </ul> <p> Se non specificato, il fuso orario viene impostato automaticamente su GMT. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LEXICO</span> </p> </td> 
   <td colname="col2"> <p>Restituisce true solo se il campo di input è lessicalmente maggiore o uguale alla stringa specificata come minimo e minore o uguale alla stringa specificata nel valore massimo. </p> </td> 
   <td colname="col3"> <p>Il confronto lessicale utilizza il valore ASCII dei caratteri nelle stringhe che si spostano da sinistra a destra confrontando i caratteri. Per il primo carattere che non corrisponde, quello con il valore ASCII più grande è considerato il maggiore tra i due. Nel caso in cui una stringa sia più breve dell'altra, ma fino a quel punto tutti i caratteri siano stati uguali, la stringa più lunga viene considerata la maggiore tra le due. Se le stringhe sono caratteri per caratteri equivalenti e hanno la stessa lunghezza, sono considerate lessicalmente equivalenti. </p> </td> 
  </tr> 
 </tbody> 
</table>
