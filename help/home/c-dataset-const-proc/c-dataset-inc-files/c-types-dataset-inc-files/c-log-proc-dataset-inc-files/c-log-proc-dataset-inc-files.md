---
description: Il file Log Processing Dataset Include per un profilo ereditato contiene i parametri associati alla fase di elaborazione del log della costruzione del dataset.
solution: Analytics
title: I Dati Di Elaborazione Del Registro Includono I File
topic: Data workbench
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# I Dati Di Elaborazione Del Registro Includono I File{#log-processing-dataset-include-files}

Il file Log Processing Dataset Include per un profilo ereditato contiene i parametri associati alla fase di elaborazione del log della costruzione del dataset.

La prima riga di un [!DNL Log Processing Dataset Include] file definisce un tipo [!DNL LogProcessingInclude] che supporta i parametri Decoder Groups, Fields, Log Entry Condition, Parameters, Reprocess, Stage e Transformations. Tutti gli altri parametri per l&#39;elaborazione del registro devono essere definiti nel [!DNL Log Processing.cfg] file nella directory Dataset del profilo dataset. È possibile assegnare un nome a un [!DNL Log Processing Dataset Include] file come desiderato, ma la sua estensione deve essere [!DNL .cfg]. Il file deve essere memorizzato nel nome del profilo *ereditato*\Dataset\Log Processing directory. Poiché i file vengono caricati in modo ricorsivo durante la fase di elaborazione del registro della creazione del set di dati, è possibile archiviare i [!DNL Log Processing Dataset Include] file a qualsiasi livello all&#39;interno della directory (ad esempio, nome *del profilo* ereditato\Dataset\Log Processing\*nome cartella*\*include nome file*.cfg).

>[!NOTE]
>
>Molti parametri di configurazione specifici per il Web per Site sono definiti nei [!DNL Log Processing Dataset Include] file. Per informazioni su questi parametri, vedere Impostazioni [di configurazione per i dati](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)Web.

<table id="table_E2112652CCD443E889A529EEDC4ADF1C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Gruppi decodificatori </td> 
   <td colname="col2"> <p>Obbligatorio se nel file <span class="filepath"> Log Processing.cfg</span> sono state definite origini di registro o file XML. Il file di testo o i decodificatori XML definiti per estrarre i campi di dati dai file di registro e dalle origini di registro XML. </p> <p> <b>Per aggiungere un nuovo gruppo di decodificatori</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Fare clic con il pulsante destro del mouse su <span class="uicontrol"> Decoder Group</span> e scegliere <span class="uicontrol"> Add new</span> &gt; <span class="uicontrol"> TextFileDecoderGroup</span> o <span class="uicontrol"> XMLDecoderGroup</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> Nel parametro Name del nuovo gruppo, immettete il nome desiderato per il gruppo decoder. </li> 
     </ul> </p> <p> <p>Nota:  Quando si specifica un gruppo decodificatore nel file <span class="filepath"> Log Processing.cfg</span> per il profilo del set di dati, il nome deve corrispondere esattamente al nome immesso qui. Per ulteriori informazioni, vedere <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> File</a>di registro. </p> </p> <p> Per informazioni sui decodificatori che è possibile definire per ciascun gruppo, vedere <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Gruppi</a> decodificatori di file di testo o Gruppi <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> decodificatori</a>XML. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campi </td> 
   <td colname="col2"> <p>Elenca i campi definiti in <span class="wintitle"> Log Sources</span> o <span class="wintitle"> Transformations</span> in un file <span class="wintitle"> Log Processing Dataset Configuration</span> , ma utilizzati in trasformazioni, condizioni o dimensioni estese in un file <span class="wintitle"> Transformation Dataset Configuration</span> devono essere elencati qui. </p> <p> Ogni campo riportato di seguito deve essere elencato in alcuni <span class="wintitle"> file DataSet di elaborazione log che includono</span> : 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione voce di registro </td> 
   <td colname="col2"> <p>Facoltativo. Definisce le regole in base alle quali le voci di registro vengono considerate per l'inclusione nel set di dati. Vedere <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condizione</a>di registrazione. </p> <p> <p>Nota:  Per essere inclusa nel dataset, una voce di registro deve soddisfare la condizione <span class="wintitle"> di</span> voce di registro nel file <span class="filepath"> Log Processing.cfg</span> e in ogni file <span class="wintitle"> Log Processing Dataset Include</span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parametri </td> 
   <td colname="col2"> Facoltativo. Variabile a cui potete fare riferimento in altri parametri di configurazione. Per ulteriori informazioni, vedere <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definizione dei parametri in Dataset Includi file</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rielabora </td> 
   <td colname="col2"> <p>Facoltativo. È possibile inserire qui qualsiasi carattere o combinazione di caratteri. La modifica di questo parametro e il salvataggio del file nel server workbench dati avvia la rielaborazione dei dati. </p> <p> Per informazioni sulla rielaborazione dei dati, vedere <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e trasformazione</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>Facoltativo. Il nome del passaggio di elaborazione che si applica a questo file <span class="wintitle"> Log Processing Dataset Include</span> . Le fasi di elaborazione sono definite nel parametro Stages nel file <span class="filepath"> Log Processing.cfg</span> . </p> <p> <p>Nota:  Quando si specifica uno stage, il nome dello stage deve corrispondere esattamente al nome elencato nel parametro Stages nel file <span class="filepath"> Log Processing.cfg</span> per il profilo del dataset. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trasformazioni </td> 
   <td colname="col2"> Facoltativo. Definisce le trasformazioni di dati che devono essere applicate durante l'elaborazione del registro. Per informazioni sui tipi di trasformazione disponibili, vedere <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Trasformazioni</a>dati. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Per una descrizione dei parametri nel [!DNL Log Processing.cfg] file, vedere File [di configurazione](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)Elaborazione log.

Quando lavorate con [!DNL Log Processing Dataset Include] i file, tenete a mente quanto segue:

* La modifica di uno qualsiasi dei parametri in questo file richiede la rielaborazione di tutti i dati.
* Potete aggiungere al [!DNL Log Processing Dataset Include] file uno qualsiasi dei parametri precedentemente descritti aprendo e modificando il file in Blocco note. Eventuali modifiche apportate e salvate vengono visualizzate quando si riapre il file nel workbench dati. Quando si aggiunge un nuovo parametro, utilizzate il tasto Space (non il tasto Tab) per applicare un rientro di due (2) spazi a destra del livello di intestazione precedente.

