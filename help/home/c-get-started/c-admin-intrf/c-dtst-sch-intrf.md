---
description: L’interfaccia Schema del set di dati visualizza le dimensioni estese (dimensioni numerabili, semplici, da molti a molti, numeriche, standard e temporali) definite in qualsiasi file di configurazione del set di dati di trasformazione e fornisce una visualizzazione delle relazioni tra tali dimensioni.
title: Interfaccia Dataset Schema (Schema del set di dati)
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
exl-id: a8d4cf02-4ff7-4fcc-9062-425c1fe1fb28
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 3%

---

# Interfaccia Dataset Schema (Schema del set di dati){#dataset-schema-interface}

{{eol}}

L’interfaccia Schema del set di dati visualizza le dimensioni estese (dimensioni numerabili, semplici, da molti a molti, numeriche, standard e temporali) definite in qualsiasi file di configurazione del set di dati di trasformazione e fornisce una visualizzazione delle relazioni tra tali dimensioni.

Inoltre, il [!DNL Dataset Schema] l’interfaccia mostra tutte le dimensioni derivate definite dall’utente, nonché tutte le dimensioni estese configurate per essere nascoste.

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>Puoi cercare le dimensioni all’interno del diagramma di schema. Il nome delle dimensioni trovate dalla stringa di ricerca viene evidenziato e le linee della classe padre cambiano colore per gli hit trovati nelle dimensioni secondarie subordinate. Le dimensioni conteggiate rimangono visibili mentre scorri per fornire una gerarchia e un contesto visualizzabili.

**Per interpretare un tipo di dimensione utilizzando [!DNL Dataset Schema] interfaccia**

Nella tabella seguente sono elencati i tipi di dimensioni e i colori in cui i relativi nomi vengono visualizzati nella tabella [!DNL Dataset Schema] interfaccia. Vengono inoltre indicati i genitori per le dimensioni del campione (dall’esempio precedente).

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo di Dimension </th> 
   <th colname="col2" class="entry"> Colore </th> 
   <th colname="col3" class="entry"> Dimension di esempio e padre </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Contabile </td> 
   <td colname="col2"> Rosa </td> 
   <td colname="col3"> <p>Visitatore: in questo schema, il visitatore è una dimensione contabile principale. </p> <p>Sessione: l’elemento principale è Visitatore </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormale </td> 
   <td colname="col2"> Giallo </td> 
   <td colname="col3"> Pagina standard: principale è Visualizzazione pagina </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivato </td> 
   <td colname="col2"> Blu </td> 
   <td colname="col3"> Pagina successiva - Pagina padre: visualizzazione pagina </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Many-to-Many (Da molti-a-molti) </td> 
   <td colname="col2"> Rosa e verde (il gambo del genitore è rosa, mentre il nome della dimensione è verde). </td> 
   <td colname="col3"> Termine di ricerca - l'elemento padre è Session </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numeriche </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Durata esatta della pagina : l’elemento principale è Vista pagina. In questo esempio, Exact Page Duration è una dimensione numerica nascosta. Vedi il tipo di dimensione Nascosto in questa tabella. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Semplice </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Pagina : l’elemento padre è Vista pagina </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Ora - il genitore è la sessione </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascosto </td> 
   <td colname="col2"> Le dimensioni nascoste sono una versione più scura del colore appropriato per il tipo di dimensione. Ad esempio, una dimensione numerica nascosta è un verde più scuro e meno chiaro. </td> 
   <td colname="col3"> Durata esatta della pagina - l’elemento principale è Vista pagina </td> 
  </tr> 
 </tbody> 
</table>

Per ulteriori informazioni su questi tipi di dimensioni, consulta la sezione *Guida alla configurazione del set di dati*.

**Visualizzazione predefinita di una dimensione**

* In [!DNL Dataset Schema] fai clic sulla dimensione desiderata. Viene visualizzata la visualizzazione predefinita. Ad esempio, se la visualizzazione predefinita è una tabella contenente sessioni e la dimensione selezionata e fai clic sulla dimensione URI, in Data Workbench viene visualizzata una tabella con URI per sessioni.

   >[!NOTE]
   >
   >Per modificare la visualizzazione predefinita visualizzata, consulta [Interfaccia dello schema del set di dati](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175).

**Visualizzazione di una visualizzazione specifica per una dimensione**

* In [!DNL Dataset Schema] , fai clic con il pulsante destro del mouse sulla dimensione desiderata e fai clic su **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.
