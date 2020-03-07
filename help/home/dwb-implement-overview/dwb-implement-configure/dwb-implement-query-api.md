---
description: Guida rapida per l'impostazione di un'API di query.
title: Impostazione API query
uuid: 521f06a4-65ee-4206-b769-4c1ce6e5fe7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Impostazione API query{#query-api-setup}

Guida rapida per l&#39;impostazione di un&#39;API di query.

Per impostare l&#39;API Query, effettuate le operazioni seguenti:

1. Acquisizione certificato API query

   Invia un&#39;e-mail al team Tech Ops di Adobe Email - `Dataworkbench@adobe.com`.

   Specificare il nome CN da utilizzare per l&#39;API Query( fornire un nome generico come API `<Client>` Query).

   >[!NOTE]
   >
   >Tech Ops genererà il certificato e lo caricerà in un URL. Dopo aver ricevuto la notifica da Tech Ops relativa alla generazione del ticket, i consulenti Adobe sono invitati a informarvi che il ticket verrà inviato nuovamente.

1. Download ed estrazione di API Stunnel. Ricevi il file api-stunnel da un consulente.

   Verificare che Perl sia installato nel computer.

   Nella cartella estratta (il percorso della cartella in cui copiate il file), copiate il certificato API di query all&#39;interno della cartella *stunnel* .

1. Configurare Stunnel.conf

   All’interno della cartella *Stunnel* (in cui è stato copiato il certificato) dovrebbe essere presente un file denominato *stunnel.conf* .

   Modificate il file in Blocco note.

   ![](assets/dwb_impl_API1.png)

   Modificate i parametri come segue: ![](assets/dwb_impl_API2.png)

   In questo file è necessario modificare due parametri.

   * *Cert* = nome sul certificato. In questo esempio è Aadhithiya Ramani QAPI Client.pem.
   * *Connect* = nome del server per l’unità di elaborazione dati principale.

1. Copia di *Query.pm*.

   Il file *Query.pm* sarà disponibile nella cartella delle API di Insight.

   Copiate il file *Query.pm* e incollatelo nella cartella Perl Library (in genere sarà *C:\Perl64\lib *, ma verificate dove è installato Perl nel computer).

1. Modificare il file *api-http.pl*

   Il file api-http.pl sarà disponibile nella cartella api-stunnel.

   Solo un parametro da modificare

   *My $profile* = nome profilo per il quale state configurando l&#39;API Query.

1. Installate l&#39;API Query.

   Aprite il prompt dei comandi nel sistema come &quot;Amministratore&quot; e andate alla directory in cui è stato estratto lo *stunnel* come illustrato: ![](assets/dwb_impl_API3.png)

   Esegui il comando seguente *.\stunnel -install*. ![](assets/dwb_impl_API4.png)

   Dopo l&#39;esecuzione del comando, compare una finestra in cui viene indicato che è installato lo *stunnel* .

   >[!NOTE]
   >
   >Dopo l&#39;esecuzione del comando, compare una finestra in cui viene indicato che è installato lo *stunnel* .

1. Verifica della configurazione dello stunnel dell&#39;API Query

   Il passaggio finale di questo processo sarà quello di verificare la configurazione dell&#39;API Query. Nel prompt dei comandi utilizzato per installare la directory api-stunnel. ![](assets/dwb_impl_API5.png)

   Eseguite lo script Perl disponibile in quella cartella utilizzando il seguente comando* perl api-http.pl*. ![](assets/dwb_impl_API6.png)

   Dopo aver eseguito lo script, i risultati devono essere come lo screenshot di seguito (l&#39;ora e i valori di data nel risultato variano a seconda del tempo e di altri parametri nel profilo in cui hai configurato l&#39;API Query (nel passaggio 6). ![](assets/dwb_impl_API7.png)

