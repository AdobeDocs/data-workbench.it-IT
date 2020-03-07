---
description: Una dimensione temporale consente di creare un set di dimensioni temporali locali periodiche o assolute (come Giorno, Giorno della settimana, Ora del giorno, Ora della prenotazione e così via) in base a qualsiasi campo di marca temporale specificato per il parametro Ora di input (1970 epoch).
solution: Analytics
title: Dimensioni tempo
topic: Data workbench
uuid: b633cf4f-0db4-4378-9e59-43b6ad8f772d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dimensioni tempo{#time-dimensions}

Una dimensione temporale consente di creare un set di dimensioni temporali locali periodiche o assolute (come Giorno, Giorno della settimana, Ora del giorno, Ora della prenotazione e così via) in base a qualsiasi campo di marca temporale specificato per il parametro Ora di input (1970 epoch).

Quando definite le dimensioni dell’ora, potete anche scegliere un giorno diverso dal lunedì da usare come inizio di una settimana specificando il parametro Giorno inizio settimana. Puoi definire più di un set di dimensioni temporali nel set di dati, purché le dimensioni abbiano nomi diversi.

Le dimensioni temporali sono definite dai seguenti parametri:

<table id="table_9734F6CD7ABA4661A2F9A5FB948A7282"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> impostazione predefinita </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descrittivo della dimensione così come viene visualizzata nel workbench dati. Il nome della dimensione non può includere un trattino (-). </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla dimensione estesa. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensioni </td> 
   <td colname="col2"> <p>È possibile specificare i nomi delle dimensioni per uno dei seguenti periodi: </p> <p> 
     <ul id="ul_EB0837DD66BE4004A615A6029EEF4CD5"> 
      <li id="li_2E46E6DB004E443C8CC831DCEE743D60"> Day </li> 
      <li id="li_F59A27779EBE4E2A84E0972EE8BCDFA7"> Giorno della settimana </li> 
      <li id="li_7D74CD547ED1449091EF7B2E0E8C46DE"> Ora </li> 
      <li id="li_706AF9D385CB44C098DEBACA3BA2CD4B"> Ora del giorno </li> 
      <li id="li_76FBF69B25954885A0192D308A155E41"> Mese </li> 
      <li id="li_3C16955BE5C54291A25E25CD31259661"> Settimana </li> 
     </ul> </p> <p> I nomi inseriti sono i nomi visualizzati nei menu delle dimensioni e nelle visualizzazioni nel workbench dati. Se lasciate vuoto il nome di una dimensione temporale, la dimensione non viene creata nel dataset. </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nascosto </td> 
   <td colname="col2"> Determina se la dimensione viene visualizzata nell'interfaccia workbench dati. Per impostazione predefinita, questo parametro è impostato su false. Se, ad esempio, la dimensione deve essere utilizzata solo come base di una metrica, è possibile impostare questo parametro su true per nascondere la dimensione dalla visualizzazione del workbench dati. </td> 
   <td colname="col3"> true </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Tempo di ingresso (1970 epoch) </td> 
   <td colname="col2"> <p>Nome del campo timestamp da utilizzare come input. </p> <p> <p>Nota:  I valori del campo devono rappresentare il numero di secondi dal 1° gennaio 1970 alle 00:00:01. Se il tempo di input non è un tempo valido (1970-2037), il processo di trasformazione non riuscirà e il server workbench dati genererà un errore. </p> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Elemento padre </td> 
   <td colname="col2"> Nome della dimensione padre. Qualsiasi dimensione numerabile può essere una dimensione padre. Per i dati Web, l'elemento padre è Session. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Giorno inizio settimana </td> 
   <td colname="col2"> <p>Il giorno da utilizzare come primo giorno di una settimana. </p> <p> Questo parametro influisce sulla dimensione Settimana, sulla dimensione Giorno della settimana e sulle eventuali dimensioni temporali di reporting definite in termini di settimane. </p> </td> 
   <td colname="col3"> Lun </td> 
  </tr> 
 </tbody> 
</table>

Questo esempio crea un set di dimensioni temporali in base al campo x-time-1970 definito dall&#39;utente. Il set di dimensioni temporali è denominato &quot;Ora sessione&quot;. Poiché l’elemento padre di ciascuna dimensione è la dimensione Sessione, ogni elemento delle dimensioni ora corrisponde all’ora di inizio di una sessione. Il parametro Giorno inizio settimana specifica che ogni settimana della dimensione Settimana inizia il lunedì.

![](assets/cfg_Transformation_Dim_TimeDim.png)

