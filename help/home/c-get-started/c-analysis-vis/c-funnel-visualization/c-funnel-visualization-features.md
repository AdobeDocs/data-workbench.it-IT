---
description: La visualizzazione Funnel include funzioni per la creazione di un funnel con dimensioni multiple, numeri di visitatori non elaborati, percentuale di visitatori in ogni passaggio e ambiti separati.
solution: Analytics
title: Funzioni funnel
topic: Data workbench
uuid: 7d2f5ff9-95d3-41f5-931c-689f140714c2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Funzioni funnel{#funnel-features}

La visualizzazione Funnel include funzioni per la creazione di un funnel con dimensioni multiple, numeri di visitatori non elaborati, percentuale di visitatori in ogni passaggio e ambiti separati.

Queste sono le caratteristiche di base della visualizzazione funnel.

![](assets/funnel_visualization_capture.png)

<table id="table_49A08740CEE74D64B6F9C37CD91F1AE5"> 
 <tbody> 
  <tr> 
   <td colname="col01"> <img id="image_0C1701833FE049708CE38ADEB5EC7EEF" src="assets/funnel_visualization_capture_1.png" /> </td> 
   <td colname="col1"> Primo elemento </td> 
   <td colname="col2"> Primo passaggio funnel nel processo. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_EF8AF94D833B4A249959B76F8FAF2318" src="assets/funnel_visualization_capture_2.png" /> </td> 
   <td colname="col1"> Terzo elemento </td> 
   <td colname="col2">Terzo passaggio funnel nel processo. <p><p>Nota:  Gli elementi selezionati non devono provenire dalla stessa dimensione. </p></p></td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_F3C5130B52234FAC9DEB50279F94FF90" src="assets/funnel_visualization_capture_3.png" /> </td> 
   <td colname="col1"> Percentuale di immersione </td> 
   <td colname="col2"> Percentuale di completamento del percorso definito visualizzato in tre ambiti. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_3F030396CEB14528980F5B965113BD36" src="assets/funnel_visualization_capture_4.png" /> </td> 
   <td colname="col1"> Browser di fallout </td> 
   <td colname="col2">Freccia di abbandono. Fai clic con il pulsante destro del mouse e seleziona <span class="uicontrol"> Aggiungi browser</span> percorso per vedere il percorso seguito dagli altri visitatori. </td> 
  </tr> 
  <tr> 
   <td colname="col01"> <img id="image_0DA7567BDBDF4BEF9CA840D2F88A414E" src="assets/funnel_visualization_capture_5.png" /> </td> 
   <td colname="col1"> Abbandono percentuale </td> 
   <td colname="col2">Percentuali che descrivono tre ambiti di abbandono per gli utenti che non hanno completato il percorso. <p>Le percentuali sono presentate in tre ambiti: </p><p><img id="image_B85C46DDF12C41D5BF213D5F9DC04967" placement="break" src="assets/funnel_path_browser_5.png" /></p><p><img id="image_BC37007D7B4B425C8F87905CE68F0114" src="assets/funnel_path_browser_6.png" /> Percentuale di abbandono dal passaggio precedente a questo passaggio. </p><p><img id="image_B10866B083424360AFF1B19E836A94CF" src="assets/funnel_path_browser_7.png" /> Percentuale di abbandono dal primo passaggio nell'imbuto. </p><p><img id="image_19B9AE916B584E18A82F5D5E10674414" src="assets/funnel_path_browser_8.png" /> Percentuale di abbandono in base al numero totale di visitatori. </p></td> 
  </tr> 
 </tbody> 
</table>

## Passaggi funnel {#section-96a6732558dd4740b73541844f06d3ef}

I dischi di un imbuto rappresentano i passi nella navigazione, i coni rappresentano il passaggio da un passaggio all&#39;altro e le frecce rappresentano l&#39;abbandono. Facendo clic su un cono, verranno selezionati gli utenti che sono caduti in quel punto e inclusi nel filtro dell&#39;area di lavoro corrente. Facendo clic su una freccia si selezioneranno i visitatori che sono caduti.

>[!NOTE]
>
>La visualizzazione Funnel ha un limite di otto fasi che è possibile applicare.

## Funzioni e funzioni aggiuntive {#section-22a3582db8114ca8bce77f50bbbf296a}

* **Regolare la clip e il livello dell&#39;imbuto**. Selezionare l&#39;opzione Funnel dal menu Visualizzazione. Dopo aver creato l&#39;imbuto, è possibile fare clic con il pulsante destro del mouse sul titolo per regolare la clip e livellare a qualsiasi metrica numerabile nel sistema.

   ![](assets/funnel_path_browser_9.png)

* **Trascinate altri elementi**. Aggiungete altri elementi all&#39;imbuto trascinandoli dalla tabella Dimensione all&#39;imbuto utilizzando i tasti `<Ctrl>` + `<Alt>` . È possibile trascinare più passaggi contemporaneamente dalla tabella Dimensione selezionando più elementi (utilizzando `<Ctrl>` + clic) e quindi trascinandoli nella visualizzazione Funnel utilizzando i `<Ctrl>` tasti `<Alt>` +.
* **Eliminare un passaggio**: Per eliminare gli elementi, fai clic con il pulsante destro del mouse sul passaggio nella visualizzazione e fai clic su **Sì**.

   ![](assets/funnel_path_browser_4.png)

* **Ridisporre i passi trascinati nell’imbuto**. È sufficiente fare clic sul passaggio per selezionarlo e trascinarlo in un&#39;altra posizione per ridisporre i passi.
* **Aprite un browser** di percorsi. Per ulteriori dettagli sulle posizioni dei clienti rispetto al processo, consulta la funzione [Aggiungi browser](../../../../home/c-get-started/c-analysis-vis/c-funnel-visualization/c-path-browser-funnel.md#concept-b0cedf7a28ae422696ded1258c9a4119) percorso.

* **Aggiungi altri passaggi**. Puoi aggiungere fino a otto passaggi a ogni visualizzazione funnel.
* **Modificare la metrica**. La metrica può essere modificata in modo che i passaggi contino le visite o qualche altra metrica in ogni fase. Le opzioni disponibili variano in base al dataset.
* **Visualizzate in visualizzazione** tabulare. Fare clic con il pulsante destro del mouse sul titolo per visualizzare il menu Visualizzazione imbuto e scegliere **[!UICONTROL Show Tabular View]**. Una volta visualizzata la visualizzazione tabulare, potete scegliere **[!UICONTROL Show Graph View]** di tornare alla rappresentazione grafica dell&#39;imbuto. Per aprire la vista Tabulare, fare clic con il pulsante destro del mouse sul titolo e selezionare Mostra vista tabulare dal menu.

* **Confronta le sequenze**. Un modo efficace per confrontare due sequenze simili consiste nel visualizzare le due visualizzazioni affiancate. È inoltre possibile visualizzare sia la vista tabulare che la vista grafico affiancate utilizzando la funzione Duplica. Per aprire, fare clic con il pulsante destro del mouse sul titolo e selezionare Duplica dal menu.
