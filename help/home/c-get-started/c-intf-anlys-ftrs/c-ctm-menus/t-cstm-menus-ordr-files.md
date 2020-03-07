---
description: Potete personalizzare l’aspetto di qualsiasi menu modificando il file order.txt associato a tale menu.
solution: Analytics
title: Personalizzare un menu utilizzando i file order.txt
topic: Data workbench
uuid: 4346114a-05d0-4d15-9633-09c9d869cdd6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Personalizzare un menu utilizzando i file order.txt{#customize-a-menu-using-order-txt-files}

Potete personalizzare l’aspetto di qualsiasi menu modificando il file order.txt associato a tale menu.

I passaggi descritti in questa sezione sono applicabili a tutti i tipi di menu.

**Per modificare il file order.txt e personalizzare un menu**

1. Nella [!DNL Profile Manager]colonna del nome *del* profilo fare clic con il pulsante destro del mouse sul segno di spunta del [!DNL order.txt] file e fare clic **[!UICONTROL Make Local]**.
1. Fare clic con il pulsante destro del mouse sul [!DNL order.txt] file nella [!DNL User] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Viene [!DNL order.txt] visualizzato il file.

   ![Informazioni sul passaggio](assets/cfg_ordertxt.png)

1. (Facoltativo) Se necessario, aggiungete o modificate l’impostazione [Inclusive] o [Exclusive] nella parte superiore del file. Questa impostazione controlla se gli elementi non elencati nel [!DNL order.txt] file ma presenti nel [!DNL Profile Manager] file sono elencati nel menu. Le opzioni includono:

   * **[Inclusivo]:**Questa è l&#39;impostazione predefinita. Questa impostazione consente di visualizzare in ordine alfabetico le voci di menu non specificate nel[!DNL order.txt]file. Ad esempio, se il[!DNL Profile Manager]contenuto conteneva un elemento Profilo oltre a quelli elencati in[!DNL order.txt]precedenza, il profilo veniva visualizzato sotto Dati.

   * **[Esclusivo]:**Questa impostazione fa sì che le voci di menu non specificate nel[!DNL order.txt]file vengano escluse dal menu. Ad esempio, se il[!DNL Profile Manager]contenuto conteneva un elemento Profilo oltre a quelli elencati in[!DNL order.txt]precedenza, il profilo non veniva visualizzato in nessun punto del menu.

   * **blank:** Se [Inclusive] o [Exclusive] non vengono visualizzate nella parte superiore del file, Workbench dati visualizza le voci di menu come se l&#39;impostazione fosse [Inclusive].

1. Completa uno o più dei seguenti passaggi:

   <table id="table_C5D5313DF5E4470499B0B285BA2690F0"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Per eseguire questa operazione... </th> 
    <th colname="col2" class="entry"> Effettuate le seguenti operazioni... </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <p>Riordinare le voci di menu </p> </td> 
    <td colname="col2"> <p>Digitare i nomi degli articoli nell'ordine in cui si desidera che vengano visualizzati in Workbench dati. </p> <p>Ad esempio, se il nome di ogni voce di menu corrisponde al nome di file o cartella corrispondente, quanto segue determinerà<b> la visualizzazione per prima cosa di Aggiungi tabella</b> , quindi di <b>Aggiungi visualizzazione</b>, <b>Aggiungi legenda</b>e <b>Aggiungi nota</b> per ultima. </p> <p><b>Aggiungi tabella </b> </p> <p><b>Aggiungi visualizzazione </b> </p> <p><b>Aggiungi legenda </b> </p> <p><b>Aggiungi nota </b> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Rinominare una voce di menu </p> </td> 
    <td colname="col2"> <p>Rinominare il file o la cartella corrispondente in <span class="wintitle"> Profile Manager</span>, quindi modificare il nome dell’elemento nel file <span class="filepath"> order.txt</span> . </p> <p>Ad esempio, per rinominare Aggiungi annotazione in Nuova annotazione, rinominare la cartella Aggiungi annotazione in Gestore <span class="wintitle"> profilo in Nuova annotazione, quindi modificare il nome dell’elemento Aggiungi annotazione nel file</span> order.txt <span class="filepath"></span> in Nuova annotazione. </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Nascondere una voce di menu </p> </td> 
    <td colname="col2"> <p>Per nascondere la voce di menu ma non eliminare la voce stessa, digitare un segno meno (-) all'inizio del nome. </p> <p>Ad esempio, i seguenti risultati in <span class="wintitle"> Aggiungi annotazione</span> non vengono visualizzati nel menu. </p> <p>Aggiungi legenda </p> <p>-Aggiungi annotazione </p> <p>Per visualizzare di nuovo la voce di menu nascosta, rimuovete semplicemente il segno meno (-) o utilizzate il parametro Unhide All nel file <span class="filepath"> Insight.cfg</span> , consultate <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> Insight Configuration Parameters</a>(Parametridi configurazione di Insight). </p> <p>È inoltre possibile nascondere le voci di menu utilizzando i metodi seguenti: 
    <ul id="ul_CC9A82AFCE784CA49CC912C9256BAC1A"> 
    <li id="li_28C28CA0DE4B4A8F9C2C2C2B3BDD0557"> <p>Il parametro Show in un file <span class="filepath"> .filter</span>, <span class="filepath"> .Metric</span>o <span class="filepath"> .dim</span> nasconde filtri, metriche e dimensioni derivate e dimensioni estese dai rispettivi menu. Quando si utilizza questa opzione, la voce non è elencata nel menu, ma è ancora nel profilo e può essere utilizzata. </p> <p>Per utilizzare questo parametro per nascondere filtri e metriche e dimensioni derivate, aggiungi la seguente riga alla fine del file <span class="filepath"> .Metric</span>, <span class="filepath"> .dim</span>o <span class="filepath"> .filter</span> : </p> <p><span class="filepath"> show = bool: false</span> </p> <p>Per utilizzare questo parametro per nascondere le dimensioni estese, consultare il Capitolo 10 della Guida alla configurazione del set di <i>dati</i> per le istruzioni. </p> <p>Potete scoprire temporaneamente gli elementi nascosti utilizzando questo metodo impostando il parametro Unhide All (Mostra tutto) nel file <span class="filepath"> Insight.cfg</span> . Per ulteriori informazioni su questo parametro, consultate Parametri <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> di configurazione di</a>Insight. </p> </li> 
    <li id="li_2CB65D594DD04C59A8D27A17DBF278FA">Il parametro Hidden nel file <span class="filepath"> Transformation.cfg</span> o qualsiasi set di dati include file nasconde le dimensioni estese dal menu della dimensione. Quando si utilizza questa opzione, la voce non è elencata nel menu, ma è ancora nel profilo e può essere utilizzata. <p> <p>Nota:  Quando nascondi dimensioni estese utilizzando questo metodo, devi trasformare nuovamente il set di dati per nascondere le dimensioni. </p> </p> <p>Potete scoprire temporaneamente gli elementi nascosti utilizzando questo metodo impostando il parametro Unhide All (Mostra tutto) nel file <span class="filepath"> Insight.cfg</span> . Per ulteriori informazioni su questo parametro, consultate Parametri <a href="../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b"> di configurazione di</a>Insight. </p> </li> 
    <li id="li_6E161953FEA44EC18237D88D7173DC60"> <p>I file a byte zero nascondono qualsiasi tipo di elemento in qualsiasi menu. Quando si utilizza questa opzione, un file vuoto (a byte zero) nasconde la presenza di un file con lo stesso nome che contiene i dati. Workbench dati tratta i file a zero come se non esistessero. Per ulteriori informazioni, vedere <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Nascondere i file utilizzando file</a>vuoti (a byte zero). </p> </li> 
    </ul> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Eliminare una voce di menu </p> </td> 
    <td colname="col2"> <p>Se questo file è impostato per utilizzare l'opzione [Esclusivo], è sufficiente eliminare la voce di menu da questo file. L'elemento stesso è ancora nel profilo, ma non è elencato nel menu. </p> <p>Se questo file è impostato per utilizzare l'opzione [Inclusivo], è necessario rimuovere il nome della voce di menu da questo file ed eliminare o zero byte il file corrispondente per rimuovere la voce dal menu. </p> <p>Per informazioni sull’eliminazione di file, consultate <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-del-files-wkg-prof.md#task-1e29c25e6c824cc9b51cb651e835856b"> Eliminazione di file dal profilo</a>di lavoro. Per informazioni sui file a zero byte, vedere <a href="../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491"> Nascondere i file utilizzando file</a>vuoti (a zero byte). </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Aggiungere un’intestazione di gruppo </p> </td> 
    <td colname="col2"> <p>Digitare tre trattini prima e dopo il testo del titolo che si desidera visualizzare. </p> <p>Ad esempio, quanto segue restituisce l’intestazione di un gruppo Gestisci per un set di voci di menu correlate. </p> <p>---Gestire i--- </p> <p>Profilo </p> <p>Set di dati </p> <p> <img id="image_DB5BB8A33553499A9FC6B53C544CD4CC" src="assets/cfg_ordertxt_example.png"> </img> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <p>Aggiunta di una riga a sezioni separate di un menu </p> </td> 
    <td colname="col2"> <p>Digitare tre trattini in cui si desidera visualizzare una linea. </p> <p>Ad esempio, la seguente riga separa Aggiungi annotazione e Aggiungi personalizzato. </p> <p>Aggiungi annotazione </p> <p>--- </p> <p>Aggiungi personalizzato </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. Salvate e chiudete il file.
1. (Facoltativo) Per rendere disponibili le modifiche a tutti gli utenti del profilo di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta bianco del [!DNL order.txt] file nella [!DNL User] colonna e scegliere **[!UICONTROL Save to]** > * **[!UICONTROL working profile name]**.
