---
description: Se lavori con i dati raccolti dal traffico del sito web, puoi utilizzare la trasformazione Sessionize per determinare come vengono definite le sessioni.
title: Sessionize
uuid: c6e2487a-80e5-4e00-b4d4-2ce013fac3ea
exl-id: bb25cb4b-7185-4524-8ff5-740b672e1cd9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 1%

---

# Sessionize{#sessionize}

{{eol}}

Se lavori con i dati raccolti dal traffico del sito web, puoi utilizzare la trasformazione Sessionize per determinare come vengono definite le sessioni.

La trasformazione prende come input una marca temporale e un ID di tracciamento e produce un numero di sessione per ogni voce di registro. Il numero di sessione è &quot;1&quot; per la prima sessione con un determinato ID di tracciamento, &quot;2&quot; per la seconda sessione con lo stesso ID di tracciamento e così via. L’output può essere utilizzato direttamente come chiave di sessione perché ha un valore univoco per ogni sessione.

>[!NOTE]
>
>Per lavorare, [!DNL Sessionize] La trasformazione richiede che i dati siano ordinati in tempo e raggruppati in base all’ID di tracciamento nei dati di origine. Pertanto, [!DNL Sessionize] funziona solo quando è definito in [!DNL Transformation.cfg] o in un [!DNL Transformation Dataset Include] file.

<table id="table_34984DF9340149C0A5016F08EABAD158"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Impostazione predefinita </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla trasformazione. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione </td> 
   <td colname="col2"> Le condizioni in cui viene applicata questa trasformazione. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Timestamp di input </td> 
   <td colname="col2"> Il campo contenente i valori della marca temporale da utilizzare. </td> 
   <td colname="col3"> x-timestamp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID tracciamento input </td> 
   <td colname="col2"> <p>Il campo contenente i valori dell’ID di tracciamento da utilizzare. Il valore deve essere un numero esadecimale a 64 bit (16 cifre) o un numero esadecimale inferiore o un numero intero decimale di 16 cifre o meno. </p> <p> <p>Nota: Se desideri utilizzare un campo diverso da x-trackingid per l’ID di tracciamento, devi prima aggiungere un hash al campo . Vedi <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-hash.md#concept-9c353923264941c3aea4428fed66d369"> Hash</a>. </p> </p> </td> 
   <td colname="col3"> x-trackingid </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durata massima della sessione </p> </td> 
   <td colname="col2">La durata più lunga della sessione prima dell’avvio di una nuova sessione. (In questo modo le pagine web con contenuto automatico vengono aggiornate dalla creazione di sessioni arbitrariamente lunghe.) Se la <span class="wintitle"> Condizione di timeout</span> è soddisfatto e il referente di un clic è impostato su una delle voci nel parametro Domini interni. Per definire la fine di una sessione viene utilizzata la durata massima della sessione. Nessuna sessione può superare la durata massima della sessione specificata, indipendentemente dal numero di clic che contiene. Il valore consigliato è 48 ore. Per ulteriori informazioni sui parametri Maximum Session Duration e Internal Domains, vedi <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Impostazioni di configurazione per i dati web</a>. </td> 
   <td colname="col3"> 48 ore </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numero della sessione di output </td> 
   <td colname="col2"> Campo in cui è memorizzato il numero di sessione. Questo campo ha un valore univoco per ogni sessione per ogni visitatore. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Timeout sessione </td> 
   <td colname="col2"> <p>Il tempo che deve trascorrere tra le voci di registro di un determinato visitatore per determinare la fine di una sessione e l’inizio di una nuova sessione (ovvero il timeout tipico utilizzato per definire una sessione utente). Il valore consigliato di questo parametro è di 30 minuti. Se la condizione Timeout non è soddisfatta e il referente di un clic non è impostato su uno dei referenti nel parametro Domini interni, per definire la sessione viene utilizzato Timeout sessione. </p> <p> Se la condizione di timeout è soddisfatta e cs(referrer-domain) per una voce di registro è nell'elenco dei domini interni, la durata massima della sessione determina se la voce di registro corrente fa parte di una sessione esistente o se inizia una nuova sessione. </p> <p> Per ulteriori informazioni sul parametro Timeout sessione, vedi <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Impostazioni di configurazione per i dati web</a>. </p> </td> 
   <td colname="col3"> 30 minuti </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione di timeout </td> 
   <td colname="col2"> La condizione che deve essere soddisfatta perché una voce di registro sia considerata l’inizio di una nuova sessione. Il tempo trascorso tra la voce di registro e la voce di registro precedente deve essere almeno pari al valore del parametro Timeout sessione . </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Una nuova sessione inizia quando si verifica una delle situazioni seguenti:

* L&#39;ID di tracciamento cambia.
* L’ora dall’ultima voce di registro è almeno uguale al valore del parametro Timeout sessione e la condizione Timeout viene soddisfatta.
* Il tempo trascorso dalla prima voce di registro dell’ultima sessione supera il valore del parametro Maximum Session Duration.

>[!NOTE]
>
>Se hai già definito la Durata massima sessione e il Timeout sessione come parametri nel [!DNL Session Parameters.cfg] file , non inserire valori per essi nella configurazione. Puoi fare riferimento ai parametri digitando *$(nome parametro)* come illustrato nell’esempio seguente. Per ulteriori informazioni su questi parametri, vedi [Impostazioni di configurazione per i dati web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

La [!DNL Sessionize] La trasformazione in questo esempio prende come input i campi x-timestamp e x-trackingid e registra il numero di sessione per ogni voce di log nel campo x-session-key. La trasformazione [!DNL Timeout Condition] si basa su un [!DNL Neither] condizione: Se il campo cs(referrer-domain) per una voce di registro corrisponde a un membro del parametro Internal Domains, la condizione restituisce false. Prendi nota dei riferimenti ai parametri Domini interni e Timeout sessione .

Per informazioni sulla [!DNL NeitherCondition], vedi [Condizioni](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md). Per informazioni sui parametri Domini interni e Timeout sessione, vedi [Impostazioni di configurazione per i dati web](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519).

![](assets/cfg_TransformationType_Sessionize.png)
