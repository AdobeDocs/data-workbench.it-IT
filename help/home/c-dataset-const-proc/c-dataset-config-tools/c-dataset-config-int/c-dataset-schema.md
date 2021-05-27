---
description: L’interfaccia Schema del set di dati visualizza le dimensioni estese (dimensioni numerabili, semplici, da molti a molti, numeriche, standard e temporali) definite in qualsiasi file Configurazione set di dati di trasformazione e le relazioni tra tali dimensioni.
title: Dataset Schema (Schema del set di dati)
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
exl-id: b80e6e8e-9147-46ec-8602-2d7e5d33f077
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Dataset Schema (Schema del set di dati){#dataset-schema}

L’interfaccia Schema del set di dati visualizza le dimensioni estese (dimensioni numerabili, semplici, da molti a molti, numeriche, standard e temporali) definite in qualsiasi file Configurazione set di dati di trasformazione e le relazioni tra tali dimensioni.

Inoltre, l&#39;interfaccia [!DNL Dataset Schema] mostra tutte le dimensioni derivate definite dall&#39;utente, nonché tutte le dimensioni estese configurate per essere nascoste.

![](assets/vis_DatasetSchema_Example.png)

Questa sezione illustra i seguenti argomenti:

* [Per interpretare il tipo di dimensione utilizzando l’interfaccia Schema del set di dati](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [Visualizzazione predefinita di una dimensione](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [Visualizzazione di una visualizzazione specifica per una dimensione](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## Per interpretare il tipo di Dimension utilizzando l&#39;interfaccia Dataset Schema (Schema del set di dati) {#section-16a0a12b11334c07bec558c0b7d260b1}

Nella tabella seguente sono elencati i tipi di dimensioni e i colori in cui i relativi nomi vengono visualizzati nell&#39;interfaccia [!DNL Dataset Schema]. Vengono inoltre indicati i genitori per le dimensioni del campione (dall’esempio precedente).

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
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
   <td colname="col3"> <p>Visitatore: in questo schema, il visitatore è una dimensione contabile principale. </p> <p> Sessione: l’elemento padre è Visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormale </td> 
   <td colname="col2"> Giallo </td> 
   <td colname="col3"> DenormalPage - padre è Page View. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivato </td> 
   <td colname="col2"> Blu </td> 
   <td colname="col3"> Pagina successiva : la pagina padre è Vista pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Many-to-Many (Da molti-a-molti) </td> 
   <td colname="col2"> Rosa e verde (il gambo del genitore è rosa, mentre il nome della dimensione è verde). </td> 
   <td colname="col3"> Termine di ricerca - l'elemento padre è Sessione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numeriche </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Exact Page Duration - parent is Page View In questo esempio, Exact Page Duration è una dimensione numerica nascosta. Vedi il tipo di dimensione Nascosto in questa tabella. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Semplice </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Pagina : l’elemento principale è Visualizzazione pagina . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Ora: il padre è Sessione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascosto </td> 
   <td colname="col2"> Le dimensioni nascoste sono una versione più scura del colore appropriato per il tipo di dimensione. Ad esempio, una dimensione numerica nascosta è un verde più scuro e meno chiaro. </td> 
   <td colname="col3"> Durata esatta della pagina : l’elemento principale è Vista pagina. </td> 
  </tr> 
 </tbody> 
</table>

## Visualizzazione della visualizzazione predefinita per un Dimension {#section-1bbb73a5cbb34ffb844eb1932db85318}

* Nell’interfaccia [!DNL Dataset Schema] fai clic sulla dimensione desiderata. Viene visualizzata la visualizzazione predefinita. Ad esempio, se la visualizzazione predefinita è una tabella contenente sessioni e la dimensione selezionata e fai clic sulla dimensione URI, Data Workbench visualizza una tabella con URI per sessioni.

>[!NOTE]
>
>Per modificare la visualizzazione predefinita visualizzata, consulta il capitolo Configuring Interface and Analysis Features in *Data Workbench User Guide* (Configurazione delle funzioni di interfaccia e analisi).

## Visualizzazione di una visualizzazione specifica per un Dimension {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* Nell’interfaccia [!DNL Dataset Schema] fai clic con il pulsante destro del mouse sulla dimensione desiderata e fai clic su **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.
