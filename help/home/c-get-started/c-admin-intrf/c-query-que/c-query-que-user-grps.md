---
description: Tabella che definisce i parametri del gruppo di utenti.
solution: Analytics
title: Gruppi utenti coda di query
topic: Data workbench
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Gruppi utenti coda di query{#query-queue-user-groups}

Tabella che definisce i parametri del gruppo di utenti.

<table id="table_670A47E25A7A43F0B599BD7ABB173E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Campo </th> 
   <th colname="col2" class="entry"> Tipo </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nome </p> </td> 
   <td colname="col2"> <p>string </p> </td> 
   <td colname="col3"> <p>Nome definito dall’utente del gruppo di utenti, ad esempio Analisti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Criteri </p> </td> 
   <td colname="col2"> <p>vettore </p> </td> 
   <td colname="col3"> <p>Specifica un tipo di criterio. Fare clic con il pulsante destro del mouse per scegliere Politica standard o Pianificazione giornaliera. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Criteri standard </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Un criterio standard garantisce che gli utenti con priorità bassa vengano spostati in modo incrementale verso l'alto e programmati, anche se gli utenti con priorità superiore accedono alla coda. È possibile aggiungere più criteri dello stesso tipo in un gruppo e il loro effetto è cumulativo. 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>Limite priorità:</b> Limite al di sopra del quale la priorità non viene incrementata. Il valore di priorità massimo. Potete utilizzare questo valore per mantenere le priorità generate da questo criterio in un intervallo specifico (ad esempio, in modo che le priorità per altri gruppi di utenti siano sempre più alte, o in modo che non superino la priorità non toccabile). </li> 
     </ul> </p> <p> <b>Incrementi criteri standard</b> </p> <p>Le impostazioni di incremento per Standard Policy aumentano la priorità di un gruppo di query al passaggio del tempo. Questo non forza la pianificazione dei batch, ma puoi utilizzare queste impostazioni per dare priorità agli utenti che hanno aspettato a lungo. I parametri messi in coda influiscono sulle query attualmente in coda (ad esempio in attesa a causa di risorse insufficienti per completarle). I parametri pianificati influiscono sulle query alle quali viene fornita risposta. La priorità di una query aumenta in base al numero specificato nei campi appropriati per l'incremento e l'intervallo di incremento: 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>Incremento in coda:</b> Imposta l'incremento di priorità per ogni aggiornamento durante la coda. Questa impostazione consente di spostare gli utenti con priorità bassa verso l’alto nella coda di pianificazione. </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Intervallo incremento in coda:</b> Imposta il numero di secondi tra gli aggiornamenti durante la coda. </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Incremento pianificato:</b> Imposta l'incremento di priorità per ogni aggiornamento durante la programmazione. </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Intervallo di incremento pianificato:</b> Imposta il numero di secondi tra gli aggiornamenti pianificati. <p> <p>Nota:  L'impostazione di tassi di aggiornamento di incremento e intervallo superiori per i batch in coda rispetto a quelli programmati può causare oscillazioni. Ad esempio, si supponga di impostare il valore Incremento in coda su 100 e l'Incremento pianificato su 0, quindi di impostare il valore Intervallo incrementi in coda su 1 e la priorità non toccabile su un valore elevato. Se due batch di query hanno una priorità di base pari a 0 e non sono disponibili risorse sufficienti per eseguire entrambe le query contemporaneamente, uno di questi è pianificato. Dopo un secondo, la query non pianificata ha una priorità di 100 ed evita quella pianificata. Dopo altri due secondi, quello che era stato predetto ora ha una priorità di 200, e i due switch si posizionano di nuovo. Nessuna query termina, perché ogni due secondi la query che si sta calcolando viene precompilata in modo da poter eseguire l'altra query.) </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pianificazione giornaliera </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Consente di modificare la priorità in orari specifici del giorno. Questa pianificazione è utile per i client automatizzati, come <span class="wintitle"> Report Server</span>, e quando gli utenti del sistema vivono in fusi orari diversi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifiche </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Fare clic con il pulsante destro del mouse per aggiungere una modifica di priorità pianificata. L’ora di modifica è l’ora del giorno in cui si verifica la modifica. Il formato è ora:minuti AM/PM. Se AM o PM non viene immesso, il sistema utilizza l'ora militare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite priorità </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Il valore di priorità massimo risultante da una modifica. Modifica priorità è l'importo aggiunto alla priorità. Ad esempio, il valore 0 restituisce una priorità predefinita. Qualsiasi altro valore determina una priorità della priorità predefinita più questo numero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utenti </p> </td> 
   <td colname="col2"> <p>vettore </p> </td> 
   <td colname="col3"> <p>Elenca gli utenti membri del gruppo. </p> <p> <b>Nome:</b> Il nome dell’utente così come viene visualizzato nel campo Nome comune del certificato dell’utente. </p> <p> <b>Priorità supplementare:</b> Fornisce priorità aggiuntiva alla priorità di base del gruppo di utenti per determinare la priorità iniziale per tale utente. </p> </td> 
  </tr> 
 </tbody> 
</table>

