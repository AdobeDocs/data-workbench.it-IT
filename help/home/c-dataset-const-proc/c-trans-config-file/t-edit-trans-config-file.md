---
description: Passaggi per modificare il file Transformation.cfg per un profilo di set di dati.
title: Modifica del file di configurazione delle trasformazioni
uuid: 77b9e566-4a9a-4ea1-b5ab-63a4574c0fdb
exl-id: 3fab17a4-d356-4548-b977-f5d409870753
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1135'
ht-degree: 2%

---

# Modifica del file di configurazione delle trasformazioni{#editing-the-transformation-configuration-file}

Passaggi per modificare il file Transformation.cfg per un profilo di set di dati.

1. Quando lavori nel profilo del set di dati, apri il [!DNL Profile Manager] e fai clic su **[!UICONTROL Dataset]** per visualizzarne il contenuto.

   Per informazioni sull&#39;apertura e l&#39;utilizzo di [!DNL Profile Manager], vedere la *Guida utente alla Data Workbench*.

   >[!NOTE]
   >
   >Potrebbe esistere una sottodirectory Transformation all&#39;interno della directory Dataset. Questa sottodirectory contiene i file [!DNL Transformation Dataset Include] creati per uno o più profili ereditati. Per informazioni sui file [!DNL Transformation Dataset Include], consulta [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md) (File inclusi nel set di dati).

1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Transformation.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**. Viene visualizzata la finestra [!DNL Transformation.cfg].

   Puoi anche aprire il file [!DNL Transformation.cfg] da un [!DNL Transformation Dependency Map]. Per informazioni su [!DNL transformation dependency maps], consulta [Strumenti di configurazione del set di dati](../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

1. Modifica i parametri nel file di configurazione utilizzando la seguente tabella come guida.

   Quando modifichi il file [!DNL Transformation.cfg] all’interno di una finestra di Data Workbench, puoi utilizzare i tasti di scelta rapida per le funzioni di modifica di base, tra cui Taglia (Ctrl+x ), Copia (Ctrl+c) , Incolla (Ctrl+v ), Annulla (Ctrl+z ), Ripristina (Ctrl+Maiusc+Z ), seleziona la sezione (clic+trascina) e seleziona tutto (Ctrl+a ). Inoltre, è possibile utilizzare le scelte rapide per copiare e incollare il testo da un file di configurazione ( [!DNL .cfg]) a un altro.

   >[!NOTE]
   >
   >I file [!DNL Transformation Dataset Include] per un profilo ereditato contengono un sottoinsieme dei parametri descritti nella tabella seguente e alcuni parametri aggiuntivi. Per informazioni sui file [!DNL Transformation Dataset Include], consulta [Dataset Include Files](../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md) (File inclusi nel set di dati)

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
      <td colname="col2"> <p>Facoltativo. Filtra i dati per includere voci di registro con marche temporali fino a questa volta, ma non incluse. L'Adobe consiglia di utilizzare per il tempo uno dei seguenti formati: 
      <ul id="ul_1EC55DA4936946C98E447E1476E8280F"> 
       <li id="li_F2D862833F4B451C965E1ED6C05DCE1B"> 1 gennaio 2013 HH:MM:SS EDT </li> 
       <li id="li_EB7FFEB2E2C24EAFB8E4B14F2479DA3D"> 1 gennaio 2013 OH:MM:SS GMT </li> 
      </ul> </p> <p> Ad esempio, specificando "29 luglio 2013 00:00:00 EDT" come Ora di fine sono inclusi i dati fino al 28 luglio 2013, alle 11:59:59 PM EDT. </p> <p> È necessario specificare un fuso orario. Il fuso orario non viene impostato su GMT se non viene specificato. Per un elenco delle abbreviazioni del fuso orario supportate dal server di Data Workbench, consulta <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codici del fuso orario </a>. </p> <p> <p>Nota:  Se si specifica un valore per Ora di fine, viene impostato e applicato un parametro denominato Ora di fine durante la fase di trasformazione della costruzione del set di dati. Per informazioni sui parametri, consulta <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definizione dei parametri in Dataset Include Files (File inclusi nel set di dati) </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Dimensioni estese </td> 
      <td colname="col2"> Facoltativo. Adobe consiglia di definire dimensioni estese in uno o più file <span class="wintitle"> Dataset di trasformazione Include </span>. Per informazioni, consulta <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Dataset Include Files (File inclusi nel set di dati di trasformazione) </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Soglia hash </td> 
      <td colname="col2"> <p>Facoltativo. Un fattore di campionamento per il sottocampionamento casuale delle righe. Se è impostato su un numero n, solo uno su ogni n ID di tracciamento entra nel set di dati, riducendo il numero totale di righe nel set di dati di un fattore n. Per creare un set di dati che richiede una precisione del 100% (ovvero per includere tutte le righe), imposta la soglia hash su 1. </p> <p> Se Hash Threshold è specificato nei file <span class="filepath"> Log Processing.cfg </span> e <span class="filepath"> Transformation.cfg </span>, non viene applicato in sequenza; si applica il massimo dei valori impostati in entrambi i file di configurazione. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Condizione voce di registro (Log Entry Condition) </td> 
      <td colname="col2"> Facoltativo. Definisce le regole in base alle quali le voci di registro generate dall’elaborazione del registro vengono considerate per l’inclusione nel profilo del set di dati. Vedere <a href="../../../home/c-dataset-const-proc/c-log-proc-config-file/c-info-log-proc-param.md#concept-ecaff95cee4e40bc90f81e099c5fc934"> Condizione voce di registro </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Nuova condizione del visitatore (New Visitor Condition) </td> 
      <td colname="col2"> Facoltativo. Da utilizzare con i dati web. Definisce le regole in base alle quali i visitatori vengono considerati per l’inclusione nei dati. La <span class="wintitle"> Nuova condizione visitatore </span> definisce la prima voce di registro per un visitatore (ordinata per ora) che deve essere utilizzata nel set di dati. Tutte le voci di registro successive per questo visitatore sono incluse nel set di dati indipendentemente dal fatto che soddisfino questa condizione. Consulta <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-new-vstr-con.md#concept-1d0d8e26718447ad9d235e00b33a36f3"> Nuova condizione del visitatore </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Rielaborazione </td> 
      <td colname="col2"> <p>Facoltativo. È possibile inserire qui qualsiasi carattere o combinazione di caratteri. La modifica di questo parametro e il salvataggio del file avvia la riconversione dei dati. </p> <p> Per informazioni sulla rielaborazione dei dati, vedere <a href="../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md"> Rielaborazione e ritrasformazione </a>. </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Controllo dello schema </td> 
      <td colname="col2"> True o false. Se true, il server di Data Workbench identifica i problemi di corruzione dei set di dati e registra le informazioni sui problemi nei file di registro nella directory Trace del server di Data Workbench. Il valore predefinito è vero. Adobe consiglia di lasciare questo parametro impostato su true in qualsiasi momento. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fasi </td> 
      <td colname="col2"> <p>Facoltativo. I nomi delle fasi di elaborazione che possono essere utilizzate nei file <span class="wintitle"> Dataset di trasformazione Includono </span>. Le fasi di elaborazione forniscono un modo per ordinare le trasformazioni definite nei file <span class="wintitle"> Dataset di trasformazione Include </span> . Questo parametro è molto utile se hai definito una o più trasformazioni all’interno di più file di inclusione del set di dati di trasformazione </span> e desideri che trasformazioni specifiche vengano eseguite in punti specifici durante la trasformazione.<span class="wintitle"> </span></p> <p> L'ordine in cui si elencano le fasi qui determina l'ordine in cui le trasformazioni nei file <span class="wintitle"> Dataset di trasformazione Include </span> vengono eseguite durante la trasformazione. <span class="wintitle"> La preelaborazione  </span> e la  <span class="wintitle"> postelaborazione  </span> sono fasi integrate;  <span class="wintitle"> La preelaborazione  </span> è sempre la prima fase e la  <span class="wintitle"> postelaborazione  </span> è sempre l’ultima fase. Per impostazione predefinita, esiste una fase denominata <span class="wintitle"> Predefinito </span>. </p> <p> <b>Per aggiungere una nuova fase di elaborazione</b> </p> <p> 
      <ul id="ul_6AF2EF72CEE34FA88575C46FA333BDA1"> 
       <li id="li_80627E7A89CE4E57A4228C4F5496533F"> Nella finestra <span class="filepath"> Transformation.cfg </span> , fai clic con il pulsante destro del mouse su <span class="uicontrol"> Stages </span> e fai clic su <span class="uicontrol"> Aggiungi nuovo </span> &gt; <span class="uicontrol"> Stage </span>. </li> 
       <li id="li_321BEDB1E95F4AA4B282EED32A4CA196"> Immettere un nome per il nuovo passaggio. </li> 
      </ul> </p> <p> <b>Per eliminare una fase di elaborazione esistente</b> </p> <p> 
      <ul id="ul_2EFA5A40982A48919E9946BF1955110A"> 
       <li id="li_3B3829DA34FD4774B3F9F94074099794"> Fare clic con il pulsante destro del mouse sul numero corrispondente all'area di visualizzazione che si desidera eliminare e fare clic su <span class="uicontrol"> Rimuovi </span><i>&lt; <span class="uicontrol"> #stage_number </span></i>. </li> 
      </ul> </p> <p> <p>Nota:  Quando si specifica uno stage in un file di tipo <span class="wintitle"> Dataset di trasformazione Include </span>, il nome dell’area di visualizzazione deve corrispondere esattamente al nome immesso. Per ulteriori informazioni sui file di inclusione dei set di dati, consulta <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-abt-dataset-inc-files.md"> Dataset Include Files </a> (File inclusi nel set di dati). </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Ora di inizio </td> 
      <td colname="col2"> <p>Facoltativo. Filtrare i dati per includere voci di registro con marche temporali in o dopo questo momento. L'Adobe consiglia di utilizzare per il tempo uno dei seguenti formati: 
      <ul id="ul_6BC86CCB1FC447ACAC4045E08C8EF8F8"> 
       <li id="li_2151B3F7FAD54F38B6C33E25CDCACBBE"> 1 gennaio 2013 HH:MM:SS EDT </li> 
       <li id="li_CA1BB675C1244104915FB9ED96A3013D"> 1 gennaio 2013 OH:MM:SS GMT </li> 
      </ul> </p> <p> Ad esempio, specificando 29 luglio 2013 00:00:00 EDT come <span class="wintitle"> Ora di inizio </span> sono inclusi i dati a partire dal 29 luglio 2013 alle 12:00:00 EDT. </p> <p> È necessario specificare un fuso orario. Il fuso orario non viene impostato su GMT se non viene specificato. Per un elenco delle abbreviazioni del fuso orario supportate dal server di Data Workbench, consulta <a href="../../../home/c-dataset-const-proc/c-time-zone.md#concept-9b540ec3e770490d94e9d5a985765477"> Codici del fuso orario </a>. </p> <p> <p>Nota:  Se si specifica un valore per Start Time, viene impostato e applicato un parametro denominato Start Time durante la fase di trasformazione della costruzione del set di dati. Per informazioni sui parametri, consulta <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-def-param-dataset-inc-files/c-def-param-dataset-inc-files.md#concept-5ad06acc8dc44bf2a99643fafdd56b50"> Definizione dei parametri in Dataset Include Files (File inclusi nel set di dati) </a>. </p> </p> </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Trasformazioni </td> 
      <td colname="col2"> Facoltativo. L’Adobe consiglia di definire le trasformazioni per la fase di trasformazione della costruzione del set di dati in uno o più file <span class="wintitle"> di Dataset di trasformazione che includono </span>. Per informazioni, consulta <a href="../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-trans-dataset-inc-files.md#concept-c64aa78ed9ce40b8a0f4932c82ff5ace"> Dataset Include Files (File inclusi nel set di dati di trasformazione) </a>. </td> 
   </tr> 
   <tr> 
      <td colname="col1"> Fuso orario </td> 
      <td colname="col2"> <p>Fuso orario del profilo del set di dati. I fusi orari vengono utilizzati per le conversioni temporali e per la creazione di dimensioni temporali. Vedere <a href="../../../home/c-dataset-const-proc/c-trans-config-file/c-spec-trans-param/c-time-zones.md#concept-9cf16b1cb4874f7d85e1dd950fdb4956"> Fusi orari </a>. </p> <p> <p>Nota:  Quando è definito nel file <span class="filepath"> Log Processing.cfg </span> , il parametro Time Zone viene utilizzato solo per le conversioni temporali. </p> </p> </td> 
   </tr> 
   </tbody> 
   </table>

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL Transformation.cfg]nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > * **[!UICONTROL dataset profile name]** per rendere effettive le modifiche apportate localmente. La riconversione dei dati inizia dopo la sincronizzazione del profilo del set di dati.

   >[!NOTE]
   >
   >Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

   Per informazioni sulla rielaborazione o la trasformazione dei dati, vedere [Rielaborazione e ritrasformazione](../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
