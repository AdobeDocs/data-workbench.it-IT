---
description: L'interfaccia Schema del set di dati visualizza le dimensioni estese (numerabili, semplici, molte a molte, numeriche, standard e temporali) definite in qualsiasi file di configurazione del set di dati di trasformazione e fornisce una visualizzazione delle relazioni tra tali dimensioni.
solution: Analytics
title: Interfaccia Schema del set di dati
topic: Data workbench
uuid: 3726e568-d3ea-47f8-8ac4-582c97fbbe0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Interfaccia Schema del set di dati{#dataset-schema-interface}

L&#39;interfaccia Schema del set di dati visualizza le dimensioni estese (numerabili, semplici, molte a molte, numeriche, standard e temporali) definite in qualsiasi file di configurazione del set di dati di trasformazione e fornisce una visualizzazione delle relazioni tra tali dimensioni.

Inoltre, l&#39; [!DNL Dataset Schema] interfaccia mostra tutte le dimensioni derivate definite dall&#39;utente, nonché tutte le dimensioni estese configurate per essere nascoste.

![](assets/vis_DatasetSchema_Example2.png)

>[!NOTE]
>
>È possibile cercare dimensioni all&#39;interno del diagramma schema. Il nome delle dimensioni rilevate dalla stringa di ricerca viene evidenziato e le righe della classe padre cambiano colore per tutti gli hit trovati nelle dimensioni secondarie subordinate. Le dimensioni Contabili restano visibili mentre scorrete per fornire una gerarchia e un contesto visualizzabili.

**Per interpretare un tipo di dimensione utilizzando l&#39;[!DNL Dataset Schema]interfaccia**

Nella tabella seguente sono elencati i tipi di dimensioni e i colori in cui i relativi nomi compaiono nell&#39; [!DNL Dataset Schema] interfaccia. Vengono inoltre indicati i genitori per le dimensioni del campione (dall’esempio precedente).

<table id="table_CF888522626E49A4A10D87085CAB5CC1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo dimensione </th> 
   <th colname="col2" class="entry"> Colore </th> 
   <th colname="col3" class="entry"> Dimensione di esempio e padre </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Contabile </td> 
   <td colname="col2"> Rosa </td> 
   <td colname="col3"> <p>Visitatore - In questo schema, Visitatore è una dimensione contabile principale. </p> <p>Sessione: padre è visitatore </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormale </td> 
   <td colname="col2"> Giallo </td> 
   <td colname="col3"> Pagina normale: principale è Visualizzazione pagina </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivato </td> 
   <td colname="col2"> Blu </td> 
   <td colname="col3"> Pagina successiva: principale è Visualizzazione pagina </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Molti-a-molti </td> 
   <td colname="col2"> Rosa e Verde (il gambo del padre è rosa, mentre il nome della dimensione è verde). </td> 
   <td colname="col3"> Termine di ricerca - padre è sessione </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numeriche </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Esatta durata pagina - principale è Visualizzazione pagina. In questo esempio, Exact Page Duration è una dimensione numerica nascosta. Vedi il tipo di dimensione Nascosto in questa tabella. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Semplice </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Pagina: principale è Visualizzazione pagina </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Ora: il padre è la sessione </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascosto </td> 
   <td colname="col2"> Le dimensioni nascoste sono una versione più scura del colore appropriato per il tipo di quota. Ad esempio, una dimensione numerica nascosta è un verde più scuro e meno chiaro. </td> 
   <td colname="col3"> Esatta durata della pagina - principale è Visualizzazione pagina </td> 
  </tr> 
 </tbody> 
</table>

Per ulteriori informazioni su questi tipi di dimensioni, vedere la Guida alla configurazione del *set di dati*.

**Visualizzazione predefinita di una dimensione**

* Nell&#39; [!DNL Dataset Schema] interfaccia, fare clic sulla dimensione desiderata. Viene visualizzata la visualizzazione predefinita. Ad esempio, se la visualizzazione predefinita è una tabella in cui sono visualizzate le sessioni e la dimensione selezionata e si fa clic sulla dimensione URI, Workbench dati visualizza una tabella con URI per sessioni.

   >[!NOTE]
   >
   >Se si desidera modificare la visualizzazione predefinita visualizzata, vedere [L&#39;interfaccia](../../../home/c-get-started/c-admin-intrf/c-dtst-sch-intrf.md#concept-e147b3a5b542453ca2b121e1c85bb175)Schema del set di dati.

**Visualizzazione di una visualizzazione specifica per una dimensione**

* Nell&#39; [!DNL Dataset Schema] interfaccia, fare clic con il pulsante destro del mouse sulla dimensione desiderata e scegliere **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.

