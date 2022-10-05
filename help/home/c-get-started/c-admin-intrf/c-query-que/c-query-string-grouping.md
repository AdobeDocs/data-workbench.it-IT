---
description: Raggruppamento stringhe di query consente di integrare un gran numero di campi.
title: Raggruppamento stringhe di query
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
exl-id: 4052cf7e-abdf-4e16-9f42-521c4e719786
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# Raggruppamento stringhe di query{#query-string-grouping}

{{eol}}

Raggruppamento stringhe di query consente di integrare un gran numero di campi.

Il raggruppamento di stringhe query è specifico per ciascun profilo, ma funziona bene nelle trasformazioni come mostrato in questo esempio:

1. Crea le coppie da abbinare aggiungendo un file di configurazione personalizzato ( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg]) e quindi aggiungere il tipo di trasformazione *BuildNameValuePair* come parametro.

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

1. Crea un nuovo file per estrarre i dati condensati nei campi che desideri utilizzare aggiungendo un file di configurazione personalizzato ( [!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg]) e quindi aggiungere il tipo di trasformazione *ExtractNameValuePair* come parametro.

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

Se hai molti campi con evar, prop e variabili personalizzate, durante l’elaborazione del registro puoi creare una coppia di valori di nome per combinare i campi in un rapporto. Ad esempio, puoi creare coppie nome-valore in campi combinati per ridurre il [!DNL tempDB] dimensioni del file.

![](assets/query_string_grouping.png)
