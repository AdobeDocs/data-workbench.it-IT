---
description: Se state lavorando con i dati raccolti dal traffico del sito Web, potete utilizzare la trasformazione Sessionizza per determinare come vengono definite le sessioni.
solution: Analytics
title: Sessionizza
topic: Data workbench
uuid: c6e2487a-80e5-4e00-b4d4-2ce013fac3ea
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Sessionizza{#sessionize}

Se state lavorando con i dati raccolti dal traffico del sito Web, potete utilizzare la trasformazione Sessionizza per determinare come vengono definite le sessioni.

La trasformazione assume come input un timestamp e un ID di tracciamento e produce un numero di sessione per ciascuna voce di registro. Il numero di sessione è &quot;1&quot; per la prima sessione con un determinato ID tracciamento, &quot;2&quot; per la seconda sessione con lo stesso ID tracciamento e così via. L’output può essere utilizzato direttamente come chiave di sessione perché ha un valore univoco per ogni sessione.

>[!NOTE]
>
>Per funzionare, la [!DNL Sessionize] trasformazione richiede che i dati siano ordinati nel tempo e raggruppati dall&#39;ID di tracciamento nei dati di origine. Pertanto, [!DNL Sessionize] funziona solo se definito nel [!DNL Transformation.cfg] file o in un [!DNL Transformation Dataset Include] file.

<table id="table_34984DF9340149C0A5016F08EABAD158"> 
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
   <td colname="col2"> Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Commenti </td> 
   <td colname="col2"> Facoltativo. Note sulla trasformazione. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione </td> 
   <td colname="col2"> Condizioni in cui viene applicata la trasformazione. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Timestamp di input </td> 
   <td colname="col2"> Campo contenente i valori della marca temporale da utilizzare. </td> 
   <td colname="col3"> x-timestamp </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ID tracciamento input </td> 
   <td colname="col2"> <p>Campo contenente i valori dell’ID di tracciamento da utilizzare. Il valore deve essere un numero esadecimale inferiore o a 64 bit (16 cifre) oppure un numero intero decimale di almeno 16 cifre. </p> <p> <p>Nota: Per utilizzare un campo diverso da x-trackingid per l’ID di tracciamento, è necessario prima hash il campo. Vedi <a href="../../../../../home/c-dataset-const-proc/c-data-trans/c-transf-types/c-standard-transf/c-hash.md#concept-9c353923264941c3aea4428fed66d369"> Hash</a>. </p> </p> </td> 
   <td colname="col3"> x-trackingid </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Durata massima sessione </p> </td> 
   <td colname="col2">La durata più lunga della sessione prima dell’avvio di una nuova sessione. In questo modo, le pagine Web con contenuto automatico vengono aggiornate e non vengono create sessioni di durata arbitraria. Se la condizione <span class="wintitle"> di</span> timeout è soddisfatta e il referente di un clic è impostato su una delle voci nel parametro Domini interni, per definire la fine di una sessione viene utilizzata la durata massima della sessione. Nessuna sessione può superare la durata massima specificata, indipendentemente dal numero di clic che contiene. Il valore consigliato è 48 ore. Per ulteriori informazioni sui parametri Durata massima sessione e Domini interni, vedere <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Impostazioni di configurazione per i dati</a>Web. </td> 
   <td colname="col3"> 48 ore </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Numero sessione di output </td> 
   <td colname="col2"> Campo in cui è memorizzato il numero di sessione. Questo campo ha un valore univoco per ogni sessione per ogni visitatore. </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Timeout sessione </td> 
   <td colname="col2"> <p>Il tempo che deve trascorrere tra le voci di registro di un determinato visitatore per determinare la fine di una sessione e l’inizio di una nuova sessione (ovvero il timeout tipico utilizzato per definire una sessione utente). Il valore consigliato di questo parametro è 30 minuti. Se la condizione di timeout non è soddisfatta e il referente di un clic non è impostato su uno dei referenti nel parametro Domini interni, Timeout sessione viene utilizzato per definire la sessione. </p> <p> Se la condizione di timeout è soddisfatta e cs(referrer-domain) per una voce di registro è nell’elenco dei domini interni, la durata massima della sessione determina se la voce di registro corrente fa parte di una sessione esistente o l’inizio di una nuova sessione. </p> <p> Per ulteriori informazioni sul parametro Timeout sessione, vedere <a href="../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519"> Impostazioni di configurazione per i dati</a>Web. </p> </td> 
   <td colname="col3"> 30 minuti </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Condizione di timeout </td> 
   <td colname="col2"> Condizione da soddisfare affinché una voce di registro venga considerata l’inizio di una nuova sessione. Il tempo trascorso tra la voce di registro e la voce di registro precedente deve essere almeno pari al valore del parametro Timeout sessione. </td> 
   <td colname="col3"> </td> 
  </tr> 
 </tbody> 
</table>

Una nuova sessione inizia quando si verifica una delle situazioni seguenti:

* L’ID di tracciamento cambia.
* L’ora dall’ultima voce di registro è almeno uguale al valore del parametro Timeout sessione e la condizione di timeout è soddisfatta.
* L’ora dalla prima voce di registro dell’ultima sessione supera il valore del parametro Durata massima sessione.

>[!NOTE]
>
>Se avete già definito Durata massima sessione e Timeout sessione come parametri nel [!DNL Session Parameters.cfg] file, non immettete i relativi valori nella configurazione. Potete fare riferimento ai parametri digitando *$(nome parametro)* come illustrato nell&#39;esempio seguente. Per ulteriori informazioni su questi parametri, vedere Impostazioni [di configurazione per i dati](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)Web.

La [!DNL Sessionize] trasformazione in questo esempio prende come input i campi x-timestamp e x-trackingid e registra il numero di sessione per ogni voce di registro nel campo x-session-key. La trasformazione [!DNL Timeout Condition] è basata su una [!DNL Neither] condizione: Se il campo cs(referrer-domain) per una voce di registro corrisponde a un membro del parametro Domains interno, la condizione restituisce false. Prendete nota dei riferimenti ai parametri Domini interni e Timeout sessione.

Per informazioni su [!DNL NeitherCondition], consultate [Condizioni](../../../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md). Per informazioni sui parametri Domini interni e Timeout sessione, vedere Impostazioni [di configurazione per i dati](../../../../../home/c-dataset-const-proc/c-config-web-data/c-config-web-data.md#concept-9a306b65483a484bb3f6f3c1d7e77519)Web.

![](assets/cfg_TransformationType_Sessionize.png)

