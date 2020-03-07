---
description: La configurazione del set di dati si riferisce al processo di modifica dei file di configurazione i cui parametri forniscono le regole per la creazione del set di dati.
solution: Analytics
title: Informazioni sulla configurazione del set di dati
topic: Data workbench
uuid: 813933d1-f52d-4584-8edd-ce9cd4aed74a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Informazioni sulla configurazione del set di dati{#understanding-dataset-configuration}

La configurazione del set di dati si riferisce al processo di modifica dei file di configurazione i cui parametri forniscono le regole per la creazione del set di dati.

Il dataset costruito risiede fisicamente nel [!DNL temp.db] file memorizzato nel computer server workbench dati, ma i file di configurazione per il dataset risiedono all&#39;interno di una directory per un profilo. Un profilo contiene un set di file di configurazione che crea un set di dati (incluse le dimensioni estese) per uno scopo di analisi specifico. Inoltre, un profilo contiene le definizioni di entità quali metriche, dimensioni derivate, aree di lavoro, rapporti e visualizzazioni che consentono agli analisti di interagire con il dataset e ottenere informazioni da esso.

Il profilo i cui file di configurazione del set di dati che si stanno modificando è denominato profilo del set di dati. Un profilo set di dati fa riferimento a più profili ereditati, che possono essere qualsiasi profilo creato e gestito in modo da poter configurare l’applicazione Adobe in base alle esigenze di analisi. Un profilo dataset può anche fare riferimento a profili interni forniti con l&#39;applicazione Adobe per costituire la base per tutte le funzionalità disponibili nell&#39;applicazione.

Per ulteriori informazioni sui diversi tipi di profili disponibili con le applicazioni Adobe, vedere la Guida *utente di Workbench* dati.

<!--
c_req_config_files.xml
-->

Un profilo dataset per qualsiasi applicazione Adobe deve contenere i seguenti file di configurazione nel computer Insight Server:

* **Profile.cfg:** Elenca i profili ereditati e i server di elaborazione per il profilo. I server di elaborazione sono i DPU di Insight Server che elaborano i dati per il profilo. Se avete installato un cluster Insight Server, potete specificare più computer Insight Server per eseguire un unico profilo.

   Per istruzioni sull&#39;aggiunta di profili ereditati al [!DNL Profile.cfg] file di un profilo di dataset, vedere la Guida all&#39;installazione e all&#39;amministrazione dei prodotti *server*. Per informazioni sull&#39;installazione di un cluster Insight Server o sulla configurazione di un profilo di set di dati da eseguire su un cluster Insight Server, vedere la Guida *all&#39;installazione e all&#39;amministrazione dei prodotti* server.

* **Set di dati\Log Processing.cfg:** Controlla la fase di elaborazione del log del processo di costruzione del dataset. Vedere [Elaborazione](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-8a63892878004dc389c7dad784fcb061)log. Per ulteriori informazioni sul [!DNL Log Processing.cfg] file, vedere [File](../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)di configurazione Elaborazione log.

* **Set di dati\Transformation.cfg:** Controlla la fase di trasformazione del processo di costruzione del dataset. Vedere [Trasformazione](../../home/c-dataset-const-proc/c-dataset-constr.md#concept-88f72e0897a744b5bc03df5039264dda). Il [!DNL Transformation.cfg] file in genere configura il dataset per l&#39;analisi specifica del profilo. Per ulteriori informazioni sul [!DNL Transformation.cfg] file, vedere [File](../../home/c-dataset-const-proc/c-trans-config-file/c-abt-trans-config-file.md)di configurazione delle trasformazioni.

* **I set di dati includono i file:** Un [!DNL dataset include] file contiene un sottoinsieme dei parametri contenuti nel [!DNL Log Processing.cfg] file o nel [!DNL Transformation.cfg] profilo del dataset, ma viene memorizzato e gestito all&#39;interno di un profilo ereditato. [!DNL Dataset include] i file completano i file di configurazione del dataset principale. Per ulteriori informazioni, vedere [Set di dati Includi file](../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

Il profilo set di dati fornito durante l&#39;implementazione dell&#39;applicazione Adobe contiene un set di file di configurazione di set di dati che puoi aprire, modificare e salvare utilizzando l&#39; [!DNL Profile Manager].

Per informazioni su [!DNL Profile Manager]di esso, consulta la *Guida* utente di Insight.

<!--
c_addl_config_files.xml
-->

Sebbene non siano necessari per tutti i set di dati, questi file consentono di controllare altri aspetti del processo di creazione dei set di dati:

* **Modalità di elaborazione log.cfg:** Il [!DNL Log Processing Mode.cfg] file consente di mettere in pausa l&#39;elaborazione dei dati in un dataset, specificare le origini offline o specificare la frequenza con cui il server workbench dati salva i propri file di stato. Consultate File [di configurazione](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)aggiuntivi.

* **Server.cfg:** Il [!DNL Server.cfg] file specifica la dimensione predefinita della cache dei dati (in byte) per i computer workbench dati che si connettono al server workbench dati. Consultate File [di configurazione](../../home/c-dataset-const-proc/c-add-config-files/c-add-config-files.md#concept-1afef4f88f1e467ab4326875fd1d3004)aggiuntivi.

* **Transform.cfg e Transform Mode.cfg:** Questi file sono disponibili solo se avete concesso in licenza la funzionalità di trasformazione dei dati da utilizzare con l’applicazione Adobe. Il [!DNL Transform.cfg] file contiene i parametri che definiscono le origini del registro e le trasformazioni dei dati per la funzionalità di trasformazione. Le trasformazioni definite manipolano i dati di origine e li restituiscono in un formato specificato dall&#39;utente. Il [!DNL Insight Transform Mode.cfg] file consente di mettere in pausa l&#39;elaborazione dei dati in un dataset, specificare le origini offline o specificare la frequenza con cui il server Insight che esegue la funzionalità di trasformazione salva i file di stato. Consultate [Funzionalità](https://docs.adobe.com/content/help/en/data-workbench/using/server-admin-install/transform/t-config-tfm.html)di trasformazione.

<!--
c_next_steps.xml
-->

Per informazioni su specifiche attività di configurazione del dataset, utilizzare la tabella seguente per individuare e leggere le attività di interesse:

<table id="table_394CFB5135274545B5DA37952EC6943E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Se vuoi... </th> 
   <th colname="col2" class="entry"> Consulta... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Definizione delle origini di registro </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea"> Origini log </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Determinare quali voci di registro immettere nel dataset durante l'elaborazione del registro </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-41bd49bf6b64442d91c232ec67529a3d"> Filtri dati</a> </p> <p> <a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condizione voce di registro</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Abilitare la suddivisione degli ID di tracciamento con grandi quantità di dati evento </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-64b416bbe42f4d689f90df246f7f7caf"> Suddivisione tasti</a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurare un server Insight da eseguire come unità del file server </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurazione di un'unità del file server Insight Server </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Configurare un server di informazioni da eseguire come server di normalizzazione centralizzato </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-log-proc-config-file/c-ins-svr-file-svr-unit.md#concept-995abff3fce34e439fb3f7f47191c80d"> Configurazione di un'unità del file server Insight Server </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Impostare il fuso orario da utilizzare per creare dimensioni temporali e effettuare conversioni temporali </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fusi orari </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Apportate lievi modifiche ai file di configurazione del dataset inclusi nei profili interni forniti da Adobe </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077"> Modifica dei set di dati esistenti Includi file </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Specificare nuovi campi di dati da passare dall'elaborazione del registro alla trasformazione </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Creazione di nuovi set di dati con i file </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab"> I Dati Di Elaborazione Del Registro Includono I File </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definire le trasformazioni </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-data-trans/c-abt-transf.md"> Trasformazioni dei dati </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Creazione di nuovi set di dati con i file </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> I set di dati delle trasformazioni includono i file </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Creazione di dimensioni estese </p> </td> 
   <td colname="col2"> <p> <a href="../../home/c-dataset-const-proc/c-ex-dim/c-abt-ex-dim.md"> Dimensioni estese </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-create-new-dataset-inc-files.md#task-b29f30605c374a6ca747ac843337b06e"> Creazione di nuovi set di dati con i file </a> </p> <p> <a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> I set di dati delle trasformazioni includono i file </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Definire i parametri da utilizzare per l'elaborazione o la trasformazione del registro </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definizione dei parametri per l'inclusione di file nei set di dati </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scopri le interfacce Insight che consentono di monitorare o gestire il dataset </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-int/c-dataset-config-int.md#concept-0ea33a52ce234ec8951e7b4430fbc5ab"> Utilizzo Delle Interfacce Di Configurazione Del Set Di Dati </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nascondere determinate dimensioni estese in modo che non vengano visualizzate nel menu delle dimensioni in Insight </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Nascondere i componenti del set di dati </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ignorare alcuni file di configurazione del set di dati in un profilo che non è possibile modificare o non si desidera modificare </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-dataset-config-tools/c-hide-dataset-comp/c-hide-dataset-comp.md#concept-50d9a004736f42f6b0aa7cde0d6148ff"> Nascondere i componenti del set di dati </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rielabora il set di dati </p> </td> 
   <td colname="col2"> <p><a href="../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e riconversione </a> </p> </td> 
  </tr> 
 </tbody> 
</table>

