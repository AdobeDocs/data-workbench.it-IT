---
description: Passaggi per la modifica del file Transformation.cfg per un profilo di set di dati.
solution: Analytics
title: Modifica del file di configurazione delle trasformazioni
topic: Data workbench
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Modifica del file di configurazione delle trasformazioni{#editing-the-transformation-configuration-file}

Passaggi per la modifica del file Transformation.cfg per un profilo di set di dati.

1. Quando lavori nel profilo del set di dati, apri il set di dati [!DNL Profile Manager] e fai clic **[!UICONTROL Dataset]** per visualizzarne il contenuto.

   Per informazioni sull&#39;apertura e l&#39;utilizzo di [!DNL Profile Manager], vedere la Guida *utente di Workbench* dati.

   >[!NOTE]
   >
   >All&#39;interno della directory Dataset potrebbe esistere una sottodirectory Transformation. Questa sottodirectory contiene i [!DNL Transformation Dataset Include] file creati per uno o più profili ereditati. Per informazioni sui [!DNL Transformation Dataset Include] file, vedere [Set di dati Includi file](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md).

1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Transformation.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Viene [!DNL Transformation.cfg] visualizzata la finestra.

   È inoltre possibile aprire il [!DNL Transformation.cfg] file da un [!DNL Transformation Dependency Map]. Per informazioni su [!DNL transformation dependency maps], vedere Strumenti [di configurazione](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)DataSet.

1. Modificate i parametri nel file di configurazione utilizzando la seguente tabella come guida.

   Quando si modifica il [!DNL Transformation.cfg] file all&#39;interno di una finestra del workbench dati, è possibile utilizzare i tasti di scelta rapida per le funzioni di modifica di base, quali Taglia (Ctrl+x ), Copia (Ctrl+c), Incolla (Ctrl+v), Annulla (Ctrl+z ), Ripristina (Ctrl+Maiusc+Z ), Seleziona la sezione (Clic+trascinamento) e seleziona tutto (Ctrl+a ). Inoltre, potete utilizzare i collegamenti per copiare e incollare il testo da un file di configurazione ( [!DNL .cfg]) a un altro.

   >[!NOTE]
   >
   >I [!DNL Transformation Dataset Include] file per un profilo ereditato contengono un sottoinsieme dei parametri descritti nella tabella seguente, nonché alcuni parametri aggiuntivi. Per informazioni sui [!DNL Transformation Dataset Include] file, consultate [DataSet Include Files (Includi file nei set di dati)](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md)

   <table id="table_5E184F67CCEC4421B2BBD4261711A6FE"> 
   <thead> 
   <tr> 
      <th colname="col1" class="entry"> Parametro </th> 
      <th colname="col2" class="entry"> Descrizione </th> 
   </tr> 
   </thead>
   <tbody> 
   <tr> 
      <td colname="col1"> Ora di fine </td> 
      <td colname="col2"> <p>Facoltativo. Filtrare i dati per includere voci di registro con marche temporali fino a, ma non incluse, questa volta. Adobe consiglia di utilizzare per il momento uno dei seguenti formati: 
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 1 gennaio 2013 HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> 1 gen 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Ad esempio, se specificate "29 luglio 2013 00:00:00 EDT" come Ora di fine, i dati sono inclusi fino al 28 luglio 2013, alle 11:59:59 PM EDT. </p> <p> È necessario specificare un fuso orario. Il fuso orario predefinito non è GMT se non specificato. Per un elenco delle abbreviazioni del fuso orario supportate dal server workbench dati, vedere <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codici del fuso orario </a>. </p> <p> <p>Nota:  Se si specifica un valore per Ora di fine, viene impostato e applicato un parametro denominato Ora di fine durante la fase di trasformazione della costruzione del set di dati. Per informazioni sui parametri, vedere <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definizione dei parametri in Dataset Includi file </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dimensioni estese </td> 
      <td colname="col2"> Facoltativo. Adobe consiglia di definire le dimensioni estese in uno o più file <span class="wintitle"> Transformation Dataset Include (Includi </span> file). Per informazioni, consultate <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> DataSet di trasformazioni Includi file </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Soglia hash </td> 
      <td colname="col2"> <p>Facoltativo. Fattore di campionamento per il sottocampionamento casuale delle righe. Se è impostato su un numero n, solo uno su ogni n ID di tracciamento entra nel dataset, riducendo il numero totale di righe nel dataset di un fattore n. Per creare un set di dati che richiede una precisione del 100% (ovvero per includere tutte le righe), impostare Soglia hash su 1. </p> <p> Se la Soglia hash è specificata nei file <span class="filepath"> Log Processing.cfg </span> e <span class="filepath"> Transformation.cfg </span> , non viene applicata in sequenza; viene applicato il massimo dei valori impostati in uno dei file di configurazione. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condizione voce di registro </td> 
      <td colname="col2"> Facoltativo. Definisce le regole in base alle quali le voci di registro emesse dall'elaborazione del registro vengono considerate per l'inclusione nel profilo del set di dati. Vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condizione di voce di registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nuova condizione del visitatore </td> 
      <td colname="col2"> Facoltativo. Da utilizzare con i dati Web. Definisce le regole in base alle quali i visitatori vengono considerati per l'inclusione nei dati. La <span class="wintitle"> nuova condizione del visitatore </span> definisce la prima voce di registro per un visitatore (ordinata per ora) che deve essere utilizzata nel set di dati. Tutte le voci di registro successive per questo visitatore sono incluse nel set di dati, indipendentemente dal fatto che soddisfino o meno questa condizione. Consulta <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> Nuova condizione del visitatore </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rielabora </td> 
      <td colname="col2"> <p>Facoltativo. È possibile inserire qui qualsiasi carattere o combinazione di caratteri. La modifica di questo parametro e il salvataggio del file avvia la riconversione dei dati. </p> <p> Per informazioni sulla rielaborazione dei dati, vedere <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e </a>Trasformazione. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Controllo schema </td> 
      <td colname="col2"> True o false. Se true, il server workbench dati identifica i problemi di corruzione del dataset e registra le informazioni sui problemi nei file di registro nella directory Trace del server workbench dati. Il valore predefinito è true. Adobe consiglia di lasciare sempre questo parametro impostato su true. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Stadi </td> 
      <td colname="col2"> <p>Facoltativo. I nomi delle fasi di elaborazione che possono essere utilizzate in <span class="wintitle"> Transformation Dataset includono </span> i file. Le fasi di elaborazione consentono di ordinare le trasformazioni definite in <span class="wintitle"> Transformation Dataset Include </span> i file. Questo parametro è molto utile se avete definito una o più trasformazioni all'interno di più file <span class="wintitle"> Transformation Dataset Include </span> e desiderate che trasformazioni specifiche vengano eseguite in punti specifici durante la trasformazione. </p> <p> L'ordine in cui vengono elencati i passaggi qui determina l'ordine in cui le trasformazioni nei file <span class="wintitle"> Transformation Dataset Include (Includi set di dati di trasformazione) vengono eseguite durante </span> la trasformazione. <span class="wintitle"> La preelaborazione </span> e il <span class="wintitle"> posttrattamento </span> sono fasi integrate; <span class="wintitle"> La preelaborazione </span> è sempre la prima fase, mentre la <span class="wintitle"> postelaborazione </span> è sempre l'ultima fase. Per impostazione predefinita, è presente uno stage denominato <span class="wintitle"> Default </span>. </p> <p> <b>Per aggiungere una nuova fase di elaborazione</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> Nella finestra <span class="filepath"> Transformation.cfg </span> , fare clic con il pulsante destro del mouse su <span class="uicontrol"> Stages </span> e scegliere <span class="uicontrol"> Aggiungi nuovo </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> Immettete un nome per il nuovo passaggio. </li> 
      </ul> </p> <p> <b>Per eliminare una fase di elaborazione esistente</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> Fare clic con il pulsante destro del mouse sul numero corrispondente all'area di visualizzazione da eliminare e scegliere <span class="uicontrol"> Rimuovi </span><i>&lt; <span class="uicontrol"> #stage_number </span>&gt;</i>. </li> 
      </ul> </p> <p> <p>Nota:  Quando si specifica uno stage in un set di dati di <span class="wintitle"> trasformazione che include </span> i file, il nome dell'area di visualizzazione deve corrispondere esattamente al nome immesso. Per ulteriori informazioni sui dataset includono i file, vedere <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Dataset Include i file </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ora di inizio </td> 
      <td colname="col2"> <p>Facoltativo. Filtrare i dati per includere voci di registro con marche temporali all’ora o dopo. Adobe consiglia di utilizzare per il momento uno dei seguenti formati: 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 1 gennaio 2013 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 1 gen 2013 HH:MM:SS GMT </li> 
      </ul> </p> <p> Ad esempio, se specificate il 29 luglio 2013 00:00:00 EDT come ora di <span class="wintitle"> inizio </span> sono inclusi i dati a partire dal 29 luglio 2013, alle 01:00:00 EDT delle ore 12. </p> <p> È necessario specificare un fuso orario. Il fuso orario predefinito non è GMT se non specificato. Per un elenco delle abbreviazioni del fuso orario supportate dal server workbench dati, vedere <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codici del fuso orario </a>. </p> <p> <p>Nota:  Se si specifica un valore per Ora di inizio, un parametro denominato Ora di inizio viene impostato e applicato durante la fase di trasformazione della costruzione del set di dati. Per informazioni sui parametri, vedere <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definizione dei parametri in Dataset Includi file </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Trasformazioni </td> 
      <td colname="col2"> Facoltativo. Adobe consiglia di definire le trasformazioni per la fase di trasformazione della creazione di set di dati in uno o più file <span class="wintitle"> Transformation Dataset Include (Includi </span> file). Per informazioni, consultate <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> DataSet di trasformazioni Includi file </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuso orario </td> 
      <td colname="col2"> <p>Fuso orario del profilo del dataset. I fusi orari vengono utilizzati per le conversioni temporali e per la creazione di dimensioni temporali. Consultate <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fusi orari </a>. </p> <p> <p>Nota:  Quando viene definito nel file <span class="filepath"> Log Processing.cfg </span> , il parametro Time Zone viene utilizzato solo per le conversioni temporali. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.
1. Fare [!DNL Profile Manager]clic con il pulsante destro del mouse sul segno di spunta [!DNL Transformation.cfg]nella [!DNL User] colonna, quindi scegliere **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** per rendere attive le modifiche locali. Il ripristino dei dati inizia dopo la sincronizzazione del profilo del set di dati.

   >[!NOTE]
   >
   >Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe, in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti per tali profili.

   Per informazioni sulla rielaborazione o la trasformazione dei dati, vedere [Rielaborazione e trasformazione](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
