---
description: Tabella che definisce i parametri del gruppo di utenti.
title: Gruppi utenti coda query
uuid: 90d9058c-1809-4579-a8c6-930a07affc83
exl-id: e9586ad4-4c0b-48b7-b533-4d23a0f4a216
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 2%

---

# Gruppi utenti coda query{#query-queue-user-groups}

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
   <td colname="col3"> <p>Un nome definito dall'utente del gruppo di utenti, ad esempio Analisti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Criteri </p> </td> 
   <td colname="col2"> <p>vettore </p> </td> 
   <td colname="col3"> <p>Specifica un tipo di criterio. Fare clic con il pulsante destro del mouse per scegliere Criteri standard o Pianificazione giornaliera. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Criteri standard </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Un criterio standard assicura che gli utenti con priorità bassa vengano spostati in modo incrementale verso l’alto e pianificati, anche se gli utenti con priorità più elevata accedono alla coda. È possibile aggiungere più criteri dello stesso tipo in un gruppo e il loro effetto è cumulativo. 
     <ul id="ul_F7F60D23DC934F61AF2183177A11FA65"> 
      <li id="li_805ED3E740814FAEBFF2B411BAB3D248"><b>Limite di priorità:</b> il limite al di sopra del quale la priorità non viene incrementata. Il valore di priorità massimo. Puoi utilizzare questo valore per mantenere le priorità generate da questo criterio in un intervallo specifico (ad esempio, in modo che le priorità per altri gruppi di utenti siano sempre più elevate, o in modo che non superino la priorità Incommensurabile). </li> 
     </ul> </p> <p> <b>Incrementi dei criteri standard</b> </p> <p>Le impostazioni incrementali per i criteri standard aumentano la priorità di un insieme di query man mano che il tempo passa. Questo non costringe la pianificazione dei bundle, ma puoi utilizzare queste impostazioni per dare priorità agli utenti che attendono da molto tempo. I parametri in coda influiscono sulle query attualmente in coda (ad esempio in attesa a causa di risorse insufficienti per completarle). I parametri pianificati influiscono sulle query a cui viene data risposta. La priorità di una query aumenta in base al numero specificato nei campi appropriati per l’incremento e l’intervallo di incremento: 
     <ul id="ul_7A5EE18CE10E4484A203B938525C806C"> 
      <li id="li_4B5CD827AF3848DA811A96C851340518"><b>Incremento in coda:</b> imposta l’incremento di priorità per aggiornamento durante la coda. Questa impostazione assicura che gli utenti a bassa priorità vengano spostati verso l’alto nella coda di pianificazione. </li> 
      <li id="li_91CA798235234A1CAC7AB32A7FB1CE84"><b>Intervallo di incremento in coda:</b> imposta il numero di secondi tra gli aggiornamenti durante la coda. </li> 
      <li id="li_079275E21ABA43B796A853624A6BDC29"><b>Incremento pianificato:</b> imposta l'incremento di priorità per aggiornamento durante la pianificazione. </li> 
      <li id="li_3AE2EC3EBE6C4670BA0FA1BBD03FEBBD"><b>Intervallo di incremento pianificato:</b> imposta il numero di secondi tra gli aggiornamenti pianificati. <p> <p>Nota:  L'impostazione dei tassi di aggiornamento dell'incremento e dell'intervallo più elevati per i bundle in coda rispetto ai bundle pianificati può causare oscillazioni. (Ad esempio, si supponga di impostare il valore Incremento in coda su 100 e l'Incremento programmato su 0, quindi di impostare il valore Intervallo incremento in coda su 1 e la Priorità non toccabile su un valore elevato. Se due batch di query hanno una priorità di base pari a 0 e non sono disponibili risorse sufficienti per eseguire entrambe le query contemporaneamente, viene pianificata una di esse. Dopo un secondo, la query non pianificata ha una priorità di 100 ed evita quella pianificata. Dopo altri due secondi, quello che è stato prescelto ora ha una priorità di 200, e i due switch si posizionano di nuovo. Nessuna delle due query termina, perché ogni due secondi la query che si sta calcolando viene eliminata e l’altra query può essere eseguita.) </p> </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Criteri di pianificazione giornaliera </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>Consente di modificare la priorità in orari specifici del giorno. Questa pianificazione è utile per i client automatizzati, ad esempio <span class="wintitle"> Report Server</span>, e per gli utenti del sistema che vivono in fusi orari diversi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Modifiche </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Fai clic con il pulsante destro del mouse per aggiungere una modifica di priorità pianificata. L'ora di modifica è l'ora del giorno in cui si verifica la modifica. Il formato è ora:minuti AM/PM. Se AM o PM non viene inserito, il sistema utilizza l'ora militare. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Limite priorità </p> </td> 
   <td colname="col2"> <p>int </p> </td> 
   <td colname="col3"> <p>Il valore di priorità massimo risultante da una modifica. La modifica della priorità è l’importo aggiunto alla priorità. Ad esempio, il valore 0 restituisce una priorità predefinita. Qualsiasi altro valore determina una priorità della priorità predefinita più questo numero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utenti </p> </td> 
   <td colname="col2"> <p>vettore </p> </td> 
   <td colname="col3"> <p>Elenca gli utenti membri del gruppo. </p> <p> <b>Nome:</b> nome dell’utente visualizzato nel campo Nome comune del certificato dell’utente. </p> <p> <b>Priorità supplementare:</b> fornisce priorità aggiuntiva alla priorità di base del gruppo di utenti per determinare la priorità iniziale per quell’utente. </p> </td> 
  </tr> 
 </tbody> 
</table>
