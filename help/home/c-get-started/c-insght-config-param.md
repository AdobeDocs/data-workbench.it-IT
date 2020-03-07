---
description: Impostare i parametri nel file Insight.cfg per specificare le impostazioni di connessione di rete e di configurazione del Workbench dati.
solution: Analytics
title: Parametri di configurazione
topic: Data workbench
uuid: 6e1248c1-3eae-44a3-8b19-f595d79e8d0d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Parametri di configurazione{#configuration-parameters}

Impostare i parametri nel file Insight.cfg per specificare le impostazioni di connessione di rete e di configurazione del Workbench dati.

L&#39;esempio seguente contiene solo i parametri inclusi nel [!DNL Insight.cfg] file per impostazione predefinita.

**Nuova vista Layout**

![](assets/config_tree_new_layout.png)

**Layout originale**

![](assets/cfg_Workstation_AddServer.png)

Alcuni dei parametri disponibili nel nuovo [!DNL Insight.cfg] file potrebbero non essere disponibili nella versione del [!DNL Insight.cfg] file. Se è necessario uno di questi parametri, è necessario aggiungerlo al [!DNL Insight.cfg] file utilizzando [!DNL Add Custom Key], facendo clic con il pulsante destro del mouse su un parametro, e quindi specificando il nome e il tipo. È inoltre possibile aggiungere parametri aprendo il [!DNL .cfg] file (che si trova nella directory di installazione di Workbench dati) tramite un editor di testo.

Di seguito è riportato un esempio di tutti i parametri disponibili per il [!DNL Insight.cfg] file che potete usare come modello per aggiungere voci di parametri:

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

La tabella seguente fornisce una descrizione dei parametri di [!DNL Insight.cfg] file disponibili in ordine alfabetico.

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
   <td colname="col2"> <p>Il nome host o l'indirizzo IP numerico del computer del server Workbench dati. </p> <p>Esempio: <span class="filepath"> vServer.mycompany.com o 192.168.1.90</span> </p> <p>Se <span class="wintitle"> Address</span> non è specificato, <span class="keyword"> il client</span> utilizza il nome comune specificato nel parametro Nome comune del server SSL quando Usa file indirizzo è impostato su false. </p> <p> <p>Nota: Se il parametro Use Address File (Usa file indirizzo) è impostato su true, il testo immesso nel parametro Address può essere rimosso dopo che <span class="keyword"> il primo profilo è stato aperto sul client</span>. Quindi, l'impostazione per il parametro Posizione di rete determina quali indirizzi del file Indirizzo del cluster vengono utilizzati per la connessione al server principale. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Set colori </p> </td> 
   <td colname="col2"> <p>Specifica il colore di sfondo dell'applicazione <span class="keyword"></span>client. Le opzioni sono le seguenti: </p> <p>0 = nero </p> <p>1 = bianco </p> <p>2 = monocromatico </p> <p>Il valore predefinito è 0, nero. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Livello online predefinito </p> </td> 
   <td colname="col2"> <p>Facoltativo. Consente di rendere l'istanza di Workbench dati funzionante per impostazione predefinita come streaming, offline o online ogni volta che viene aperta. Le opzioni sono Streaming, Online o Offline. La configurazione predefinita di Workbench dati è l'utilizzo non in linea. </p> <p> <p>Nota: Prima di decidere di lavorare online per impostazione predefinita, accertatevi di valutare i vantaggi e le conseguenze descritti in <a href="../../home/c-get-started/c-off-on.md#concept-cef8758ede044b18b3558376c5eb9f54"> Working Offline (Utilizzo offline) e Online</a>(Online). </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Font </p> </td> 
   <td colname="col2"> <p>Facoltativo. Vettoriale che elenca i font che <span class="keyword"> il client</span> deve utilizzare per il rendering dei caratteri unicode basati su UTF8. Il numero di font nell'elenco è illimitato. </p> <p>Il primo font deve sempre essere Lucida Sans Console. Se questo parametro non è incluso nel file <span class="filepath"> Insight.cfg</span> , Workbench dati utilizza solo la console Lucida Sans per visualizzare il testo. </p> <p> Workbench dati utilizza il primo font nell'elenco per eseguire il rendering di tutti i caratteri fino a quando non rileva un carattere di cui non è possibile eseguire il rendering. Utilizza il secondo font nell'elenco per eseguirne il rendering. Se tale carattere non esegue il rendering del carattere, Workbench dati utilizza il terzo carattere nell'elenco per eseguirne il rendering e così via, fino alla fine dell'elenco dei font. Se il font corretto non è elencato nel vettore, Workbench dati visualizza il valore esadecimale del carattere. </p> <p> <p>Nota:  Non modificare questo parametro mentre Workbench dati è in esecuzione. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> Impostazione gamma per la visualizzazione del workbench dati. Il valore predefinito è 1,6. Adobe non consiglia di modificare questo valore. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Licenze </p> </td> 
   <td colname="col2"> <p>Facoltativo. È necessario modificare i parametri nel vettore Licensing solo se si sta contattando il server delle licenze Adobe tramite un server proxy. </p> <p>Identificatore di sezione per i parametri che consentono al <span class="keyword"> client</span> di contattare Adobe License Server tramite un server proxy. Espandete il nodo Licensing e completate i seguenti parametri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indirizzo proxy </p> </td> 
   <td colname="col2"> <p>Facoltativo. Indirizzo del server proxy che il <span class="keyword"> client</span> deve utilizzare per accedere ad Adobe License Server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Porta proxy </p> </td> 
   <td colname="col2"> <p>Facoltativo. La porta del server proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome utente proxy </p> </td> 
   <td colname="col2"> <p>Facoltativo. Nome utente per il server proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Password proxy </p> </td> 
   <td colname="col2"> <p>Facoltativo. La password associata al Nome utente proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dimensione massima campione (MB) </p> </td> 
   <td colname="col2"> <p>Specifica la dimensione massima consentita nella cache dei dati utilizzata dal client <span class="keyword"></span> in esecuzione su un singolo computer. </p> <p>Mentre il parametro Byte di esempio nel file <span class="filepath"> Server.cfg</span> specifica la dimensione della cache dei dati per tutti <span class="keyword"> i client</span> che si connettono a un server Workbench dati (per impostazione predefinita, 250e6 byte), il parametro Dimensione campione massima consente di limitare ulteriormente la dimensione della cache dei dati per un particolare computer. Questo è utile quando il client è installato su un computer con capacità di archiviazione o di elaborazione limitata. </p> <p> <p>Nota: Questo parametro limita la dimensione di un esempio di dati locale interrogato localmente dal programma client. Al contrario, il file <span class="filepath"> cache.db</span> contiene i dati per ogni profilo a cui il client si collega, più i nomi degli elementi e le relative dimensioni. I nomi e le dimensioni di questi elementi nei file <span class="filepath"> cache.db</span> sono necessari per eseguire le query locali. Di conseguenza, non è possibile limitarne la dimensione se non riducendo il numero di elementi nel set di dati. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome </p> </td> 
   <td colname="col2">Facoltativo. Nome utilizzato <span class="keyword"> dal client</span> per identificare il <span class="keyword"> server</span>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Posizione di rete </p> </td> 
   <td colname="col2"> <p>Facoltativo. Percorso di rete utilizzato dal <span class="keyword"> client</span> per risolvere il nome comune del server Workbench dati in un indirizzo IP. Le posizioni di rete disponibili sono definite nel file dell'indirizzo sul server. Per ulteriori informazioni, vedere la Guida all'installazione e all'amministrazione dei prodotti <i>server</i>. </p> <p>Se non si specifica un percorso di rete, <span class="keyword"> il client</span> risolve i nomi comuni utilizzando il percorso di rete predefinito, "Insight". </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Porta </p> </td> 
   <td colname="col2"> <p>La porta alla quale <span class="keyword"> il client</span> invia le richieste. Questo numero di porta deve corrispondere alla porta su cui il server Workbench dati ascolta le richieste. Questa è in genere 443 per connessioni sicure. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indirizzo proxy </p> </td> 
   <td colname="col2"> <p>Se è necessario un server proxy per connettersi ai computer del server Workbench dati, è necessario completare almeno questo parametro e il parametro Porta proxy. Facoltativamente, potete completare i parametri Nome utente proxy e Password utente proxy. </p> <p>Indirizzo del server proxy che <span class="keyword"> il client</span> deve utilizzare per accedere al server Workbench dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Password proxy </p> </td> 
   <td colname="col2"> <p>Facoltativo. La password del server proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Porta proxy </p> </td> 
   <td colname="col2"> <p>La porta del server proxy. Il valore predefinito è 8080. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome utente proxy </p> </td> 
   <td colname="col2"> <p>Facoltativo. Nome utente per il server proxy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cerca </p> </td> 
   <td colname="col2"> <p>In <span class="filepath"> Insight.cfg</span> (o qualsiasi file <span class="filepath"> .cfg</span> ), potete cercare per nome chiave, tipo di chiave o valore per individuare rapidamente una voce, per rimuovere la necessità di scorrere file espansi e grandi per le informazioni nidificate. È possibile individuare nomi di dimensioni, nomi di server e così via. </p> <p>Digitare una frase di ricerca in questo campo per individuare i dati. A seconda dell’esito positivo di una corrispondenza, cambia il colore del campo. Le corrispondenze vengono evidenziate e le non corrispondenze risultano attenuate. In assenza di corrispondenze, lo sfondo del campo di ricerca diventa rosso. Quando si preme Invio, la struttura di configurazione si espande ogni punto in cui esiste una corrispondenza e si comprime laddove non esiste una corrispondenza. </p> <p>È inoltre possibile utilizzare espressioni regolari nel campo <span class="wintitle"> Cerca</span> . Ad esempio, puoi usare re: <span class="filepath"> *zip.*</span> per qualsiasi voce contenente la parola "zip". </p> <p>Per cancellare una ricerca, premere <span class="uicontrol"> Esc</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server </p> </td> 
   <td colname="col2"> <p>Intestazione vettoriale per le connessioni <span class="keyword"> client</span> - <span class="keyword"> server</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Certificato client SSL </p> </td> 
   <td colname="col2"> <p>Facoltativo, a meno che non disponiate di più certificati. Nome del file contenente il certificato digitale per questa copia di Workbench dati. Si tratta del file scaricato in Download e installazione del certificato digitale. </p> <p>Esempio: <span class="filepath"> Samantha Smith.pem</span> </p> <p>Se lasciate vuoto questo parametro, <span class="keyword"> il client</span> utilizza qualsiasi certificato presente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome comune server SSL </p> </td> 
   <td colname="col2"> <p>Nome comune del server Workbench dati (assegnato sul certificato digitale). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Icone della barra degli strumenti </p> </td> 
   <td colname="col2"> <p>False disattiva le icone nell'interfaccia utente della workstation e visualizza il testo nella barra degli strumenti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usa file di indirizzo </p> </td> 
   <td colname="col2"> <p>Specifica se eventuali impostazioni nel file dell'indirizzo sostituiscono l'impostazione del parametro Address. Le opzioni sono true o false. Se è impostato su true, le impostazioni nel file dell'indirizzo, se presente, sostituiscono l'impostazione del parametro Address. Il valore predefinito è true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Usa SSL </p> </td> 
   <td colname="col2">Specifica se SSL viene utilizzato per la comunicazione protetta tra il server Workbench dati e <span class="keyword"> il client</span>. Le opzioni sono true o false. Il valore predefinito è true. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mostra tutto </p> </td> 
   <td colname="col2"> <p>Facoltativo. Consente di scoprire temporaneamente tutte le metriche, le dimensioni e i filtri che sono stati nascosti utilizzando una delle seguenti funzionalità: 
     <ul id="ul_B40E28D9FDC0418BBFA9B0A37F4F6913"> 
      <li id="li_E51BAC99AAE949E5886F19557366453A">Impostazione [Exclusive] nei file <span class="filepath"> order.txt</span> </li> 
      <li id="li_E3D8222BC55D4CEB90BCCAE606711306">Opzione Nascondi nei file <span class="filepath"> order.txt</span> </li> 
      <li id="li_2ADE4EFC1F964D0A90B40CFB3D2766E8">Mostra i parametri nei file <span class="filepath"> .Metric</span>, <span class="filepath"> .dim</span>e <span class="filepath"> .filter</span> . </li> 
      <li id="li_BBCD248A8F33440092B52E407E300FCC">Parametro nascosto nel file <span class="filepath"> Transformation.cfg</span> . </li> 
     </ul> </p> <p>Per ulteriori informazioni su questi metodi, vedere <a href="../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999"> Nascondere una voce</a>di menu. </p> <p>Le opzioni sono true o false. L'impostazione predefinita è false. Modificate questo parametro su true per visualizzare temporaneamente metriche, dimensioni e filtri nascosti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sblocca </p> </td> 
   <td colname="col2"> <p>Facoltativo. Specifica se è consentito sbloccare le aree di lavoro bloccate. Le opzioni sono true e false. True consente di sbloccare qualsiasi area di lavoro bloccata, mentre false non lo è. Il valore predefinito è False. Per ulteriori informazioni sulle aree di lavoro bloccate, vedere <a href="../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e"> Sblocco di un’area di lavoro</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Software di aggiornamento </p> </td> 
   <td colname="col2"> <p>Facoltativo. Specifica se consentire <span class="keyword"> l'aggiornamento del software </span>client da parte del server Workbench dati. Le opzioni sono true o false. Il valore predefinito è true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cartella utente </p> </td> 
   <td colname="col2"> <p>Facoltativo. Specifica il nome e la posizione della cartella che contiene le copie locali di eventuali file di aree di lavoro, metriche, dimensioni o configurazione per ciascun profilo. L'impostazione predefinita è Utente\\, che specifica la cartella Utente all'interno della directory di installazione di Workbench dati. </p> <p>La modifica di questa impostazione è utile quando due utenti condividono lo stesso computer. Per ospitare entrambi gli utenti, potete specificare una cartella condivisa a cui entrambi gli utenti hanno accesso. </p> </td> 
  </tr> 
 </tbody> 
</table>

