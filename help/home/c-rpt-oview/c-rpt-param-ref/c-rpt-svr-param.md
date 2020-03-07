---
description: Informazioni sui parametri Report Server.cfg.
solution: Analytics
title: Report Server.cfg Parameters
topic: Data workbench
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Report Server.cfg Parameters{#report-server-cfg-parameters}

Informazioni sui parametri Report Server.cfg.

L&#39;esempio [!DNL Report Server.cfg] mostrato in [Configurazione della connessione a Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) contiene solo i parametri inclusi nel [!DNL Report Server.cfg] file per impostazione predefinita.

Se contattate Adobe License Server tramite un server proxy, dovete aggiungere il vettore Licensing e i relativi parametri al server [!DNL Report Server.cfg]. Di seguito è riportato un esempio di questo vettore e dei relativi parametri che è possibile utilizzare come modello per il vettore Licensing:

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

La tabella seguente fornisce una descrizione dei parametri del [!DNL Report Server.cfg] file:

<table id="table_9DA4A3124A9D444CBB4CBFF6FA279A42"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Excel Extension </td> 
   <td colname="col2"> <p>Le estensioni Excel supportate includono: </p> <p>Estensione Excel = stringa: <span class="filepath"> .xlsx </span> </p> <p>Estensione Excel = stringa: <span class="filepath"> .xls </span> (predefinito) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Font </td> 
   <td colname="col2"> <p>Facoltativo. Vettoriale che elenca i font che <span class="keyword"> Report Server </span> deve utilizzare per il rendering dei caratteri unicode basati su UTF8. Il numero di font nell'elenco è illimitato. </p> <p>Il primo font deve sempre essere Lucida Sans Console. Se questo parametro non è incluso nel file <span class="filepath"> Report Server.cfg </span> , <span class="keyword"> Report Server </span> utilizza solo la console Lucida Sans per visualizzare il testo. </p> <p> <span class="keyword"> Il server di report </span> utilizza il primo font dell'elenco per eseguire il rendering di tutti i caratteri fino a quando non rileva un carattere che non può essere rappresentato. Quindi utilizza il secondo font nell'elenco per eseguirne il rendering. Se tale carattere non esegue il rendering del carattere, <span class="keyword"> il server di report </span> utilizza il terzo carattere nell'elenco per eseguirne il rendering e così via, fino alla fine dell'elenco dei font. Se il font corretto non è elencato nel vettore, <span class="keyword"> Report Server </span> visualizza il valore esadecimale del carattere. </p> <p> <p>Nota:  Non apportare modifiche a questo parametro mentre <span class="keyword"> Report Server </span> è in esecuzione. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Impostazione gamma </span> per l'output di file <span class="filepath"> .png </span> . Il valore predefinito è 1.6. </p> <p> <p>Nota:  Adobe non consiglia di modificare questo valore. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licenze </td> 
   <td colname="col2"> <p>Facoltativo. È necessario modificare i parametri in questo vettore solo se si contatta il server licenze Adobe tramite un server proxy. </p> <p>Identificatore di sezione per i parametri impostati per contattare il server licenze di Adobe tramite un server proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo proxy </td> 
   <td colname="col2"> L'indirizzo di un server proxy che <span class="keyword"> Report Server </span> deve utilizzare per accedere al server licenze di Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Password proxy </td> 
   <td colname="col2"> Facoltativo. La password associata al Nome utente <span class="wintitle"> proxy </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta proxy </td> 
   <td colname="col2"> La porta del server proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome utente proxy </td> 
   <td colname="col2"> Facoltativo. Nome utente utilizzato per accedere al server proxy. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Posizione di rete </td> 
   <td colname="col2"> Il percorso di rete che <span class="keyword"> Report Server </span> utilizza per risolvere il nome comune del server in un indirizzo IP. Le posizioni di rete sono definite nel file indirizzo che si trova nella directory Indirizzi del computer server workbench dati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server </td> 
   <td colname="col2"> <p>Identificatore sezione per i parametri impostati per configurare quali computer server workbench dati <span class="keyword"> Report Server </span> devono connettersi per generare i report. Questo include un numero che indica quanti elementi sono elencati in questo vettore. </p> <p>Per ciascun server, aggiungete una voce serverInfo e completate i parametri come necessario. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo </td> 
   <td colname="col2"> Indirizzo IP del computer server workbench dati a cui <span class="keyword"> Report Server </span> deve connettersi per generare i report. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome che <span class="keyword"> Report Server </span> utilizza internamente per identificare il server workbench dati. Si tratta semplicemente di un'etichetta interna, che consente di utilizzare qualsiasi nome. Per coerenza, si consiglia di utilizzare il nome comune elencato nel certificato digitale del server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta </td> 
   <td colname="col2"> Porta attraverso la quale <span class="keyword"> Report Server </span> comunica con il server workbench dati. Per le connessioni sicure, questo valore è in genere 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo proxy </td> 
   <td colname="col2"> L'indirizzo di un server proxy che <span class="keyword"> Report Server </span> deve utilizzare per accedere al server Workbench dati. Questo parametro è necessario solo quando è necessario un server proxy per connettersi ai computer server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Password proxy </td> 
   <td colname="col2"> La password del server proxy. Questo parametro è necessario solo quando è necessario un server proxy per connettersi ai computer server workbench dati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta proxy </td> 
   <td colname="col2"> La porta del server proxy. Il valore predefinito è 8080. Questo parametro è necessario solo quando è necessario un server proxy per connettersi ai computer server workbench dati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome utente proxy </td> 
   <td colname="col2"> Nome utente del server proxy. Questo parametro è necessario solo quando è necessario un server proxy per connettersi ai computer server workbench dati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificato client SSL </td> 
   <td colname="col2"> Nome del file di certificato SSL per il computer <span class="keyword"> Report Server </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome comune server SSL </td> 
   <td colname="col2"> <span class="wintitle"> Nome comune server </span> elencato nel certificato digitale del server workbench dati. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usa SSL </td> 
   <td colname="col2"> Indica se SSL è utilizzato per la comunicazione protetta tra il server workbench dati e il server <span class="keyword"> report </span>. Le opzioni sono true o false. Il valore predefinito è true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite memoria risultato (KB) </td> 
   <td colname="col2"> <p>La quantità di memoria (in KB) che si desidera rendere disponibile per report e avvisi. Il valore predefinito è 50000. </p> <p>Durante l'esecuzione dei report, <span class="keyword"> Report Server </span> verifica prima questo valore, quindi verifica il valore nel parametro Dimensione massima sezione. Ad esempio, se impostate questo parametro su 50.000 e Dimensione massima sezione su 50, <span class="keyword"> Report Server </span> esegue solo 50 aree di lavoro alla volta anche se è disponibile spazio per eseguire più aree di lavoro. </p> <p> <p>Nota:  Questo limite non deve mai superare il valore impostato nel parametro Limite di memoria query del server workbench dati e, idealmente, deve essere impostato un po' più in basso rispetto al limite di memoria <span class="wintitle"> query </span> per fornire un margine di manovra agli altri utenti che potrebbero eseguire contemporaneamente i rapporti. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensione massima sezione </td> 
   <td colname="col2"> Il numero massimo di aree di lavoro del report che <span class="keyword"> il server di report </span> può eseguire contemporaneamente. Il valore predefinito è 50. Per ulteriori informazioni sull'utilizzo di <span class="keyword"> questa impostazione da parte del server di report, consulta la descrizione del parametro </span> Result Memory Limit (KB) <span class="wintitle"> </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Software di aggiornamento </td> 
   <td colname="col2"> <p>Indica se consentire l'aggiornamento del <span class="keyword"> software del </span> server di report da parte del server workbench dati. Le opzioni sono true o false. Il valore predefinito è true. </p> <p>Di seguito è riportato un esempio di questo parametro che potete usare come modello: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utilizzare il rendering hardware OpenGL </td> 
   <td colname="col2"> <p>Controlla se <span class="keyword"> Report Server </span> utilizza il rendering hardware (come la scheda grafica del computer) per produrre l'output del report. Le opzioni sono true o false. Il valore predefinito è true. </p> <p>Questo parametro deve essere impostato su false solo in caso di problemi con la scheda grafica. Se impostato su false, <span class="keyword"> Report Server </span> non tenta di utilizzare il rendering hardware e utilizza il rendering software per impostazione predefinita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Generazione di rapporti </td> 
   <td colname="col2"> Identificatore di sezione per i parametri impostati per configurare il reporting. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervallo messaggio di completamento </td> 
   <td colname="col2"> <p>Frequenza (in secondi) con cui <span class="keyword"> Report Server </span> stampa i messaggi di stato di completamento quando le query vengono eseguite durante la generazione del rapporto o dell'avviso. Il valore predefinito è 120 secondi. </p> <p>Esempio: Le query dell'area di lavoro sono completate al 62,145672%. </p> <p>I messaggi di completamento vengono scritti nel <span class="filepath"> report server.log </span> e sincronizzati con il server. Questa impostazione controlla i file <span class="filepath"> status.txt </span> che vengono inviati avanti e indietro per ciascun set di rapporti, in modo che la percentuale di completamento possa essere visualizzata con le miniature. I messaggi vengono inviati ogni volta che un set di rapporti viene completato o quando viene raggiunto l'intervallo, a seconda di quale viene prima. Se si imposta questo valore più alto, non viene applicata la frequenza con cui vengono visualizzati i report generati dalle miniature nell'interfaccia client, ma viene anche determinato il numero di messaggi intermedi visualizzati. Se si specifica un valore basso, il sistema può dedicare molto tempo alla sincronizzazione dei dati, poiché i dati vengono sincronizzati dal server <span class="keyword"> di report al profilo, tra tutte le unità di elaborazione dati e a tutti i client connessi ogni volta che un messaggio </span> status.txt <span class="filepath"> </span> viene modificato. </p> <p>Il sistema invia sempre un file <span class="filepath"> status.txt </span> al completamento di un set di report, indipendentemente dall'impostazione di questo parametro di configurazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profili </td> 
   <td colname="col2"> <p>Numero che indica quanti elementi sono elencati in questo vettore. Per ciascun profilo per il quale creare i rapporti, aggiungi una voce <span class="wintitle"> Profilo rapporto </span> nel vettore Profili e completa i parametri Server e Profilo. </p> <p> <span class="wintitle"> Server </span> - Il nome che <span class="keyword"> Report Server </span> utilizza internamente per identificare il server workbench dati. Questo nome deve essere il nome comune del server elencato nel certificato SSL del server workbench dati. </p> <p> <span class="wintitle"> Profilo </span> - Nome del profilo per il quale creare i rapporti. Questo nome deve corrispondere al profilo denominato nel computer server workbench dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server SMTP per errori </td> 
   <td colname="col2"> <p>L'indirizzo del server SMTP da cui si desidera inviare gli errori del server <span class="wintitle"> di report </span> via e-mail. </p> <p>Esempio: <span class="filepath"> mail.mycompany.com </span> </p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Password errore server SMTP </td> 
   <td colname="col2"> <p>La password per accedere al server SMTP. Questo parametro è facoltativo, a meno che non sia necessario effettuare il login per inviare la posta elettronica. </p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server SMTP per gli errori inviati da </td> 
   <td colname="col2"> L'indirizzo e-mail dal quale si desidera inviare gli errori <span class="wintitle"> del server di report </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server SMTP per gli errori inviati a </td> 
   <td colname="col2"> <p>Gli indirizzi e-mail cui vengono inviati gli avvisi. </p> <p>Esempio: <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server SMTP per errori, nome utente </td> 
   <td colname="col2"> <p>Nome utente per l'accesso al server SMTP. Questo parametro è facoltativo, a meno che non sia necessario effettuare il login per inviare la posta elettronica. </p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervallo di stato </td> 
   <td colname="col2"> <p>Frequenza (in secondi) con cui <span class="wintitle"> Report Server </span> genera e invia le informazioni sullo stato al server workbench dati per essere visualizzato in <span class="wintitle"> Dettagliato Stato </span>. </p> <p>Il valore predefinito è 120 secondi. Non è consigliabile impostare questo valore su un valore ridotto, ad esempio due minuti, perché l'esecuzione di una coda di reporting potrebbe richiedere ore. In tal caso, potete considerare un'impostazione da 600 a 1200 secondi. </p> <p>Per ulteriori informazioni sullo stato <span class="wintitle"> dettagliato </span>, consulta il capitolo Interfacce amministrative della Guida utente di <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Insight </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervallo aggiornamento </td> 
   <td colname="col2"> <p>Frequenza (in minuti) con la quale <span class="keyword"> Report Server </span> controlla tutti i profili elencati nel vettore Profili per i nuovi rapporti e avvisi. Il valore predefinito è 10 minuti. </p> <p>L’ora specificata viene divisa tra tutti i profili elencati. Ad esempio, se l’intervallo è impostato su 10 minuti e state monitorando due profili, ogni profilo viene monitorato per 5 minuti. Se un profilo viene monitorato quando un nuovo rapporto o un avviso modificato viene salvato nel profilo, il rapporto o l'avviso è immediatamente disponibile per la generazione. </p> <p>Se l' <span class="wintitle"> intervallo di aggiornamento </span> è configurato per monitorare più di un profilo, è importante che questa impostazione sia sufficientemente elevata per caricare tutti i profili entro il tempo configurato. Nei sistemi con molte dimensioni configurate, ad esempio, in cui potrebbero essere necessari alcuni minuti per recuperare la connessione dati iniziale con tutti i nomi degli elementi, questa impostazione deve essere sufficientemente lunga da consentire la sincronizzazione completa. In caso contrario, il sistema genera un errore di sincronizzazione del profilo. </p> </td> 
  </tr> 
 </tbody> 
</table>

