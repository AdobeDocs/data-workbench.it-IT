---
description: Il file di configurazione Transform Mode.cfg consente di mettere in pausa l’elaborazione dei dati in un set di dati, specificare le origini offline o specificare la frequenza con cui il server di Data Workbench che esegue la funzionalità di trasformazione salva i file di stato.
title: Il file di Transform Mode.cfg
uuid: 6e875d02-341a-414c-90e5-aa7fa910ab81
exl-id: 4faca063-3ca9-4c7c-9f04-ba2dfb647a77
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 3%

---

# Il file di Transform Mode.cfg{#the-transform-mode-cfg-file}

{{eol}}

Il file di configurazione Transform Mode.cfg consente di mettere in pausa l’elaborazione dei dati in un set di dati, specificare le origini offline o specificare la frequenza con cui il server di Data Workbench che esegue la funzionalità di trasformazione salva i file di stato.

Apportare modifiche al [!DNL Transform Mode.cfg] il file , inclusa l’aggiunta o la rimozione di origini, non causa la rielaborazione dei dati.

**Per modificare il file Transform Mode.cfg per un profilo di set di dati**

1. Quando lavori nel profilo di cui desideri esportare i dati, apri la [!DNL Profile Manager] e fai clic su **[!UICONTROL Dataset]** per visualizzare il contenuto della directory.
1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL Transform Mode.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nel [!DNL User] colonna.
1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La [!DNL Transform Mode.cfg] viene visualizzata la finestra .
1. Modifica i parametri nel file di configurazione utilizzando la seguente tabella come guida:

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
     <li id="li_617C04FE9F1C4E998394F224CFEA21F3"> Fai clic con il pulsante destro del mouse <span class="uicontrol"> Origini offline</span> e fai clic su <span class="uicontrol"> Aggiungi nuovo</span> &gt; <span class="uicontrol"> Origine</span>. </li> 
    <li id="li_B263A294D1F14D62BBAA5DBF3B388C38"> Nel parametro per la nuova sorgente, immetti la maschera della sequenza di log. Per le origini di registro Sensor con nomi di file del formato <span class="filepath"> YYYMMDD-SENSORID.vsl</span>, la maschera è <i>SENSORID.SENSORID</i> fa distinzione tra maiuscole e minuscole. Per le origini dei file di log, la maschera è la stringa estratta dal <span class="wintitle"> Pattern di maschera</span> (vedi <a href="../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e"> File di registro</a>). </li> 
    </ul> <p> Aggiunta o rimozione di origini <span class="wintitle"> Origini offline</span> non causa la rielaborazione del set di dati. </p> <p> Come delle misurazioni del tempo sono mantenuti per l'elaborazione delle fonti online del profilo. Quando l'origine offline è nuovamente online, riprende l'elaborazione dei file di registro in ingresso per quella sorgente. </p> <p> <p>Nota: Ogni volta che un'origine torna online, devi rimuoverla da <span class="wintitle"> Origini offline</span>. In caso contrario, il server di Data Workbench tratta l’origine come un’origine online e la aggiorna a partire dal momento in cui l’origine invia i dati. Se l'origine torna offline di nuovo, le misurazioni dell'ora A si arrestano. </p> </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> In pausa </td> 
    <td colname="col2"> True o false. Se true, i nuovi dati non vengono elaborati nel set di dati. Il valore predefinito è false. </td> 
    </tr> 
    <tr> 
    <td colname="col1"> Intervallo di salvataggio (sec) </td> 
    <td colname="col2"> <p>La frequenza con cui il server di Data Workbench su cui è in esecuzione la funzionalità di trasformazione salva i relativi file di stato. Il valore predefinito è 3600. </p> <p> <p>Nota: Non modificare questo valore senza consultare un Adobe. </p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   Durante la modifica del [!DNL Transform Mode.cfg] all’interno di una finestra di Data Workbench, puoi utilizzare i tasti di scelta rapida per le funzioni di modifica di base, tra cui Taglia (Ctrl+x ), Copia (Ctrl+c) , Incolla (Ctrl+v ), Annulla (Ctrl+z ), Ripristina (Ctrl+Maiusc+Z ), seleziona una sezione (clic+trascina) e seleziona tutto (Ctrl+a ). Inoltre, è possibile utilizzare le scelte rapide per copiare e incollare il testo da un file di configurazione ( [!DNL .cfg]) a un altro.

1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.
1. Per rendere effettive le modifiche apportate localmente, nella [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per Data Workbench [!DNL Transform Mode.cfg] in [!DNL User] , quindi fai clic su **[!UICONTROL Save to]** > **[!UICONTROL profile name]**, dove nome profilo è il nome del profilo per il quale stai esportando i dati. La rielaborazione dei dati inizia dopo la sincronizzazione del profilo.

   Per informazioni sulla rielaborazione dei dati per l’esportazione, consulta [Rielaborazione e ritrasformazione](../../../../home/c-dataset-const-proc/c-reproc-retrans/c-unst-reproc-retrans.md).
