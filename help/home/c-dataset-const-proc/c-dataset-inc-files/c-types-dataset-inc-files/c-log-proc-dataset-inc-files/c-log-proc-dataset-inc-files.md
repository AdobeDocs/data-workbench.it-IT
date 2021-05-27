---
description: Il file di inclusione del set di dati di elaborazione del registro per un profilo ereditato contiene i parametri associati alla fase di elaborazione del registro della costruzione del set di dati.
title: Elaborazione del registro di Dataset Include Files (File inclusi nel set di dati)
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
exl-id: 06d8046d-6bac-4ccd-bcef-06f7c9ec7619
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 3%

---

# Elaborazione del registro di Dataset Include Files (File inclusi nel set di dati){#log-processing-dataset-include-files}

Il file di inclusione del set di dati di elaborazione del registro per un profilo ereditato contiene i parametri associati alla fase di elaborazione del registro della costruzione del set di dati.

La prima riga di un file [!DNL Log Processing Dataset Include] definisce un tipo [!DNL LogProcessingInclude] che supporta i parametri Decoder Groups, Fields, Log Entry Condition, Parameters, Reprocess, Stage e Transformations. Tutti gli altri parametri per l’elaborazione del registro devono essere definiti nel file [!DNL Log Processing.cfg] nella directory Dataset del profilo di set di dati. Puoi denominare un file [!DNL Log Processing Dataset Include] come desiderato, ma l’estensione del file deve essere [!DNL .cfg]. Il file deve essere memorizzato all&#39;interno del *nome del profilo ereditato*\Dataset\Log Processing directory. Poiché i file vengono caricati in modo ricorsivo durante la fase di elaborazione del registro della costruzione del set di dati, è possibile memorizzare i file [!DNL Log Processing Dataset Include] a qualsiasi livello all’interno della directory (ad esempio, *nome profilo ereditato*\Dataset\Log Processing\*nome cartella*\*include nome file*.cfg).

>[!NOTE]
>
>Molti parametri di configurazione specifici per il Web per Site sono definiti in file [!DNL Log Processing Dataset Include]. Per informazioni su questi parametri, vedere [Impostazioni di configurazione per i dati Web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

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
   <td colname="col2"> <p>Obbligatorio se sono state definite origini di file di registro o file XML nel file <span class="filepath"> Log Processing.cfg</span>. Il file di testo o i decodificatori XML definiti per estrarre campi di dati da file di registro e origini di registro XML. </p> <p> <b>Per aggiungere un nuovo gruppo di decodificatori</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Fai clic con il pulsante destro del mouse su <span class="uicontrol"> Decoder Group</span> e fai clic su <span class="uicontrol"> Aggiungi nuovo</span> &gt; <span class="uicontrol"> TextFileDecoderGroup</span> o <span class="uicontrol"> XMLDecoderGroup</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> Nel parametro Name del nuovo gruppo, immetti il nome desiderato del gruppo decoder. </li> 
     </ul> </p> <p> <p>Nota:  Quando si specifica un gruppo decodificatore nel file <span class="filepath"> Log Processing.cfg</span> per il profilo del set di dati, il nome deve corrispondere esattamente al nome immesso qui. Per ulteriori informazioni, consulta <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> File di registro</a>. </p> </p> <p> Per informazioni sui decodificatori che è possibile definire per ciascun gruppo, vedere <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Gruppi decoder file di testo</a> o <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> Gruppi decoder XML</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campi </td> 
   <td colname="col2"> <p>Elenca i campi definiti in <span class="wintitle"> Origini di registro</span> o <span class="wintitle"> Trasformazioni</span> in un file <span class="wintitle"> Configurazione set di dati di elaborazione del registro</span> ma utilizzati in trasformazioni, condizioni o dimensioni estese in un file <span class="wintitle"> Configurazione set di dati di trasformazione</span> devono essere elencati qui. </p> <p> Ogni campo qui sotto deve essere elencato in alcuni file <span class="wintitle"> Dataset Include</span> di elaborazione del registro: 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione voce di registro (Log Entry Condition) </td> 
   <td colname="col2"> <p>Facoltativo. Definisce le regole in base alle quali le voci di registro vengono considerate per l’inclusione nel set di dati. Vedere <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condizione voce di registro</a>. </p> <p> <p>Nota:  Per essere inclusa nel set di dati, una voce di registro deve soddisfare la <span class="wintitle"> Condizione voce di registro</span> nel file <span class="filepath"> Elaborazione registro.cfg</span> e in ogni file <span class="wintitle"> Elaborazione registro Dataset Include</span>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parametri </td> 
   <td colname="col2"> Facoltativo. Variabile a cui è possibile fare riferimento in altri parametri di configurazione. Per ulteriori informazioni, consulta <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definizione dei parametri in Dataset Include Files</a> (Definizione dei parametri nel set di dati). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rielaborazione </td> 
   <td colname="col2"> <p>Facoltativo. È possibile inserire qui qualsiasi carattere o combinazione di caratteri. La modifica di questo parametro e il salvataggio del file sul server di Data Workbench avvia la rielaborazione dei dati. </p> <p> Per informazioni sulla rielaborazione dei dati, vedere <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e ritrasformazione</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>Facoltativo. Nome della fase di elaborazione che si applica a questo file <span class="wintitle"> Dataset Include</span> di elaborazione del registro. Le fasi di elaborazione sono definite nel parametro Stages nel file <span class="filepath"> Log Processing.cfg</span> . </p> <p> <p>Nota:  Quando si specifica uno stage, il nome dello stage deve corrispondere esattamente al nome elencato nel parametro Stages nel file <span class="filepath"> Log Processing.cfg</span> per il profilo del set di dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trasformazioni </td> 
   <td colname="col2"> Facoltativo. Definisce le trasformazioni di dati che devono essere applicate durante l’elaborazione del registro. Per informazioni sui tipi di trasformazione disponibili, consulta <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Trasformazioni dati</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Per una descrizione dei parametri nel file [!DNL Log Processing.cfg], vedere [File di configurazione dell&#39;elaborazione del registro](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

Quando lavori con i file [!DNL Log Processing Dataset Include] , tieni presente quanto segue:

* La modifica di uno qualsiasi dei parametri in questo file richiede la rielaborazione di tutti i dati.
* È possibile aggiungere uno qualsiasi dei parametri descritti sopra al file [!DNL Log Processing Dataset Include] aprendo e modificando il file in Blocco note. Le modifiche apportate e salvate vengono visualizzate quando riapri il file in Data Workbench. Quando si aggiunge un nuovo parametro, utilizzare il tasto Space (non il tasto Tab) per far rientrare due (2) spazi a destra del livello di intestazione precedente.
