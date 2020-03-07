---
description: Il menu Albero decisionale include funzioni che consentono di impostare casi d’uso positivi, filtri, opzioni di distribuzione foglia, matrice di confusione e altre opzioni avanzate.
title: Opzioni albero decisionale
uuid: 6439c6d4-60ac-4324-b870-b452a63b7ba1
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Opzioni albero decisionale{#decision-tree-options}

Il menu Albero decisionale include funzioni che consentono di impostare casi d’uso positivi, filtri, opzioni di distribuzione foglia, matrice di confusione e altre opzioni avanzate.

<table id="table_0CBCCB0856E2469EBE8846B413CAB114"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pulsanti della barra degli strumenti </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Go </td> 
   <td colname="col2"> Fai clic su per eseguire l'algoritmo della struttura decisionale e visualizzare la visualizzazione. Questa funzione è disattivata fino a quando non sono disponibili degli ingressi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reset </td> 
   <td colname="col2"> Cancella gli input e il modello della struttura decisionale e ripristina il processo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Salva </td> 
   <td colname="col2"><b>Salvare la struttura</b>decisionale. È possibile salvare la struttura decisionale in diversi formati: 
    <ul id="ul_F7C7836C06D64912893113E8EEA05704"> 
     <li id="li_D2D8451A679243F1BC67C3B80CA5F83F">Predictive Markup Language (<b>PMML</b>), un formato di file basato su XML utilizzato dalle applicazioni per descrivere e scambiare modelli di struttura decisionale. </li> 
     <li id="li_88C4B3E050CA4EFC9B7FA8BD446A9C55"><b>Testo</b> che visualizza colonne e righe semplici con valori vero o falso, percentuali, numero di membri e valori di input. </li> 
     <li id="li_3F871B88F3FA41E9B95EFF5A181E3D57">Una <b>dimensione</b> con rami corrispondenti agli elementi di risultato previsti. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Opzioni </td> 
   <td colname="col2"> Vedere la tabella seguente per il menu Opzioni. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_24D84440D0354C70928E8927624DB255"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menu Opzioni </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Imposta maiuscole/minuscole </td> 
   <td colname="col2"> Definisce la selezione dell'area di lavoro corrente come caso positivo del modello. Cancella il caso se non esiste alcuna selezione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Imposta filtro popolazione </td> 
   <td colname="col2"> Definisce la selezione dell'area di lavoro corrente come filtro popolazione del modello e sarà disegnata dai visitatori che soddisfano questa condizione. Il valore predefinito è "Everyone". </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mostra descrizione filtro complessa </td> 
   <td colname="col2"> Visualizza le descrizioni dei filtri definiti. Fare clic per visualizzare gli script di filtraggio per il filtro maiuscole/minuscole e la popolazione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascondi nodi </td> 
   <td colname="col2"> Nasconde i nodi con solo una piccola percentuale della popolazione. Questo comando di menu viene visualizzato solo quando viene visualizzata la struttura decisionale. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Matrice di fusione </td> 
   <td colname="col2"> <p>Fate clic su <span class="uicontrol"> Opzioni</span> &gt; <span class="uicontrol"> Matrice</span> di fusione per visualizzare i valori Precisione, Richiama, Precisione e Punteggio F. Più vicino al 100%, migliore sarà il punteggio. </p> <p>La Matrice di Confusione fornisce quattro conteggi di precisione del modello utilizzando una combinazione di valori: 
     <ul id="ul_D9D512F5D74B44BDBD27B1912DF4CB02"> 
      <li id="li_28C541DF1CB543FEAF2D13C2F329DB52">Positivo effettivo (AP) </li> 
      <li id="li_56233006A1544D95A72CE096CA55C1E6">Previsto positivo (PP) </li> 
      <li id="li_375FB2D6A0A3418A9AD377C9EBB65386">Negativo effettivo (AN) </li> 
      <li id="li_07A5D23A36BA4D448C25C1414836EB8E">Predicted Negative (PN) </li> 
     </ul> </p> <p>Suggerimento:  Questi numeri si ottengono applicando il modello di punteggio ottenuto dei dati di test del 20% conservati e già noti come risposta vera. Se il punteggio è maggiore del 50%, viene previsto come caso positivo (che corrisponde al filtro definito). Precisione = (TP + TN)/(TP + FP + TN + FN), Recall = TP / (TP + FN) e Precision = TP / (TP + FP). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visualizza legenda </td> 
   <td colname="col2">Consente di attivare e disattivare un tasto legenda nella struttura decisionale. <img placement="break" id="image_D5B9415A48C04619955BD96970F720A1" src="assets/decison_tree_legend.png" />Questo comando di menu viene visualizzato solo quando viene visualizzata la struttura decisionale. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Advanced </td> 
   <td colname="col2"> Fare clic per aprire il menu Avanzate per un utilizzo approfondito della struttura decisionale. Vedere la tabella seguente per le opzioni di menu. </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_91E4A74BFB224ABD889147324AC2910F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Menu Avanzate </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Dimensioni set di formazione </td> 
   <td colname="col2"> <p>Controlla la dimensione del set di formazione utilizzato per l'edificio modelli. I set più grandi richiedono più tempo per allenarsi, quelli più piccoli richiedono meno tempo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Normalizzazione input </td> 
   <td colname="col2"> <p> Consente all'utente di specificare se utilizzare la tecnica Min-Max o Z Score per normalizzare gli input nel modello. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fattore di sovracampionamento SMOTE </td> 
   <td colname="col2"> Se il caso positivo non si verifica molto spesso (meno del 10%) nel campione di formazione, SMOTE viene utilizzato per fornire ulteriori campioni. Questa opzione consente all'utente di indicare il numero di campioni da creare utilizzando SMOTE. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Soglia di distribuzione della classe foglia </td> 
   <td colname="col2"> Consente di impostare la soglia prevista per una foglia durante il processo di creazione della struttura ad albero. Per impostazione predefinita, tutti i membri di un nodo devono essere identici affinché sia una foglia (prima del passaggio di potatura). </td> 
  </tr> 
 </tbody> 
</table>

