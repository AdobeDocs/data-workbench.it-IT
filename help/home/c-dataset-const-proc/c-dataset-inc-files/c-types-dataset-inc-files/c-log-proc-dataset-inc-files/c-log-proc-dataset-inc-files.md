---
description: Il file di inclusione del set di dati di elaborazione del registro per un profilo ereditato contiene i parametri associati alla fase di elaborazione del registro della costruzione del set di dati.
title: Elaborazione del registro di Dataset Include Files (File inclusi nel set di dati)
uuid: 8bf99c9a-f674-4a07-bb3e-de0d9efc9716
exl-id: 06d8046d-6bac-4ccd-bcef-06f7c9ec7619
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '660'
ht-degree: 3%

---

# Elaborazione del registro di Dataset Include Files (File inclusi nel set di dati){#log-processing-dataset-include-files}

{{eol}}

Il file di inclusione del set di dati di elaborazione del registro per un profilo ereditato contiene i parametri associati alla fase di elaborazione del registro della costruzione del set di dati.

La prima riga di un [!DNL Log Processing Dataset Include] il file definisce un tipo [!DNL LogProcessingInclude] che supporta i parametri Decoder Groups, Fields, Log Entry Condition, Parameters, Reprocess, Stage e Transformations. Tutti gli altri parametri per l’elaborazione del registro devono essere definiti nel [!DNL Log Processing.cfg] nella directory Dataset del profilo di set di dati. È possibile assegnare un nome a [!DNL Log Processing Dataset Include] archivia tutto ciò che vuoi, ma la relativa estensione di file deve essere [!DNL .cfg]. Il file deve essere memorizzato nel *nome profilo ereditato*\Dataset\Log Processing directory. Poiché i file vengono caricati in modo ricorsivo durante la fase di elaborazione del registro della costruzione del set di dati, puoi archiviare il [!DNL Log Processing Dataset Include] file a qualsiasi livello all’interno della directory (ad esempio, *nome profilo ereditato*\Dataset\Log Processing\*nome cartella*\*include nome file*.cfg).

>[!NOTE]
>
>Molti parametri di configurazione specifici per il Web per Site sono definiti in [!DNL Log Processing Dataset Include] file. Per informazioni su questi parametri, vedi [Impostazioni di configurazione per i dati web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

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
   <td colname="col2"> <p>Obbligatorio se sono state definite origini di file di registro o di file di registro XML nel <span class="filepath"> Log Processing.cfg</span> file. Il file di testo o i decodificatori XML definiti per estrarre campi di dati da file di registro e origini di registro XML. </p> <p> <b>Per aggiungere un nuovo gruppo di decodificatori</b> 
     <ul id="ul_54087499003C48C8B0AD9660A2F46EA9"> 
      <li id="li_E361861E61D246DDB3964C97CC5187E9"> Fai clic con il pulsante destro del mouse <span class="uicontrol"> Gruppo decodificatore</span> e fai clic su <span class="uicontrol"> Aggiungi nuovo</span> &gt; <span class="uicontrol"> TextFileDecoderGroup</span> o <span class="uicontrol"> XMLDecoderGroup</span>. </li> 
      <li id="li_B2D61A0763AD4FEDB619BF9550EF4602"> Nel parametro Name del nuovo gruppo, immetti il nome desiderato del gruppo decoder. </li> 
     </ul> </p> <p> <p>Nota: Quando si specifica un gruppo decodificatore nel <span class="filepath"> Log Processing.cfg</span> per il profilo del set di dati, il nome deve corrispondere esattamente al nome immesso qui. Per ulteriori informazioni, consulta <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> File di registro</a>. </p> </p> <p> Per informazioni sui decodificatori che è possibile definire per ciascun gruppo, consulta <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#concept-0db34988e17c41bfb1797f1d8e78aabd"> Gruppi decodificatore file di testo</a> o <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-xml-dec-grps.md#concept-5eda5ab253724674832f6951e2a0d1c3"> Gruppi decodificatore XML</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campi </td> 
   <td colname="col2"> <p>Elenca i campi definiti in <span class="wintitle"> Origini del registro</span> o <span class="wintitle"> Trasformazioni</span> in <span class="wintitle"> Configurazione set di dati di elaborazione del registro</span> ma utilizzati in trasformazioni, condizioni o dimensioni estese in un <span class="wintitle"> Configurazione set di dati di trasformazione</span> file deve essere elencato qui. </p> <p> Ogni campo qui sotto deve essere elencato in alcuni <span class="wintitle"> Include set di dati di elaborazione del registro</span> file: 
     <ul id="ul_D1BB18A80D874C0B9B54DA361698EB30"> 
      <li id="li_7E8B5B697BDA408DBE10D9A63AF295AC"> x-trackingid </li> 
      <li id="li_F5DEE90A596A4A1C86AF874653C4048C"> x-timestamp </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione voce di registro (Log Entry Condition) </td> 
   <td colname="col2"> <p>Facoltativo. Definisce le regole in base alle quali le voci di registro vengono considerate per l’inclusione nel set di dati. Vedi <a href="../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condizione voce di registro</a>. </p> <p> <p>Nota: Per essere incluso nel set di dati, una voce di registro deve soddisfare <span class="wintitle"> Condizione voce di registro</span> in <span class="filepath"> Log Processing.cfg</span> file e in ogni <span class="wintitle"> Include set di dati di elaborazione del registro</span> file. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Parametri </td> 
   <td colname="col2"> Facoltativo. Variabile a cui è possibile fare riferimento in altri parametri di configurazione. Per ulteriori informazioni, consulta <a href="../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definizione dei parametri di Dataset Include Files (File inclusi nel set di dati)</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Rielaborazione </td> 
   <td colname="col2"> <p>Facoltativo. È possibile inserire qui qualsiasi carattere o combinazione di caratteri. La modifica di questo parametro e il salvataggio del file sul server di Data Workbench avvia la rielaborazione dei dati. </p> <p> Per informazioni sulla rielaborazione dei dati, consulta <a href="../../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e ritrasformazione</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Stage </td> 
   <td colname="col2"> <p>Facoltativo. Nome della fase di elaborazione che si applica a questo <span class="wintitle"> Include set di dati di elaborazione del registro</span> file. Le fasi di elaborazione sono definite nel parametro Stages nel <span class="filepath"> Log Processing.cfg</span> file. </p> <p> <p>Nota: Quando si specifica uno stage, il nome dello stage deve corrispondere esattamente al nome elencato nel parametro Stages nel <span class="filepath"> Log Processing.cfg</span> per il profilo del set di dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trasformazioni </td> 
   <td colname="col2"> Facoltativo. Definisce le trasformazioni di dati che devono essere applicate durante l’elaborazione del registro. Per informazioni sui tipi di trasformazione disponibili, consulta <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Trasformazioni dei dati</a>. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Per la descrizione dei parametri nella sezione [!DNL Log Processing.cfg] file, vedi [File di configurazione dell’elaborazione del registro](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

Quando lavori con [!DNL Log Processing Dataset Include] file:

* La modifica di uno qualsiasi dei parametri in questo file richiede la rielaborazione di tutti i dati.
* Puoi aggiungere uno qualsiasi dei parametri descritti in precedenza al [!DNL Log Processing Dataset Include] aprire e modificare il file in Blocco note. Le modifiche apportate e salvate vengono visualizzate quando riapri il file in Data Workbench. Quando si aggiunge un nuovo parametro, utilizzare il tasto Space (non il tasto Tab) per far rientrare due (2) spazi a destra del livello di intestazione precedente.
