---
description: Informazioni sui parametri Report Server.cfg.
title: Parametri del rapporto Server.cfg
uuid: 506f30f7-c8c6-4580-8423-7da8d00b0d57
exl-id: 339e4219-ff4d-4df6-b45a-7144927a843b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1685'
ht-degree: 1%

---

# Parametri del rapporto Server.cfg{#report-server-cfg-parameters}

Informazioni sui parametri Report Server.cfg.

L&#39;esempio [!DNL Report Server.cfg] mostrato in [Configurazione della connessione a Insight Server](../../../home/c-rpt-oview/c-inst-rpt/t-config-conn-ins-svr.md#task-a3ca949c43244782b658fb4437fd724c) contiene solo i parametri inclusi nel file [!DNL Report Server.cfg] per impostazione predefinita.

Se si contatta il server licenze Adobe tramite un server proxy, è necessario aggiungere il vettore Licensing e i relativi parametri al [!DNL Report Server.cfg]. Di seguito è riportato un esempio di questo vettore e dei relativi parametri che è possibile utilizzare per il vettore Licensing:

```
Licensing = serverInfo:  
Proxy Address = string: ProxyIPAddress 
Proxy Password = string: ProxyPassword 
Proxy Port = int: ProxyPort 
Proxy User Name = string: ProxyUserName 
```

La tabella seguente fornisce le descrizioni dei parametri del file [!DNL Report Server.cfg]:

<table id="table_9DA4A3124A9D444CBB4CBFF6FA279A42"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Estensione Excel </td> 
   <td colname="col2"> <p>Le estensioni Excel supportate includono: </p> <p>Estensione Excel = stringa: <span class="filepath"> .xlsx </span> </p> <p>Estensione Excel = stringa: <span class="filepath"> .xls </span> (impostazione predefinita) </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Font </td> 
   <td colname="col2"> <p>Facoltativo. Vector che elenca i font che <span class="keyword"> Report Server </span> devono utilizzare per il rendering dei caratteri speciali unicode basati su UTF8. Il numero di font nell'elenco è illimitato. </p> <p>Il primo carattere dovrebbe sempre essere Lucida Sans Console. Se questo parametro non è incluso nel file <span class="filepath"> Report Server.cfg </span>, <span class="keyword"> Report Server </span> utilizza solo la console Lucida Sans per visualizzare il testo. </p> <p> <span class="keyword"> Report Server  </span> utilizza il primo font dell’elenco per eseguire il rendering di tutti i caratteri fino a quando non rileva un carattere di cui non è in grado di eseguire il rendering. Quindi utilizza il secondo font nell’elenco per renderizzare quel carattere. Se il carattere non esegue il rendering del carattere, <span class="keyword"> Report Server </span> utilizza il terzo font dell'elenco per eseguire il rendering del carattere e così via, fino alla fine dell'elenco dei font. Se il font corretto non è elencato nel vettore, <span class="keyword"> Report Server </span> visualizza il valore esadecimale del carattere. </p> <p> <p>Nota:  Non apportare modifiche a questo parametro mentre <span class="keyword"> Report Server </span> è in esecuzione. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> <p> <span class="wintitle"> Impostazione gamma  </span> per l'uscita  <span class="filepath"> .png  </span> file. Il valore predefinito è 1.6. </p> <p> <p>Nota:  Adobe sconsiglia di modificare questo valore. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Licenze </td> 
   <td colname="col2"> <p>Facoltativo. È necessario modificare i parametri in questo vettore solo se si contatta il server licenze di Adobe tramite un server proxy. </p> <p>Identificatore di sezione per i parametri impostati per contattare il server licenze di Adobe tramite un server proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo proxy </td> 
   <td colname="col2"> L'indirizzo di un server proxy che <span class="keyword"> Report Server </span> deve utilizzare per accedere al server licenze Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Password proxy </td> 
   <td colname="col2"> Facoltativo. Password associata al <span class="wintitle"> nome utente proxy </span>. </td> 
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
   <td colname="col1"> Percorso di rete </td> 
   <td colname="col2"> Il percorso di rete utilizzato da <span class="keyword"> Report Server </span> per risolvere il nome comune del server in un indirizzo IP. Le posizioni di rete sono definite nel file dell’indirizzo che si trova nella directory Indirizzi sul computer server di Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server </td> 
   <td colname="col2"> <p>Identificatore di sezione per i parametri impostati per configurare quali computer server di Data Workbench <span class="keyword"> devono connettersi per generare rapporti. </span> Ciò include un numero che indica quanti elementi sono elencati in questo vettore. </p> <p>Per ogni server, aggiungi una voce serverInfo e completa i parametri in base alle esigenze. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo </td> 
   <td colname="col2"> Indirizzo IP del server di Data Workbench a cui <span class="keyword"> Report Server </span> deve connettersi per generare report. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome </td> 
   <td colname="col2"> Nome utilizzato internamente da <span class="keyword"> Report Server </span> per identificare il server di Data Workbench. Si tratta semplicemente di un’etichetta interna, in modo da poter utilizzare qualsiasi nome. Per coerenza, ti consigliamo di utilizzare il nome comune elencato nel certificato digitale del server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta </td> 
   <td colname="col2"> Porta attraverso la quale <span class="keyword"> Report Server </span> comunica con il server di Data Workbench. Per le connessioni sicure, questo valore è in genere 443. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Indirizzo proxy </td> 
   <td colname="col2"> Indirizzo di un server proxy che <span class="keyword"> Report Server </span> deve utilizzare per accedere al server di Data Workbench. Questo parametro è necessario solo quando è necessario un server proxy per connettersi ai computer server. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Password proxy </td> 
   <td colname="col2"> Password del server proxy. Questo parametro è necessario solo quando è necessario un server proxy per connettersi ai computer server di Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Porta proxy </td> 
   <td colname="col2"> La porta del server proxy. Il valore predefinito è 8080. Questo parametro è necessario solo quando è necessario un server proxy per connettersi ai computer server di Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome utente proxy </td> 
   <td colname="col2"> Nome utente del server proxy. Questo parametro è necessario solo quando è necessario un server proxy per connettersi ai computer server di Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Certificato client SSL </td> 
   <td colname="col2"> Nome del file di certificato SSL per il computer <span class="keyword"> Report Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome comune server SSL </td> 
   <td colname="col2"> <span class="wintitle"> Nome comune server  </span> elencato nel certificato digitale del server di Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Usa SSL </td> 
   <td colname="col2"> Indica se SSL viene utilizzato per la comunicazione sicura tra il server di Data Workbench e il server di rapporto <span class="keyword"> </span>. Le opzioni sono true o false. Il valore predefinito è vero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Limite di memoria dei risultati (KB) </td> 
   <td colname="col2"> <p>Quantità di memoria (in KB) che si desidera rendere disponibile per report e avvisi. Il valore predefinito è 50000. </p> <p>Durante l'esecuzione dei rapporti, <span class="keyword"> Report Server </span> controlla prima questo valore, quindi controlla il valore nel parametro Maximum Slice Size (Dimensione massima sezione). Ad esempio, se si imposta questo parametro su 50.000 e la dimensione massima della sezione su 50, <span class="keyword"> Report Server </span> esegue solo 50 aree di lavoro alla volta, anche se è disponibile spazio per eseguire più aree di lavoro. </p> <p> <p>Nota:  Questo limite non deve mai superare il valore impostato nel parametro Limite di memoria query del server di Data Workbench e, idealmente, deve essere impostato un po' più in basso rispetto al <span class="wintitle"> Limite di memoria query </span> per fornire un margine di manovra ad altri utenti che potrebbero eseguire i rapporti contemporaneamente. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Dimensione massima sezione </td> 
   <td colname="col2"> Il numero massimo di aree di lavoro del report che <span class="keyword"> Report Server </span> può essere eseguito contemporaneamente. Il valore predefinito è 50. Per ulteriori informazioni su come <span class="keyword"> Report Server </span> utilizza questa impostazione, consulta la descrizione del parametro <span class="wintitle"> Result Memory Limit (KB) </span> . </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Aggiorna software </td> 
   <td colname="col2"> <p>Indica se consentire l’aggiornamento del software <span class="keyword"> del server di rapporto </span> da parte del server di Data Workbench. Le opzioni sono true o false. Il valore predefinito è vero. </p> <p>Di seguito è riportato un esempio di questo parametro che è possibile utilizzare un modello: </p> <p> <code> Update&amp;nbsp;Software&amp;nbsp;=&amp;nbsp;bool:&amp;nbsp;false </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Utilizzare il rendering hardware OpenGL </td> 
   <td colname="col2"> <p>Controlla se <span class="keyword"> Report Server </span> utilizza il rendering hardware (come la scheda grafica del computer) per produrre l'output del report. Le opzioni sono true o false. Il valore predefinito è vero. </p> <p>Questo parametro deve essere impostato su false solo quando si verificano problemi con la scheda grafica. Se impostato su false, <span class="keyword"> Report Server </span> non tenta di utilizzare il rendering hardware e utilizza il rendering software per impostazione predefinita. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Generazione di rapporti </td> 
   <td colname="col2"> Identificatore di sezione per i parametri impostati per configurare il reporting. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervallo messaggi di completamento </td> 
   <td colname="col2"> <p>Frequenza (in secondi) con cui <span class="keyword"> Report Server </span> stampa i messaggi di stato di completamento quando le query vengono eseguite durante la generazione di report o avvisi. Il valore predefinito è 120 secondi. </p> <p>Esempio: Le query Workspace sono completate al 62,145672%. </p> <p>I messaggi di completamento vengono scritti nel <span class="filepath"> reportserver.log </span> e vengono sincronizzati nel server. Questa impostazione controlla i file <span class="filepath"> status.txt </span> inviati avanti e indietro per ogni set di rapporti, in modo che la percentuale di completamento possa essere visualizzata con le miniature. I messaggi vengono inviati ogni volta che un set di rapporti viene completato o quando viene raggiunto l’intervallo, a seconda di quale dei due eventi si verifica per primo. L’impostazione di questo valore più alto non influisce sulla frequenza con cui vengono visualizzati i rapporti generati nell’interfaccia client dalle miniature, ma influisce sul numero di messaggi intermedi visualizzati. Se si specifica un valore basso, il sistema può dedicare molto tempo alla sincronizzazione dei dati, perché i dati vengono sincronizzati dal server <span class="keyword"> Report Server </span> al profilo, in tutte le DPU e a tutti i client connessi ogni volta che cambia il messaggio <span class="filepath"> status.txt </span>. </p> <p>Il sistema invia sempre un file <span class="filepath"> status.txt </span> al completamento di un set di rapporti, indipendentemente dall'impostazione di questo parametro di configurazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Profili </td> 
   <td colname="col2"> <p>Numero che indica quanti elementi sono elencati in questo vettore. Per ogni profilo per il quale devono essere creati i rapporti, aggiungi una voce <span class="wintitle"> ReportProfile </span> nel vettore Profiles e completa i parametri Server e Profilo . </p> <p> <span class="wintitle"> Server  </span> - Il nome che  <span class="keyword"> Report Server  </span> utilizza internamente per identificare il server di Data Workbench. Questo nome deve essere il nome comune del server elencato nel certificato SSL del server di Data Workbench. </p> <p> <span class="wintitle"> Profilo  </span> - Nome del profilo per il quale devono essere creati i rapporti. Questo nome deve corrispondere al profilo denominato nel computer server di Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server SMTP per errori </td> 
   <td colname="col2"> <p>Indirizzo del server SMTP da cui si desidera inviare gli errori <span class="wintitle"> del server di rapporto </span> tramite e-mail. </p> <p>Esempio: <span class="filepath"> mail.mycompany.com </span> </p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Password errore server SMTP </td> 
   <td colname="col2"> <p>Password per l'accesso al server SMTP. Questo parametro è facoltativo a meno che non sia necessario l’accesso per inviare la posta. </p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server SMTP per gli errori inviati da </td> 
   <td colname="col2"> L'indirizzo e-mail da cui si desidera inviare gli errori <span class="wintitle"> Report Server </span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Server SMTP per gli errori inviati a </td> 
   <td colname="col2"> <p>Gli indirizzi e-mail a cui vengono inviati gli avvisi. </p> <p>Esempio: <span class="filepath"> adm1@company.com,adm2@company.com </span> </p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Nome utente del server SMTP per gli errori </td> 
   <td colname="col2"> <p>Nome utente per l'accesso al server SMTP. Questo parametro è facoltativo a meno che non sia necessario l’accesso per inviare la posta. </p> <p>Per utilizzare le funzionalità descritte è necessario un server SMTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervallo di stato </td> 
   <td colname="col2"> <p>Frequenza (in secondi) con cui <span class="wintitle"> Report Server </span> genera e invia informazioni sullo stato al server di Data Workbench da visualizzare in <span class="wintitle"> Stato dettagliato </span>. </p> <p>Il valore predefinito è 120 secondi. Non è consigliabile impostare questo valore su un valore piccolo, ad esempio due minuti, perché l’esecuzione di una coda di reporting può richiedere ore. In tal caso, potresti considerare un'impostazione da 600 a 1200 secondi. </p> <p>Per ulteriori informazioni su <span class="wintitle"> Stato dettagliato </span>, vedere il capitolo relativo alle interfacce amministrative della <a href="https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-admin-intrf.html" format="http" scope="external"> Guida utente di Insight </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Intervallo di aggiornamento </td> 
   <td colname="col2"> <p>Frequenza (in minuti) con cui <span class="keyword"> Report Server </span> controlla tutti i profili elencati nel vettore Profiles per i nuovi report e avvisi. Il valore predefinito è 10 minuti. </p> <p>L’ora specificata è divisa tra tutti i profili elencati. Ad esempio, se l’intervallo è impostato su 10 minuti e stai monitorando due profili, ogni profilo viene monitorato per 5 minuti. Se un profilo viene monitorato quando un report o un avviso nuovo o modificato viene salvato nel profilo, il report o l'avviso è immediatamente disponibile per la generazione. </p> <p>Se l’ <span class="wintitle"> intervallo di aggiornamento </span> è configurato per monitorare più di un profilo, è importante che questa impostazione sia sufficientemente elevata per caricare tutti i profili entro il tempo configurato. Nei sistemi con molte dimensioni di grandi dimensioni configurate, ad esempio, in cui potrebbero essere necessari diversi minuti per recuperare la connessione dati iniziale con tutti i nomi degli elementi, questa impostazione deve essere sufficientemente lunga da consentire la sincronizzazione completa. In caso contrario, il sistema genera un errore di sincronizzazione del profilo. </p> </td> 
  </tr> 
 </tbody> 
</table>
