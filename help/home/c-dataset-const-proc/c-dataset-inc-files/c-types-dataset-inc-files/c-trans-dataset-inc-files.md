---
description: Il file di inclusione del set di dati di trasformazione per un profilo ereditato contiene i parametri associati alla fase di trasformazione della costruzione del set di dati.
title: Transformation Dataset Include Files (File inclusi nel set di dati di trasformazione)
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
exl-id: 58793f82-162a-4d43-aea9-163716c82db6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 3%

---

# Transformation Dataset Include Files (File inclusi nel set di dati di trasformazione){#transformation-dataset-include-files}

Il file di inclusione del set di dati di trasformazione per un profilo ereditato contiene i parametri associati alla fase di trasformazione della costruzione del set di dati.

La prima riga del file definisce un tipo [!DNL TransformationInclude] che supporta i parametri Extended Dimension, Parameters, Reprocess, Stage e Transformations. Tutti gli altri parametri devono essere definiti nel file [!DNL Transformation.cfg] nella directory Dataset del profilo di set di dati.

L’inclusione di parametri diversi da Dimension estesi, parametri, rielaborazione, stage e trasformazioni in un file [!DNL Transformation Dataset Include] genera errori.

Puoi denominare un file [!DNL Transformation Dataset Include] come desiderato, ma l’estensione del file deve essere [!DNL .cfg]. Il file deve essere memorizzato all&#39;interno del *nome del profilo ereditato*\Dataset\Transformation directory. Poiché i file vengono caricati in modo ricorsivo durante la fase di trasformazione della costruzione del set di dati, puoi memorizzare i file [!DNL Transformation Dataset Include] a qualsiasi livello all’interno della directory (ad esempio, *nome profilo ereditato*\Dataset\Transformation\*nome cartella*\*include nome file*.cfg).

>[!NOTE]
>
>Molti parametri di configurazione specifici per il Web per Site sono definiti in file [!DNL Transformation Dataset Include]. Per informazioni su questi parametri, vedere [Impostazioni di configurazione per i dati Web](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

La tabella seguente descrive i parametri disponibili in un file [!DNL Transformation Dataset Include] :

<table id="table_7BD343888D9145BCBA889B531A4D18F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensioni estese </td> 
   <td colname="col2"> Facoltativo. Definisce le dimensioni estese. Vedere <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimension estesi</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parametri </td> 
   <td colname="col2"> Facoltativo. Variabile a cui è possibile fare riferimento in altri parametri di configurazione. Per ulteriori informazioni, consulta <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definizione dei parametri in Dataset Include Files</a> (Definizione dei parametri nel set di dati). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rielaborazione </td> 
   <td colname="col2"> <p>Facoltativo. È possibile inserire qui qualsiasi carattere o combinazione di caratteri. La modifica di questo parametro e il salvataggio del file avvia la riconversione dei dati. </p> <p> Per informazioni sulla rielaborazione dei dati, vedere <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e ritrasformazione</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>Facoltativo. Nome della fase di elaborazione che si applica a questo file <span class="wintitle"> Dataset di trasformazione Include</span>. Le fasi di elaborazione sono definite nel parametro Stages nel file <span class="filepath"> Transformation.cfg</span> . </p> <p> <p>Nota: Quando si specifica uno stage, il nome dello stage deve corrispondere esattamente al nome elencato nel parametro Stages nel file <span class="filepath"> Transformation.cfg</span> per il profilo del set di dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trasformazioni </td> 
   <td colname="col2"> Facoltativo. Definisce le trasformazioni di dati che devono essere applicate durante la trasformazione. Per informazioni sui tipi di trasformazione disponibili, consulta <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Trasformazioni dati</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Per una descrizione dei parametri nel file [!DNL Transformation.cfg], consulta [File di configurazione delle trasformazioni](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

Quando lavori con i file [!DNL Transformation Dataset Include] , tieni presente quanto segue:

* La modifica di uno qualsiasi dei parametri in questo file richiede la riconversione dei dati.
* [!DNL CrossRows],  [!DNL ODBCLookup],  [!DNL Sessionize] e  [!DNL AppendURI] le trasformazioni funzionano solo quando sono definite in un  [!DNL Transformation Dataset Configuration] file . Per informazioni su queste trasformazioni, consulta [Trasformazioni dati](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* È possibile aggiungere uno qualsiasi dei parametri descritti sopra al file [!DNL Transformation Dataset Include] aprendo e modificando il file in Blocco note. Le modifiche apportate e salvate vengono visualizzate quando riapri il file in Data Workbench. Quando si aggiunge un nuovo parametro, utilizzare il tasto Space (non il tasto Tab) per far rientrare due (2) spazi a destra del livello di intestazione precedente.

Se ti abboni al servizio dati [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] di Adobe, Adobe ti fornisce un profilo interno costituito da un set di trasformazioni di dati e dimensioni estese create specificamente per il servizio dati. Le trasformazioni e le dimensioni sono definite in file [!DNL Transformation Dataset Include] inclusi nella directory Dataset del profilo interno. Per istruzioni su come installare il profilo interno per il servizio dati [!DNL IP Geo-location] o [!DNL IP Geo-intelligence], consulta la *Guida utente Data Workbench*.
