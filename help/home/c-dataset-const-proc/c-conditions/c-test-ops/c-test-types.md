---
description: Le condizioni Confronta e Intervallo richiedono che sia specificato il tipo di confronto da eseguire per la condizione.
solution: Analytics
title: Tipi di test per le operazioni di test
topic: Data workbench
uuid: dc0433dd-a35e-472e-8975-f58347512c11
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tipi di test per le operazioni di test{#test-types-for-test-operations}

Le condizioni Confronta e Intervallo richiedono che sia specificato il tipo di confronto da eseguire per la condizione.

Nella tabella seguente sono descritti i tipi disponibili ( [!DNL LEXICAL], [!DNL NUMERIC]e [!DNL DATETIME]).

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
   <td colname="col1"> <p><span class="wintitle"> INTEGER</span> </p> </td> 
   <td colname="col2"> <p>In primo luogo, trasforma il campo di input in un numero intero. Se questo non è possibile, viene utilizzato un valore pari a zero. Il test restituisce true solo se il valore intero immesso risultante è maggiore o uguale al valore minimo specificato e minore o uguale al valore massimo specificato. </p> </td> 
   <td colname="col3"> <p>Se uno dei campi min o max è lasciato vuoto, il sistema utilizza il valore minimo o massimo appropriato disponibile per i numeri interi con segno a 64 bit. </p> <p> Se il valore minimo o massimo specificato nella condizione non viene analizzato correttamente in un valore intero, il sistema sostituisce zero e non interrompe l'elaborazione del dataset. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> DATETIME</span> </p> </td> 
   <td colname="col2"> <p>In primo luogo, trasforma il campo di immissione in una data. Se il campo di input non può essere trasformato in una data valida, il test di condizione restituisce false. Se il campo può essere trasformato in una data, il test restituisce true solo se la data di input rientra nella data minima specificata o dopo quella specificata e in quella indicata o prima della data massima specificata. </p> </td> 
   <td colname="col3"> <p>Se le date min e max non sono valide, il set di dati non è costruito. </p> <p> Se le date min o max non sono specificate, il sistema sostituisce correttamente la data min (1 gen 1, 1600) o la data max (qualche volta nel 24esimo secolo). </p> <p> Adobe consiglia di utilizzare uno dei seguenti formati per <span class="wintitle"> DATETIME</span>: </p> 
    <ul id="ul_44F469CC5D974382AF70D7B1975CF077"> 
     <li id="li_DB5FD4AFD6B34436ACD7C13282F64956"> 1 gennaio 2013 HH:MM:SS EDT </li> 
     <li id="li_307580C3F97D495BB16F1212DB38CE37"> 1 gen 2013 HH:MM:SS GMT </li> 
    </ul> <p> Se non viene specificato, per impostazione predefinita il fuso orario è GMT. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LEXICO</span> </p> </td> 
   <td colname="col2"> <p>Restituisce true solo se il campo di input è lessicamente maggiore o uguale alla stringa specificata come minimo e minore o uguale alla stringa specificata nel valore massimo. </p> </td> 
   <td colname="col3"> <p>Il confronto lessicale utilizza il valore ASCII dei caratteri nelle stringhe che si spostano da sinistra a destra confrontando i caratteri. Per il primo carattere che non corrisponde, quello con il valore ASCII più grande è considerato il maggiore dei due. Se una stringa è più corta dell'altra, ma fino a quel momento tutti i caratteri sono stati identici, la stringa più lunga viene considerata la maggiore tra le due. Se le stringhe sono caratteri per l'equivalente di caratteri e la stessa lunghezza, vengono considerate lessicalmente equivalenti. </p> </td> 
  </tr> 
 </tbody> 
</table>

