---
description: Tabella che mostra le convenzioni applicabili per la creazione di trasformazioni.
solution: Analytics
title: Convenzioni per la costruzione di trasformazioni
topic: Data workbench
uuid: 91dddca6-4c17-4107-b78b-0f8b8870ef8d
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Convenzioni per la costruzione di trasformazioni{#conventions-for-constructing-transformations}

Tabella che mostra le convenzioni applicabili per la creazione di trasformazioni.

<table id="table_BEB0F6C416D144B5A2DD3D1A21613B21"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Convention </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Esecuzione sequenziale </td> 
   <td colname="col2"> <p>Le trasformazioni all'interno di un file di configurazione del dataset vengono applicate alle voci del registro in sequenza (ovvero, nell'ordine in cui sono elencate nel file di configurazione). Pertanto, le trasformazioni devono essere elencate nell'ordine in cui le loro uscite sono utilizzate come input per altre trasformazioni. Più specificamente, se l'output di una trasformazione è utilizzato come input per un'altra trasformazione, è importante che tale trasformazione precedente sia elencata prima della seconda trasformazione nei file di configurazione del dataset. In caso contrario, il server workbench dati genera un errore. </p> <p> Le fasi di elaborazione forniscono un modo per ordinare le trasformazioni definite all'interno di più set di dati che includono file. Per tutti i set di dati sono inclusi i file associati a una particolare fase di elaborazione, le trasformazioni sono ordinate in base ai relativi input e output. Inoltre, se più set di dati includono file all’interno di un passaggio dati di output sullo stesso campo a seguito di una trasformazione, il server workbench dati genera un errore. </p> <p> Per ulteriori informazioni sulle fasi, vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md"> File</a>di configurazione dell'elaborazione del registro, File <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md"> di configurazione delle</a>trasformazioni e File <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> di inclusione dei</a>dataset. </p> <p>Una <span class="wintitle"> mappa</span> delle dipendenze di trasformazione può visualizzare il modo in cui un campo viene modificato da una serie di trasformazioni. Consulta Strumenti <a href="../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md"></a>di configurazione del set di dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nomi di output </td> 
   <td colname="col2"> La maggior parte delle trasformazioni specifica un campo di output. Se l'output è un campo esteso definito dall'utente, il nome del campo deve iniziare con "x-". I nomi dei campi di output non possono contenere spazi o caratteri speciali. I nomi dei campi estesi possono essere scritti con lettere maiuscole e minuscole, ad esempio "x-NewCampaignName" o "x-New-Campaign-Name" per garantire la leggibilità, ma il software li gestisce senza distinzione tra maiuscole e minuscole. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campi di input </td> 
   <td colname="col2"> <p>I campi di input fanno riferimento a uno dei campi della linea di base o a un campo creato dall’utente derivante dall’output di una trasformazione precedente. Se è necessaria una stringa costante, è possibile utilizzare una stringa tra virgolette al posto di una baseline o di un campo creato dall'utente. </p> <p> Per un elenco di alcuni dei campi di dati comunemente definiti che il server workbench dati può elaborare, vedere Campi <a href="../../../home/c-dataset-const-proc/c-ev-data-rec-fields.md"> record dati</a>evento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stringhe semplici e vettori di stringhe </td> 
   <td colname="col2"> Tutte le trasformazioni funzionano su stringhe e/o vettori di stringhe. Le stringhe semplici sono sequenze letterali di caratteri. I vettori di stringa contengono zero o più stringhe semplici in un ordine specifico. </td> 
  </tr> 
 </tbody> 
</table>

