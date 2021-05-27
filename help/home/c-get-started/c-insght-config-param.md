---
description: Imposta i parametri nel file Insight.cfg per specificare la connessione di rete e Data Workbench le impostazioni di configurazione.
title: Parametri di configurazione
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
exl-id: c92fc79f-452d-4839-840a-a3ea9e8754c4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1519'
ht-degree: 2%

---

# Parametri di configurazione{#configuration-parameters}

Imposta i parametri nel file Insight.cfg per specificare la connessione di rete e Data Workbench le impostazioni di configurazione.

L&#39;esempio seguente contiene solo i parametri inclusi nel file [!DNL Insight.cfg] per impostazione predefinita.

**Nuova vista Layout**

![](assets/config_tree_new_layout.png)

**Vista Layout originale**

![](assets/cfg_Workstation_AddServer.png)

Alcuni dei parametri disponibili nel nuovo file [!DNL Insight.cfg] potrebbero non essere disponibili nella versione del file [!DNL Insight.cfg]. Se è necessario uno di questi parametri, è necessario aggiungerlo al file [!DNL Insight.cfg] utilizzando [!DNL Add Custom Key], facendo clic con il pulsante destro del mouse su un parametro e specificando il nome e il tipo. Puoi anche aggiungere parametri aprendo il file [!DNL .cfg] (che si trova nella directory di installazione di Data Workbench) tramite un editor di testo.

Di seguito è riportato un esempio di tutti i parametri disponibili per il file [!DNL Insight.cfg] che è possibile utilizzare come modello per aggiungere voci di parametri:

```
Licensing = serverInfo:
  Proxy Address = string: 
  Proxy Port = int: 8080
  Proxy User Name = string: 
  Proxy Password = string: 
Servers = vector: 1 items
  0 = serverInfo: 
    Address = string: VS02
    Name = string: Insight Server
    Port = int: 443
    Proxy Address = string: 
    Proxy Password = string: 
    Proxy Port = int: 8080
    Proxy User Name = string: 
    SSL Client Certificate = string: Named User.pem
    SSL Server Common Name = string: VS02
    Use Address File = bool: false
    Use SSL = bool: true
Color Set = int: 0
Default to Online = bool: false
Fonts = vector: 0 items
Gamma = float: 1.6
Maximum Sample Size (MB) = double: 0
Network Location = string: 
Unhide All = bool: false
Unlock = bool: false
Update Software = bool: true
User Folder = string: User\\
Toolbar Icons = bool: false
```

La tabella seguente fornisce descrizioni dei parametri del file [!DNL Insight.cfg] disponibili in ordine alfabetico.

<table id="table_4465713A08B649E280A3B4840E829518"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Indirizzo </p> </td> 
   <td colname="col2"> <p>Il nome host o l'indirizzo IP numerico del computer server di Data Workbench. </p> <p>Esempio: <span class="filepath"> vsServer.mycompany.com o 192.168.1.90</span> </p> <p>Se <span class="wintitle"> Address</span> non è specificato, <span class="keyword"> il client</span> utilizza il nome comune specificato nel parametro Nome comune del server SSL quando Use Address File è impostato su false. </p> <p> <p>Nota: Se il parametro Use Address File è impostato su true, il testo inserito nel parametro Address può essere rimosso dopo l'apertura del primo profilo su <span class="keyword"> client</span>. Quindi, l'impostazione per il parametro Posizione di rete determina quali indirizzi del file Indirizzo del cluster vengono utilizzati per la connessione al server master. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Set di colori </p> </td> 
   <td colname="col2"> <p>Specifica il colore di sfondo dell'applicazione client <span class="keyword"></span>. Le opzioni sono le seguenti: </p> <p>0 = nero </p> <p>1 = bianco </p> <p>2 = monocromatico </p> <p>Il valore predefinito è 0, nero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Livello online predefinito </p> </td> 
   <td colname="col2"> <p>Facoltativo. Consente di far funzionare l’istanza di Data Workbench per impostazione predefinita come streaming, offline o online ogni volta che viene aperta. Le opzioni sono Streaming, Online o Offline. La configurazione predefinita per Data Workbench è il funzionamento offline. </p> <p> <p>Nota: Prima di decidere di lavorare online per impostazione predefinita, assicurati di valutare i vantaggi e le conseguenze descritti in <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Lavorare offline e online</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Font </p> </td> 
   <td colname="col2"> <p>Facoltativo. Vector che elenca i font che <span class="keyword"> il client</span> deve utilizzare per il rendering dei caratteri speciali unicode basati su UTF8. Il numero di font nell'elenco è illimitato. </p> <p>Il primo carattere dovrebbe sempre essere Lucida Sans Console. Se questo parametro non è incluso nel file <span class="filepath"> Insight.cfg</span>, Data Workbench utilizza solo la console Lucida Sans per visualizzare il testo. </p> <p> La Data Workbench utilizza il primo font dell’elenco per eseguire il rendering di tutti i caratteri finché non rileva un carattere di cui non è in grado di eseguire il rendering. Utilizza il secondo font dell’elenco per eseguire il rendering del carattere. Se il carattere non esegue il rendering del carattere, la Data Workbench utilizza il terzo font nell’elenco per eseguire il rendering del carattere e così via, fino alla fine dell’elenco dei font. Se il font corretto non è elencato nel vettore, in Data Workbench viene visualizzato il valore esadecimale del carattere. </p> <p> <p>Nota:  Non modificare questo parametro mentre Data Workbench è in esecuzione. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Impostazione del gamma per il display a Data Workbench. Il valore predefinito è 1.6. Ad Adobe, non è consigliabile modificare questo valore. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Licenze </p> </td> 
   <td colname="col2"> <p>Facoltativo. È necessario modificare i parametri nel vettore Licensing solo se si sta contattando il server licenze di Adobe tramite un server proxy. </p> <p>Identificatore di sezione per i parametri che consentono al <span class="keyword"> client</span> di contattare il server licenze Adobe tramite un server proxy. Espandi il nodo Gestione licenze e completa i seguenti parametri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indirizzo proxy </p> </td> 
   <td colname="col2"> <p>Facoltativo. Indirizzo del server proxy che <span class="keyword"> client</span> deve utilizzare per accedere al server licenze Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Porta proxy </p> </td> 
   <td colname="col2"> <p>Facoltativo. La porta del server proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome utente proxy </p> </td> 
   <td colname="col2"> <p>Facoltativo. Nome utente del server proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Password proxy </p> </td> 
   <td colname="col2"> <p>Facoltativo. Password associata al nome utente proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensione massima del campione (MB) </p> </td> 
   <td colname="col2"> <p>Specifica la dimensione massima consentita nella cache dati utilizzata da <span class="keyword"> il client</span> in esecuzione su un singolo computer. </p> <p>Mentre il parametro Sample Bytes nel file <span class="filepath"> Server.cfg</span> specifica la dimensione della cache dei dati per tutti i <span class="keyword"> client</span> che si connettono a un server Data Workbench (250e6 byte per impostazione predefinita), il parametro Maximum Sample Size consente di limitare ulteriormente la dimensione della cache dei dati per un determinato computer. Questo è utile quando il client è installato su un computer con una potenza di archiviazione o di elaborazione limitata. </p> <p> <p>Nota: Questo parametro limita le dimensioni di un esempio di dati locale interrogato localmente dal programma client. Al contrario, il file <span class="filepath"> cache.db</span> contiene i dati per ciascun profilo a cui il client si connette, oltre ai nomi degli elementi e alle relative dimensioni. Per eseguire le query locali, sono necessari i nomi e le dimensioni degli elementi nei file <span class="filepath"> cache.db</span> . Di conseguenza, non vi è modo di limitarne la dimensione se non la riduzione del numero di elementi nel set di dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome </p> </td> 
   <td colname="col2">Facoltativo. Nome utilizzato da <span class="keyword"> client</span> per identificare il server <span class="keyword"></span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Percorso di rete </p> </td> 
   <td colname="col2"> <p>Facoltativo. Il percorso di rete utilizzato da <span class="keyword"> client</span> per risolvere il nome comune del server di Data Workbench in un indirizzo IP. Le posizioni di rete disponibili sono definite nel file dell'indirizzo sul server. Per ulteriori informazioni, vedere la <i>Guida all'installazione e all'amministrazione dei prodotti server</i>. </p> <p>Se non si specifica un percorso di rete, <span class="keyword"> client</span> risolve i nomi comuni utilizzando il percorso di rete predefinito, "Insight". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Porta </p> </td> 
   <td colname="col2"> <p>La porta a cui <span class="keyword"> il client</span> invia le richieste. Questo numero di porta deve corrispondere alla porta su cui il server Data Workbench sta ascoltando le richieste. Questo è di solito 443 per connessioni sicure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indirizzo proxy </p> </td> 
   <td colname="col2"> <p>Se è necessario un server proxy per connettersi ai computer del server Data Workbench, è necessario completare almeno questo parametro e il parametro della porta proxy. Facoltativamente, puoi completare i parametri Nome utente proxy e Password utente proxy. </p> <p>L'indirizzo del server proxy che <span class="keyword"> il client</span> deve utilizzare per accedere al server Data Workbench. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Password proxy </p> </td> 
   <td colname="col2"> <p>Facoltativo. Password del server proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Porta proxy </p> </td> 
   <td colname="col2"> <p>La porta del server proxy. Il valore predefinito è 8080. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome utente proxy </p> </td> 
   <td colname="col2"> <p>Facoltativo. Nome utente del server proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cerca </p> </td> 
   <td colname="col2"> <p>In <span class="filepath"> Insight.cfg</span> (o in qualsiasi file <span class="filepath"> .cfg</span>), puoi cercare per nome chiave, tipo di chiave o valore per individuare rapidamente una voce, per rimuovere la necessità di scorrere file espansi di grandi dimensioni per informazioni nidificate. È possibile individuare nomi di dimensioni, nomi di server e così via. </p> <p>Digita una frase di ricerca in questo campo per individuare i dati. A seconda del successo di una corrispondenza, cambia il colore del campo. Le corrispondenze vengono evidenziate e le non corrispondenze sono disattivate. In assenza di corrispondenze, lo sfondo del campo di ricerca diventa rosso. Quando si preme Invio, l'albero di configurazione espande ogni punto in cui c'è una corrispondenza e comprime dove non c'è una corrispondenza. </p> <p>Puoi anche utilizzare espressioni regolari nel campo <span class="wintitle"> Search</span> . Ad esempio, puoi utilizzare i seguenti: <span class="filepath"> *zip.*</span> per qualsiasi voce contenente la parola "zip". </p> <p>Per cancellare una ricerca, premere <span class="uicontrol"> Escape</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server </p> </td> 
   <td colname="col2"> <p>Intestazione del vettore per le connessioni <span class="keyword"> client</span> a <span class="keyword"> server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Certificato client SSL </p> </td> 
   <td colname="col2"> <p>Facoltativo, a meno che non si disponga di più certificati. Nome del file contenente il certificato digitale per questa copia della Data Workbench. Questo è il file scaricato in Download e installazione del certificato digitale. </p> <p>Esempio: <span class="filepath"> Samantha Smith.pem</span> </p> <p>Se lasci vuoto questo parametro, <span class="keyword"> il client</span> utilizza qualsiasi certificato presente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome comune server SSL </p> </td> 
   <td colname="col2"> <p>Nome comune del server di Data Workbench (assegnato sul certificato digitale). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Icone della barra degli strumenti </p> </td> 
   <td colname="col2"> <p>False disattiva le icone nell’interfaccia utente della workstation e visualizza il testo nella barra degli strumenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usa file di indirizzi </p> </td> 
   <td colname="col2"> <p>Specifica se eventuali impostazioni nel file indirizzo sostituiscono l'impostazione del parametro Address. Le opzioni sono true o false. Se è impostato su true, le impostazioni nel file dell'indirizzo, se presenti, sostituiscono l'impostazione del parametro Address. Il valore predefinito è vero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usa SSL </p> </td> 
   <td colname="col2">Specifica se SSL viene utilizzato per la comunicazione sicura tra il server di Data Workbench e <span class="keyword"> il client</span>. Le opzioni sono true o false. Il valore predefinito è vero. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mostra tutto </p> </td> 
   <td colname="col2"> <p>Facoltativo. Consente di visualizzare temporaneamente tutte le metriche, le dimensioni e i filtri nascosti utilizzando una delle funzionalità seguenti: 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">Impostazione di [Esclusivo] nei file <span class="filepath"> order.txt</span> </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">Opzione Nascondi nei file <span class="filepath"> order.txt</span> </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">Mostra il parametro nei file <span class="filepath"> .metric</span>, <span class="filepath"> .dim</span> e <span class="filepath"> .filter</span>. </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">Parametro nascosto nel file <span class="filepath"> Transformation.cfg</span> . </li> 
     </ul> </p> <p>Per ulteriori informazioni su questi metodi, vedere <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> Nascondere una voce di menu</a>. </p> <p>Le opzioni sono true o false. L'impostazione predefinita è false. Modifica questo parametro in true per visualizzare temporaneamente metriche, dimensioni e filtri nascosti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sblocca </p> </td> 
   <td colname="col2"> <p>Facoltativo. Specifica se è consentito sbloccare le aree di lavoro bloccate. Le opzioni sono true e false. True consente di sbloccare qualsiasi area di lavoro bloccata, mentre false non lo consente. Il valore predefinito è False. Per ulteriori informazioni sulle aree di lavoro bloccate, vedere <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> Sblocco di un'area di lavoro</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aggiorna software </p> </td> 
   <td colname="col2"> <p>Facoltativo. Specifica se consentire l'aggiornamento del <span class="keyword"> software client </span>dal server Data Workbench. Le opzioni sono true o false. Il valore predefinito è vero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cartella utente </p> </td> 
   <td colname="col2"> <p>Facoltativo. Specifica il nome e il percorso della cartella contenente le copie locali di eventuali aree di lavoro, metriche, dimensioni o file di configurazione per ciascun profilo. L'impostazione predefinita è Utente\\, che specifica la cartella Utente all'interno della directory di installazione di Data Workbench. </p> <p>La modifica di questa impostazione è utile quando due utenti condividono lo stesso computer. Per accogliere entrambi gli utenti, puoi specificare una cartella condivisa a cui entrambi gli utenti possono accedere. </p> </td> 
  </tr> 
 </tbody> 
</table>
