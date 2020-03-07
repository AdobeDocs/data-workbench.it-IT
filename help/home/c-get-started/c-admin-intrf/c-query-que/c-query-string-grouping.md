---
description: Il raggruppamento delle stringhe di query consente di integrare un gran numero di campi.
title: Raggruppamento stringhe di query
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Raggruppamento stringhe di query{#query-string-grouping}

Il raggruppamento delle stringhe di query consente di integrare un gran numero di campi.

Il raggruppamento delle stringhe di query è specifico per ciascun profilo, ma funziona correttamente nelle trasformazioni come illustrato in questo esempio:

1. Create le coppie da includere nel bundle aggiungendo un file di configurazione personalizzato ( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg]), quindi aggiungendo il tipo di trasformazione *BuildNameValuePair* come parametro.

   ```
   2 = BuildNameValuePair:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to build)
             Name = string: Custom Events 
             Output = string: x-event-list       
   ```

1. Create un nuovo file per estrarre i dati condensati nei campi che desiderate utilizzare aggiungendo un file di configurazione personalizzato ( [!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg]), quindi aggiungete il tipo di trasformazione *ExtractNameValuePair* come parametro.

   ```
   2 = ExtractNameValuePairs:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Field = string: x-event-list 
         Name = string: Custom Events 
         Output Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to extract) 
             Name = string: Custom Events 
             Output = string: x-event-list   
   ```

## Altri usi {#section-cc5d2b0c9e194fc88a5a18a06ef22f5e}

Se si dispone di molti campi con variabili evar, prop e variabili personalizzate, durante l&#39;elaborazione del registro è possibile creare una coppia di valori di nome per combinare i campi in un rapporto. Ad esempio, è possibile creare coppie nome-valore in campi combinati per ridurre la dimensione del [!DNL tempDB] file.

![](assets/query_string_grouping.png)
