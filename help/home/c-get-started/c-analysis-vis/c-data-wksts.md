---
description: È possibile immettere testo o espressioni in qualsiasi cella di un foglio di lavoro.
title: Operazioni con i dati nei fogli di lavoro
uuid: c2331fa5-aa07-4622-8f44-5124c22dffcb
exl-id: 40d9211b-8f5c-4051-8f93-638ffacf45bd
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 2%

---

# Operazioni con i dati nei fogli di lavoro{#work-with-data-in-worksheets}

È possibile immettere testo o espressioni in qualsiasi cella di un foglio di lavoro.

Tutte le espressioni in un foglio di lavoro sono precedute da un segno di uguale (=) a meno che non si utilizzi [!DNL eval( )], che tratta il testo nella cella a cui si fa riferimento come espressione.

Per un elenco completo delle regole di sintassi della metrica, della dimensione e del filtro, consulta [Sintassi della lingua della query](../../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f).

**Per immettere dati in un foglio di lavoro**

1. Fai due volte clic su una cella del foglio di calcolo per accedere alla modalità di modifica. La cella selezionata viene evidenziata.
1. Digita o incolla i dati desiderati nella cella.

**Per copiare e incollare da una cella all’altra**

1. Fare clic con il pulsante destro del mouse sulla cella contenente i dati che si desidera copiare e fare clic su **[!UICONTROL Copy]**.
1. Fare clic con il pulsante destro del mouse sulla cella in cui si desidera incollare i dati copiati e fare clic su **[!UICONTROL Paste]**.

Data Workbench aggiorna automaticamente i riferimenti nella nuova cella in modo che facciano riferimento alle colonne e alle righe appropriate.

**Per copiare e incollare da un gruppo di celle a un altro**

1. Selezionare le celle contenenti i dati da copiare.
1. Fai clic con il pulsante destro del mouse sulle celle contenenti i dati da copiare e fai clic su **[!UICONTROL Copy]**.
1. Fare clic con il pulsante destro del mouse sulla prima cella in cui si desidera iniziare a incollare i dati copiati e fare clic su **[!UICONTROL Paste]**. I dati vengono incollati nella prima cella e sotto di essa.

Data Workbench aggiorna automaticamente i riferimenti nella nuova cella in modo che facciano riferimento alle colonne e alle righe appropriate.

**Inserimento di una colonna**

* Fai clic con il pulsante destro del mouse su una colonna e fai clic su **[!UICONTROL Insert Column]**. La nuova colonna viene inserita a sinistra della colonna selezionata.

**Eliminazione di una colonna**

* Fare clic con il pulsante destro del mouse sulla colonna da eliminare e fare clic su **[!UICONTROL Delete Column]**. La colonna viene rimossa.

**Inserimento di una riga**

* Fai clic con il pulsante destro del mouse su una riga e fai clic su **[!UICONTROL Insert Row]**. La nuova riga viene inserita sopra la riga selezionata.

**Eliminazione di una riga**

* Fare clic con il pulsante destro del mouse sulla riga da eliminare e fare clic su **[!UICONTROL Delete Row]**. La riga viene rimossa.

**Ridimensionamento di una colonna**

1. Nella riga di intestazione della colonna, posizionare il cursore sulla linea di divisione a destra della colonna di cui si desidera modificare la dimensione.
1. Fai clic e trascina a destra per aumentare la larghezza della colonna o a sinistra per ridurre la larghezza della colonna.

**Formattazione di una cella**

1. Fai clic con il pulsante destro del mouse sulla cella e fai clic su **[!UICONTROL Format]**.

   ![](assets/mnu_Worksheet_Format.png)

1. Fai clic sul formato desiderato nel menu delle opzioni disponibili:

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
   <td colname="col2"> <p>Applica ai dati il formato numerico selezionato, ad esempio ora, data, percentuale o decimale. </p> <p>Fare clic su <span class="uicontrol"> Default</span> per rimuovere la formattazione selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Giustifica </p> </td> 
   <td colname="col2"> <p>Giustifica i dati all’interno della cella a sinistra, al centro o a destra. La giustificazione predefinita viene lasciata. </p> <p>Fare clic su <span class="uicontrol"> Default</span> per rimuovere la formattazione selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Colore </p> </td> 
   <td colname="col2"> <p>Applica il colore del font selezionato ai dati all’interno della cella. Il colore predefinito del font è il bianco. </p> <p>Fare clic su <span class="uicontrol"> Default</span> per rimuovere la formattazione selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indicatore </p> </td> 
   <td colname="col2"> <p>Crea un indicatore di metrica utilizzando questa cella. Per ulteriori informazioni, consulta <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-metric-ind.md#concept-f0e911b23b2c4e8da3e1ea7b9ae04183"> Creazione di indicatori di metrica</a>. </p> <p>Fare clic su <span class="uicontrol"> Default</span> per rimuovere la formattazione selezionata. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cella di ingresso </p> </td> 
   <td colname="col2"> <p>Rende la cella selezionata una cella di input. Per ulteriori informazioni, vedere <a href="../../../home/c-get-started/c-analysis-vis/c-wksts/c-input-cells.md#concept-08cd2c05a28a43dd9f7698b37e23e590"> Creazione di celle di input</a>. </p> <p>Fare clic su <span class="uicontrol"> Default</span> per rimuovere la formattazione selezionata. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Scelte rapide da tastiera {#section-05301f4d2c60418e86902635a7aeee20}

Nei fogli di lavoro è possibile utilizzare molte delle scelte rapide da tastiera di base per la modifica che è possibile utilizzare in qualsiasi editor di testo, ad esempio Blocco note o Microsoft Word.

Nella tabella seguente sono elencate le scelte rapide da tastiera di base che è possibile utilizzare quando si immettono dati in un foglio di lavoro.

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
   <td colname="col2"> <p>Passa da cella a cella nel foglio di lavoro utilizzando i tasti freccia su, giù, sinistra e destra. </p> </td> 
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
   <td colname="col2"> <p>Annulla la modifica della cella selezionata. Il cursore viene rimosso dalla cella e il contenuto della cella viene ripristinato a quello esistente prima di iniziare la modifica. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elimina </p> </td> 
   <td colname="col2"> <p>Elimina il contenuto delle celle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+A </p> </td> 
   <td colname="col2"> <p>Selezionare il contenuto della cella. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+c </p> </td> 
   <td colname="col2"> <p>Copiare il contenuto delle celle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+X </p> <p>Maiusc+Canc </p> </td> 
   <td colname="col2"> <p>Copiare e rimuovere il contenuto delle celle. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+v </p> <p>Maiusc+Inserisci </p> </td> 
   <td colname="col2"> <p>Incolla il contenuto delle celle copiate nelle celle selezionate. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+Z </p> </td> 
   <td colname="col2"> <p>Annulla la digitazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ctrl+Maiusc+Z </p> </td> 
   <td colname="col2"> <p>Ripeti la digitazione. </p> </td> 
  </tr> 
 </tbody> 
</table>
