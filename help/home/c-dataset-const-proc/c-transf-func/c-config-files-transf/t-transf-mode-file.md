---
description: Il file di configurazione Transform Mode.cfg consente di mettere in pausa l'elaborazione dei dati in un dataset, specificare le origini offline o specificare la frequenza con cui il server workbench dati che esegue la funzionalità di trasformazione salva i file di stato.
solution: Analytics
title: Il file Transform Mode.cfg
topic: Data workbench
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Il file Transform Mode.cfg{#the-transform-mode-cfg-file}

Il file di configurazione Transform Mode.cfg consente di mettere in pausa l&#39;elaborazione dei dati in un dataset, specificare le origini offline o specificare la frequenza con cui il server workbench dati che esegue la funzionalità di trasformazione salva i file di stato.

Le modifiche apportate al [!DNL Transform Mode.cfg] file, inclusa l&#39;aggiunta o la rimozione di origini, non causano la rielaborazione dei dati.

**Per modificare il file Transform Mode.cfg per un profilo dataset**

1. Mentre lavorate nel profilo di cui desiderate esportare i dati, aprite il profilo [!DNL Profile Manager] e fate clic **[!UICONTROL Dataset]** per visualizzare il contenuto della directory.
1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Transform Mode.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene [!DNL Transform Mode.cfg] visualizzata la finestra.
1. Modificate i parametri nel file di configurazione utilizzando la seguente tabella come guida:

   <table id="table_9FC00BD54FD8439DA17AEF61AC2ACD50"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> Parametro </th> 
    <th colname="col2" class="entry"> Descrizione </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> Origini offline </td> 
    <td colname="col2"> <p>Maschera dell'origine del registro offline. </p> <p> Per specificare un'origine offline: </p> 
    <ul id="ul_B93F945A697C4882ADE420438712B0B0"> 
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Fai clic con il pulsante destro del mouse su <span class="uicontrol"> Origini</span> offline e fai clic su <span class="uicontrol"> Aggiungi nuovo</span> &gt; <span class="uicontrol"> Origine</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> Nel parametro per la nuova origine, immettete la maschera della sequenza di registro. Per le sorgenti di registro Sensor con nomi di file nel formato <span class="filepath"> YYYYMMDD-SENSORID.vsl</span>, la maschera è <i>SENSORID.SENSORID</i> con distinzione tra maiuscole e minuscole. Per le origini di registro dei file, la maschera è la stringa estratta dal pattern <span class="wintitle"> di</span> maschera (vedere <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> File</a>di registro). </li> 
    </ul> <p> L'aggiunta o la rimozione di origini da origini <span class="wintitle"></span> offline non causa la rielaborazione del set di dati. </p> <p> Come misura del tempo vengono mantenute per l'elaborazione delle fonti online del profilo. Quando l'origine offline è nuovamente online, l'elaborazione dei file di registro in entrata per tale origine riprende. </p> <p> <p>Nota: Ogni volta che una fonte torna online, devi rimuoverla da <span class="wintitle"> Offline Sources</span>. In caso contrario, il server workbench dati tratta l'origine come un'origine online e aggiorna il periodo di tempo impostato per l'invio dei dati. Se l'origine torna offline, le misure Come ora si fermano. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> In pausa </td> 
    <td colname="col2"> True o false. Se true, i nuovi dati non vengono elaborati nel dataset. Il valore predefinito è false. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Intervallo di salvataggio (sec) </td> 
    <td colname="col2"> <p>Frequenza con cui il server workbench dati su cui è in esecuzione la funzionalità di trasformazione salva i file di stato. Il valore predefinito è 3600. </p> <p> <p>Nota:  Non devi modificare questo valore senza consultare Adobe. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   Quando si modifica il [!DNL Transform Mode.cfg] file all&#39;interno di una finestra del workbench dati, è possibile utilizzare i tasti di scelta rapida per le funzioni di modifica di base, quali Taglia (Ctrl+x ), Copia (Ctrl+c), Incolla (Ctrl+v), Annulla (Ctrl+z ), Ripristina (Ctrl+Maiusc+Z ), Seleziona la sezione (Clic+trascinamento) e seleziona tutto (Ctrl+a ). Inoltre, potete utilizzare i collegamenti per copiare e incollare il testo da un file di configurazione ( [!DNL .cfg]) a un altro.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.
1. Per rendere attive le modifiche apportate localmente, nella [!DNL Profile Manager]colonna fare clic con il pulsante destro del mouse sul segno di spunta per il workbench dati [!DNL Transform Mode.cfg] nella [!DNL User] colonna, quindi scegliere **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, dove il nome del profilo è il nome del profilo per il quale si esportano i dati. La rielaborazione dei dati inizia dopo la sincronizzazione del profilo.

   Per informazioni sulla rielaborazione dei dati per l&#39;esportazione, vedere [Rielaborazione e trasformazione](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
