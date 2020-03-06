---
description: È possibile inserire testo o espressioni in qualsiasi cella di un foglio di lavoro.
solution: Analytics
title: Operazioni con i dati nei fogli di lavoro
topic: Data workbench
uuid: c2331fa5-aa07-4622-8f44-5124c22dffcb
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Operazioni con i dati nei fogli di lavoro{#work-with-data-in-worksheets}

È possibile inserire testo o espressioni in qualsiasi cella di un foglio di lavoro.

Tutte le espressioni di un foglio di lavoro sono precedute da un segno di uguale (=) a meno che non venga utilizzato [!DNL eval( )], che considera il testo nella cella a cui si fa riferimento come espressione.

Per un elenco completo delle regole di metrica, dimensione e sintassi del filtro, consulta Sintassi [del linguaggio di](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f)query.

**Digitazione di dati in un foglio di lavoro**

1. Fate clic due volte su una cella del foglio di calcolo per passare alla modalità di modifica. La cella selezionata viene evidenziata.
1. Digitare o incollare i dati desiderati nella cella.

**Per copiare e incollare da una cella all&#39;altra**

1. Fare clic con il pulsante destro del mouse sulla cella contenente i dati da copiare e quindi fare clic **[!UICONTROL Copy]**.
1. Fare clic con il pulsante destro del mouse sulla cella in cui si desidera incollare i dati copiati e fare clic **[!UICONTROL Paste]**.

Workbench dati aggiorna automaticamente i riferimenti nella nuova cella per fare riferimento alle colonne e alle righe appropriate.

**Per copiare e incollare da un gruppo di celle a un altro**

1. Selezionare le celle contenenti i dati da copiare.
1. Fare clic con il pulsante destro del mouse sulle celle contenenti i dati da copiare e quindi fare clic **[!UICONTROL Copy]**.
1. Fare clic con il pulsante destro del mouse sulla prima cella in cui si desidera iniziare a incollare i dati copiati e fare clic **[!UICONTROL Paste]**. I dati vengono incollati nella prima cella e sotto di essa.

Workbench dati aggiorna automaticamente i riferimenti nella nuova cella per fare riferimento alle colonne e alle righe appropriate.

**Inserimento di una colonna**

* Fate clic con il pulsante destro del mouse su una colonna e fate clic **[!UICONTROL Insert Column]**. La nuova colonna viene inserita a sinistra della colonna selezionata.

**Per eliminare una colonna**

* Fare clic con il pulsante destro del mouse sulla colonna che si desidera eliminare e quindi scegliere **[!UICONTROL Delete Column]**. La colonna viene rimossa.

**Inserimento di una riga**

* Fare clic con il pulsante destro del mouse su una riga e scegliere **[!UICONTROL Insert Row]**. La nuova riga viene inserita sopra la riga selezionata.

**Per eliminare una riga**

* Fare clic con il pulsante destro del mouse sulla riga che si desidera eliminare e fare clic **[!UICONTROL Delete Row]**. La riga viene rimossa.

**Ridimensionamento di una colonna**

1. Nella riga di intestazione della colonna, posizionare il cursore sulla linea di divisione a destra della colonna di cui si desidera modificare la dimensione.
1. Fate clic e trascinate a destra per aumentare la larghezza della colonna, oppure a sinistra per ridurre la larghezza della colonna.

**Formattazione di una cella**

1. Fare clic con il pulsante destro del mouse sulla cella e scegliere **[!UICONTROL Format]**.

   ![](assets/mnu_Worksheet_Format.png)

1. Fate clic sul formato desiderato nel menu delle opzioni disponibili:

<table id="table_5788E01E52CC44E7927A0D23760D9EDD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opzione menu </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Numero </p> </td> 
   <td colname="col2"> <p>Applica ai dati il formato numerico selezionato, ad esempio ora, data, percentuale o decimale. </p> <p>Fare clic su <span class="uicontrol"> Predefinito</span> per rimuovere la formattazione selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Giustifica </p> </td> 
   <td colname="col2"> <p>Giustifica i dati all'interno della cella a sinistra, al centro o a destra. La giustificazione predefinita è left. </p> <p>Fare clic su <span class="uicontrol"> Predefinito</span> per rimuovere la formattazione selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Colore </p> </td> 
   <td colname="col2"> <p>Applica il colore del font selezionato ai dati all'interno della cella. Il colore predefinito del font è il bianco. </p> <p>Fare clic su <span class="uicontrol"> Predefinito</span> per rimuovere la formattazione selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indicatore </p> </td> 
   <td colname="col2"> <p>Crea un indicatore di metrica utilizzando questa cella. Per ulteriori informazioni, consultate <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#concept-f0e911b23b2c4e8da3e1ea7b9ae04183"> Creazione di indicatori</a>di metrica. </p> <p>Fare clic su <span class="uicontrol"> Predefinito</span> per rimuovere la formattazione selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cella di input </p> </td> 
   <td colname="col2"> <p>Trasforma la cella selezionata in una cella di input. Per ulteriori informazioni, vedere <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-input-cells.md#concept-08cd2c05a28a43dd9f7698b37e23e590"> Creazione di celle</a>di input. </p> <p>Fare clic su <span class="uicontrol"> Predefinito</span> per rimuovere la formattazione selezionata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Scelte rapide da tastiera {#section-05301f4d2c60418e86902635a7aeee20}

Nei fogli di lavoro è possibile utilizzare molte delle scelte rapide da tastiera di base per la modifica, utilizzabili in qualsiasi editor di testo, ad esempio Blocco note o Microsoft Word.

Nella tabella seguente sono elencate le scelte rapide da tastiera di base che è possibile utilizzare per immettere dati in un foglio di lavoro.

<table id="table_8E6F73F253B3451CA1DE45EE4F4E69EF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tasti di scelta rapida </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tasti freccia </p> </td> 
   <td colname="col2"> <p>Spostarsi da una cella all'altra del foglio di lavoro utilizzando i tasti freccia su, giù, destra e sinistra. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>F2 </p> </td> 
   <td colname="col2"> <p>Modificare la cella posizionando il cursore nella cella selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Invio </p> </td> 
   <td colname="col2"> <p>Completa la modifica della cella selezionata. Il cursore viene rimosso dalla cella e il contenuto della cella riflette la modifica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esc </p> </td> 
   <td colname="col2"> <p>Annullare la modifica della cella selezionata. Il cursore viene rimosso dalla cella e il contenuto della cella viene ripristinato a quello esistente prima di iniziare la modifica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elimina </p> </td> 
   <td colname="col2"> <p>Eliminare il contenuto delle celle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+A </p> </td> 
   <td colname="col2"> <p>Selezionare il contenuto della cella. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+C </p> </td> 
   <td colname="col2"> <p>Copiare il contenuto delle celle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+X </p> <p>Maiusc+Canc </p> </td> 
   <td colname="col2"> <p>Copiare e rimuovere il contenuto delle celle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+V </p> <p>Maiusc+Inserisci </p> </td> 
   <td colname="col2"> <p>Incolla nelle celle selezionate il contenuto delle celle copiate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+Z </p> </td> 
   <td colname="col2"> <p>Annulla digitazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+Maiusc+Z </p> </td> 
   <td colname="col2"> <p>Ripristina digitazione. </p> </td> 
  </tr> 
 </tbody> 
</table>

