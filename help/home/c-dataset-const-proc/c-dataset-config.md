---
description: La configurazione del set di dati si riferisce al processo di modifica dei file di configurazione i cui parametri forniscono le regole per la costruzione del set di dati.
title: Informazioni sulla configurazione del set di dati
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
exl-id: 1358d08e-d81c-453d-a3a3-c1f279f38192
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 7%

---

# Informazioni sulla configurazione del set di dati{#understanding-dataset-configuration}

{{eol}}

La configurazione del set di dati si riferisce al processo di modifica dei file di configurazione i cui parametri forniscono le regole per la costruzione del set di dati.

Il set di dati costruito risiede fisicamente nel [!DNL temp.db] memorizzato nel computer server di Data Workbench, ma i file di configurazione del set di dati risiedono in una directory per un profilo. Un profilo contiene un set di file di configurazione che creano un set di dati (comprese le dimensioni estese) per uno scopo di analisi specifico. Inoltre, un profilo contiene le definizioni di entità quali metriche, dimensioni derivate, aree di lavoro, rapporti e visualizzazioni che consentono agli analisti di interagire con il set di dati e ottenere informazioni da esso.

Il profilo di cui vengono modificati i file di configurazione del set di dati, viene definito il profilo del set di dati. Un profilo di set di dati fa riferimento a più profili ereditati, che possono essere qualsiasi profilo creato e gestito in modo da poter configurare l’applicazione Adobe per soddisfare al meglio le tue esigenze di analisi. Un profilo di set di dati può anche fare riferimento a profili interni forniti con l’applicazione Adobe per formare la base per tutte le funzionalità disponibili nell’applicazione.

Per ulteriori informazioni sui diversi tipi di profili disponibili con le applicazioni Adobe, consulta la sezione *Guida utente di Data Workbench*.

<!--
c_req_config_files.xml
-->

Un profilo di set di dati per qualsiasi applicazione Adobe deve contenere i seguenti file di configurazione nel computer Insight Server:

* **Profile.cfg:** Elenca i profili ereditati e i server di elaborazione per il profilo. I server di elaborazione sono DPU di Insight Server che elaborano i dati per il profilo. Se è stato installato un cluster Insight Server, è possibile specificare più computer Insight Server per eseguire un singolo profilo.

   Per istruzioni su come aggiungere profili ereditati a un profilo di set di dati [!DNL Profile.cfg] vedi *Guida all’installazione e all’amministrazione dei prodotti server*. Per informazioni sull’installazione di un cluster Insight Server o sulla configurazione di un profilo di set di dati da eseguire su un cluster Insight Server, consulta la sezione *Guida all’installazione e all’amministrazione dei prodotti server*.

* **Set di dati\Log Processing.cfg:** Controlla la fase di elaborazione del registro del processo di costruzione del set di dati. Vedi [Elaborazione del registro](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061). Per ulteriori informazioni sulla [!DNL Log Processing.cfg] file, vedi [File di configurazione dell’elaborazione del registro](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md).

* **Set di dati\Transformation.cfg:** Controlla la fase di trasformazione del processo di costruzione del set di dati. Vedi [Trasformazione](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). La [!DNL Transformation.cfg] in genere configura il set di dati per l’analisi specifica del profilo. Per ulteriori informazioni sulla [!DNL Transformation.cfg] file, vedi [File di configurazione delle trasformazioni](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md).

* **Dataset Include Files (File inclusi nel set di dati):** A [!DNL dataset include] il file contiene un sottoinsieme dei parametri contenuti nel [!DNL Log Processing.cfg] o [!DNL Transformation.cfg] per il profilo del set di dati, ma viene memorizzato e gestito all’interno di un profilo ereditato. [!DNL Dataset include] i file integrano i file di configurazione del set di dati principali. Per ulteriori informazioni, consulta [Dataset Include Files (File inclusi nel set di dati)](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Il profilo di set di dati fornito durante l’implementazione dell’applicazione Adobe contiene un set di file di configurazione del set di dati che puoi aprire, modificare e salvare utilizzando [!DNL Profile Manager].

Per informazioni sulla [!DNL Profile Manager], vedi *Guida utente di Insight*.

<!--
c_addl_config_files.xml
-->

Sebbene non siano necessari per tutti i set di dati, questi file consentono di controllare altri aspetti del processo di creazione dei set di dati:

* **Elaborazione registro Mode.cfg:** La [!DNL Log Processing Mode.cfg] file ti consente di mettere in pausa l’elaborazione dei dati in un set di dati, specificare le origini offline o specificare la frequenza con cui il server di Data Workbench salva i file di stato. Vedi [File di configurazione aggiuntivi](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Server.cfg:** La [!DNL Server.cfg] file specifica la dimensione predefinita della cache dei dati (in byte) per i computer di Data Workbench che si connettono al server di Data Workbench. Vedi [File di configurazione aggiuntivi](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004).

* **Transform.cfg e Transform Mode.cfg:** Questi file sono disponibili solo se hai concesso la licenza per la funzionalità di trasformazione dei dati da utilizzare con la tua applicazione Adobe. La [!DNL Transform.cfg] il file contiene i parametri che definiscono le origini di registro e le trasformazioni dei dati per la funzionalità di trasformazione. Le trasformazioni definite manipolano i dati di origine e li trasmettono in un formato specificato dall&#39;utente. La [!DNL Insight Transform Mode.cfg] file consente di mettere in pausa l’elaborazione dei dati in un set di dati, specificare le origini offline o specificare la frequenza con cui Insight Server che esegue la funzionalità di trasformazione salva i suoi file di stato. Vedi [Funzionalità di trasformazione](https://experienceleague.adobe.com/docs/data-workbench/using/server-admin-install/transform/t-config-tfm.html).

<!--
c_next_steps.xml
-->

Per informazioni su specifiche attività di configurazione dei set di dati, utilizza la tabella seguente per individuare e leggere le attività di tuo interesse:

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Se volete... </th> 
   <th colname="col2" class="entry"> Consulta... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definire le origini di registro </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Origini del registro </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Determinare quali voci di registro inserire nel set di dati durante l’elaborazione del registro </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtri dati</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934">Condizione voce di registro (Log Entry Condition)</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Abilita la suddivisione degli ID di tracciamento con grandi quantità di dati evento </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Divisione tasti</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurare un Insight Server da eseguire come unità di file server </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurazione di un’unità del file server di Insight Server </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurare un Insight Server da eseguire come server di normalizzazione centralizzato </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurazione di un’unità del file server di Insight Server </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imposta il fuso orario da utilizzare per creare dimensioni temporali e effettuare conversioni temporali </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fusi orari </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apporta modifiche minori ai file di configurazione del set di dati inclusi nei profili interni forniti da Adobe </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> Modifica di Dataset Include Files (File inclusi nel set di dati) esistente </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Specificare nuovi campi di dati da passare dall'elaborazione del registro alla trasformazione </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e">Creazione di nuovi Dataset Include Files (File inclusi nel set di dati)</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab">Elaborazione del registro di Dataset Include Files (File inclusi nel set di dati)</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definire le trasformazioni </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Trasformazioni dei dati </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e">Creazione di nuovi Dataset Include Files (File inclusi nel set di dati)</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace">Transformation Dataset Include Files (File inclusi nel set di dati di trasformazione)</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creare dimensioni estese </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimensioni estese </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e">Creazione di nuovi Dataset Include Files (File inclusi nel set di dati)</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace">Transformation Dataset Include Files (File inclusi nel set di dati di trasformazione)</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definire i parametri da utilizzare durante l’elaborazione o la trasformazione del registro </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50">Definizione dei parametri di Dataset Include Files (File inclusi nel set di dati)</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scopri le interfacce Insight che consentono di monitorare o gestire il set di dati </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> Utilizzo delle Interfacce di configurazione del set di dati </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nascondere alcune dimensioni estese in modo che non vengano visualizzate nel menu delle dimensioni in Insight </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Nascondere i componenti del set di dati </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Escludere alcuni file di configurazione del set di dati in un profilo che non è possibile modificare o non si desidera modificare </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Nascondere i componenti del set di dati </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rielaborazione del set di dati </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e riconversione </a> </p> </td> 
  </tr> 
 </tbody> 
</table>
