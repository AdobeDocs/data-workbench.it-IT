---
description: L'interfaccia Schema del set di dati visualizza le dimensioni estese (numerabili, semplici, molte a molte, numeriche, denormali e temporali) definite in qualsiasi file di configurazione del set di dati di trasformazione e le relazioni tra tali dimensioni.
solution: Analytics
title: Schema set di dati
topic: Data workbench
uuid: 4ef5f14b-dc19-4118-a2f2-d680ded8092c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Schema set di dati{#dataset-schema}

L&#39;interfaccia Schema del set di dati visualizza le dimensioni estese (numerabili, semplici, molte a molte, numeriche, denormali e temporali) definite in qualsiasi file di configurazione del set di dati di trasformazione e le relazioni tra tali dimensioni.

Inoltre, l&#39; [!DNL Dataset Schema] interfaccia mostra tutte le dimensioni derivate definite dall&#39;utente, nonché tutte le dimensioni estese configurate per essere nascoste.

![](assets/vis_DatasetSchema_Example.png)

In questa sezione vengono trattati i seguenti argomenti:

* [Per interpretare il tipo di dimensione utilizzando l&#39;interfaccia Schema dati](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-16a0a12b11334c07bec558c0b7d260b1)
* [Visualizzazione predefinita di una dimensione](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-1bbb73a5cbb34ffb844eb1932db85318)
* [Visualizzazione di una visualizzazione specifica per una dimensione](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-schema.md#section-d46626df90bc4c44ae60c4b71eaeac7f)

## Per interpretare il tipo di dimensione utilizzando l&#39;interfaccia schema del set di dati {#section-16a0a12b11334c07bec558c0b7d260b1}

Nella tabella seguente sono elencati i tipi di dimensioni e i colori in cui i relativi nomi compaiono nell&#39; [!DNL Dataset Schema] interfaccia. Vengono inoltre indicati i genitori per le dimensioni del campione (dall’esempio precedente).

<table id="table_20D1A9EAAED247338476C475C63255F5"> 
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
   <td colname="col3"> <p>Visitatore - In questo schema, Visitatore è una dimensione contabile principale. </p> <p> Sessione - padre è Visitatore. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Denormale </td> 
   <td colname="col2"> Giallo </td> 
   <td colname="col3"> DenormalPage - parent è Page View (Visualizzazione pagina). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Derivato </td> 
   <td colname="col2"> Blu </td> 
   <td colname="col3"> Pagina successiva - principale è Visualizzazione pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Molti-a-molti </td> 
   <td colname="col2"> Rosa e Verde (il gambo del padre è rosa, mentre il nome della dimensione è verde). </td> 
   <td colname="col3"> Termine di ricerca - padre è Sessione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numeriche </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Exact Page Duration - parent is Page View In questo esempio, Exact Page Duration è una dimensione numerica nascosta. Vedi il tipo di dimensione Nascosto in questa tabella. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Semplice </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Pagina - padre è Visualizzazione pagina. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo </td> 
   <td colname="col2"> Verde </td> 
   <td colname="col3"> Ora - padre è Sessione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascosto </td> 
   <td colname="col2"> Le dimensioni nascoste sono una versione più scura del colore appropriato per il tipo di quota. Ad esempio, una dimensione numerica nascosta è un verde più scuro e meno chiaro. </td> 
   <td colname="col3"> Esatta durata pagina - principale è Visualizzazione pagina. </td> 
  </tr> 
 </tbody> 
</table>

## Visualizzazione predefinita di una dimensione {#section-1bbb73a5cbb34ffb844eb1932db85318}

* Nell&#39; [!DNL Dataset Schema] interfaccia, fare clic sulla dimensione desiderata. Viene visualizzata la visualizzazione predefinita. Ad esempio, se la visualizzazione predefinita è una tabella in cui sono visualizzate le sessioni e la dimensione selezionata e si fa clic sulla dimensione URI, il workbench dati visualizza una tabella con URI per sessioni.

>[!NOTE]
>
>Per modificare la visualizzazione predefinita visualizzata, consultare il capitolo Configurazione delle funzioni di interfaccia e analisi nella Guida *utente di Workbench* dati.

## Visualizzazione di una visualizzazione specifica per una dimensione {#section-d46626df90bc4c44ae60c4b71eaeac7f}

* Nell&#39; [!DNL Dataset Schema] interfaccia, fare clic con il pulsante destro del mouse sulla dimensione desiderata e scegliere **[!UICONTROL Add Visualization]** > *&lt;**[!UICONTROL visualization type]**>*.

