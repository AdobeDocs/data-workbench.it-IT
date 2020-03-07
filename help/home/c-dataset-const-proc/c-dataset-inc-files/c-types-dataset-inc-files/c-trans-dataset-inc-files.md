---
description: Il file Transformation Dataset Include per un profilo ereditato contiene i parametri associati alla fase di trasformazione della costruzione del set di dati.
solution: Analytics
title: I set di dati delle trasformazioni includono i file
topic: Data workbench
uuid: 46756f68-843c-4b0d-a79e-f107ef85db6c
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# I set di dati delle trasformazioni includono i file{#transformation-dataset-include-files}

Il file Transformation Dataset Include per un profilo ereditato contiene i parametri associati alla fase di trasformazione della costruzione del set di dati.

La prima riga del file definisce un tipo [!DNL TransformationInclude] che supporta i parametri Dimensioni estese, Parametri, Rielabora, Stage e Trasformazioni. Tutti gli altri parametri devono essere definiti nel [!DNL Transformation.cfg] file nella directory Dataset del profilo dataset.

L&#39;inclusione di parametri diversi da Dimensioni estese, Parametri, Rielabora, Stage e Trasformazioni in un [!DNL Transformation Dataset Include] file genera errori.

È possibile assegnare un nome a un [!DNL Transformation Dataset Include] file come desiderato, ma la sua estensione deve essere [!DNL .cfg]. Il file deve essere memorizzato nel nome del profilo *ereditato*\Dataset\Transformation directory. Poiché i file vengono caricati in modo ricorsivo durante la fase di trasformazione della creazione del set di dati, è possibile archiviare i [!DNL Transformation Dataset Include] file a qualsiasi livello all&#39;interno della directory (ad esempio, nome **\Dataset\Transformation\*nome cartella*\*include nome file*.cfg).

>[!NOTE]
>
>Molti parametri di configurazione specifici per il Web per Site sono definiti nei [!DNL Transformation Dataset Include] file. Per informazioni su questi parametri, vedere Impostazioni [di configurazione per i dati](../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)Web.

Nella tabella seguente sono descritti i parametri disponibili in un [!DNL Transformation Dataset Include] file:

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
   <td colname="col2"> Facoltativo. Definisce le dimensioni estese. Consultate <a href="../../../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimensioni</a>estese. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parametri </td> 
   <td colname="col2"> Facoltativo. Variabile a cui potete fare riferimento in altri parametri di configurazione. Per ulteriori informazioni, vedere <a href="../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definizione dei parametri in Dataset Includi file</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rielabora </td> 
   <td colname="col2"> <p>Facoltativo. È possibile inserire qui qualsiasi carattere o combinazione di caratteri. La modifica di questo parametro e il salvataggio del file avvia la riconversione dei dati. </p> <p> Per informazioni sulla rielaborazione dei dati, vedere <a href="../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e trasformazione</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>Facoltativo. Il nome del passaggio di elaborazione che si applica a questo file <span class="wintitle"> Transformation Dataset Include</span> . Le fasi di elaborazione sono definite nel parametro Stages nel file <span class="filepath"> Transformation.cfg</span> . </p> <p> <p>Nota: Quando si specifica uno stage, il nome dello stage deve corrispondere esattamente al nome elencato nel parametro Stages nel file <span class="filepath"> Transformation.cfg</span> per il profilo del dataset. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trasformazioni </td> 
   <td colname="col2"> Facoltativo. Definisce le trasformazioni di dati che devono essere applicate durante la trasformazione. Per informazioni sui tipi di trasformazione disponibili, vedere <a href="../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Trasformazioni</a>dati. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Per una descrizione dei parametri nel [!DNL Transformation.cfg] file, vedere File [di configurazione delle](../../../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)trasformazioni.

Quando lavorate con [!DNL Transformation Dataset Include] i file, tenete a mente quanto segue:

* La modifica di uno qualsiasi dei parametri in questo file richiede la riconversione dei dati.
* [!DNL CrossRows], [!DNL ODBCLookup][!DNL Sessionize]e [!DNL AppendURI] le trasformazioni funzionano solo se definite in un [!DNL Transformation Dataset Configuration] file. Per informazioni su queste trasformazioni, consultate Trasformazioni [dati](../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md).

* Potete aggiungere al [!DNL Transformation Dataset Include] file uno qualsiasi dei parametri precedentemente descritti aprendo e modificando il file in Blocco note. Eventuali modifiche apportate e salvate vengono visualizzate quando si riapre il file nel workbench dati. Quando si aggiunge un nuovo parametro, utilizzate il tasto Space (non il tasto Tab) per applicare un rientro di due (2) spazi a destra del livello di intestazione precedente.

Se ti iscrivi al servizio [!DNL IP Geo-location] [!DNL IP Geo-intelligence] dati o di Adobe, Adobe ti fornisce un profilo interno composto da una serie di trasformazioni di dati e dimensioni estese create appositamente per il servizio dati. Le trasformazioni e le dimensioni sono definite in [!DNL Transformation Dataset Include] file inclusi nella directory Dataset del profilo interno. Per istruzioni sull&#39;installazione del profilo interno per il servizio [!DNL IP Geo-location] o [!DNL IP Geo-intelligence] dati, vedere la Guida *utente di Workbench* dati.
