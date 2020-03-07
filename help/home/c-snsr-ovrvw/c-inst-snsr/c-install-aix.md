---
description: Istruzioni su come installare e configurare il server IBM HTTP su IBM AIX 5.1 o versione successiva in esecuzione in Microsoft Windows Server 2000 o versione successiva.
title: IBM HTTP Server su AIX 5.1 o versione successiva
uuid: d4a37ab2-514a-4afb-905b-420159c4ef0a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# IBM HTTP Server su AIX 5.1 o versione successiva{#ibm-http-server-on-aix-or-later}

Istruzioni su come installare e configurare il server IBM HTTP su IBM AIX 5.1 o versione successiva in esecuzione in Microsoft Windows Server 2000 o versione successiva.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponete già del file di installazione Sensor per il vostro particolare server Web, scaricatelo (o ottenetelo dal rappresentante Adobe) prima di iniziare le seguenti procedure.

Per installare e configurare Sensor, devi eseguire i seguenti passaggi di alto livello:

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

Sul server IBM AIX, crea una directory in cui installare i file del programma Sensor. Tenere presente che la coda del disco risiede anche in questa directory, quindi assicurarsi che il dispositivo scelto disponga di spazio sufficiente per contenere una coda delle dimensioni necessarie.

1. Accedete come utente principale o come utente con autorizzazione principale.
1. Decomprimete e decomprimete il file di installazione utilizzando il seguente comando:

   ```
   tar -zxf installationFilename
   ```

1. Copiare i file di programma non imballati nelle directory indicate nella tabella seguente:

<table id="table_ABFF5F92271B4F3CB0AC68DAB6A5709F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Target Directory </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> mod_visual_sciences.so </td> 
   <td colname="col2"> Modulo di caricamento del raccoglitore. </td> 
   <td colname="col3"> <i> IBMHttpServer/module</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Il programma del trasmettitore. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>—OR—</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Il file di configurazione Sensor. </td> 
   <td colname="col3"> <i>/etc</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificato utilizzato per convalidare il certificato digitale presentato da Insight Server durante il processo di connessione </td> 
   <td colname="col3"> <i>/usr/local/visual_sciences</i> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Il pacchetto di installazione contiene un foglio di calcolo denominato TestExperiment.xls. Questo foglio di calcolo è uno strumento che gli architetti usano per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se potete scegliere di farlo). Potreste desiderare, invece, copiare il file in una posizione in cui gli architetti possano accedervi o semplicemente estrarre il file dal pacchetto di installazione in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati di Insight.

**Autorizzazioni sui file del programma**

>[!NOTE]
>
>Autorizzazioni errate sui file del programma causano la maggior parte dei problemi incontrati durante l&#39;installazione del sensore. Accertatevi di impostare le autorizzazioni esattamente come indicato in questa sezione.
>
>Per impostazione predefinita, i file di programma nel file tar hanno le seguenti autorizzazioni. A seconda della configurazione del sistema, queste impostazioni potrebbero essere modificate (non mascherate) al momento dell’estrazione dei file. Per ripristinare le autorizzazioni alle impostazioni predefinite consigliate, utilizzate i comandi chmod riportati di seguito. Verificate che le directory in cui avete installato i file consentano almeno questo livello di accesso.

<table id="table_F4A46DBDE0874133B616235C32B6D9F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File </th> 
   <th colname="col2" class="entry"> Autorizzazioni predefinite </th> 
   <th colname="col3" class="entry"> chmod, comando </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> libvisual_sciences.so </td> 
   <td colname="col2"> rwx —x —x </td> 
   <td colname="col3"> <p>chmod 711 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> J2EECollector.jar </td> 
   <td colname="col2"> rw- rw- r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd </td> 
   <td colname="col2"> rwx —x —x </td> 
   <td colname="col3"> chmod 711 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> rw- rw- r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> rw- rw- r— </td> 
   <td colname="col3"> chmod 664 </td> 
  </tr> 
 </tbody> 
</table>

## Modificare il file di configurazione Sensor {#section-de0eb4a646394b61abb6cd5a2b706de0}

Il [!DNL txlogd.conf] file contiene i parametri di configurazione per Sensor.

È necessario modificare questo file per specificare, tra le altre cose, le dimensioni e la posizione del file della coda del disco, l&#39;indirizzo del server di Insight e l&#39;ID che verrà allegato ai dati dell&#39;evento prodotti da questo sensore.

Il file di configurazione contiene i parametri obbligatori e i parametri facoltativi.

* **I parametri** richiesti sono impostazioni che dovete specificare quando installate Sensor. Senza queste impostazioni, il sensore non viene eseguito correttamente.
* **I parametri** facoltativi sono impostazioni predefinite per valori predefiniti (che è possibile modificare) o per abilitare funzioni facoltative.

**Per modificare il file di configurazione Sensor**

* Aprite il [!DNL /etc/txlogd.conf] file in un editor di testo e impostate i parametri richiesti, nonché eventuali parametri opzionali desiderati.
* Salvate e chiudete il file.

**Per modificare il file di configurazione Sensor**

1. Aprite il [!DNL /etc/txlogd.conf] file in un editor di testo e impostate i parametri richiesti, nonché eventuali parametri opzionali desiderati.
1. Salvate e chiudete il file.

## Avviare il trasmettitore e creare la coda del disco {#section-55630de65f264274aefd771da2002852}

Dopo aver configurato il file txlogd.conf, potete avviare il programma di trasmettitore, registrarlo come servizio Windows e creare la coda del disco.

1. Se la directory in cui risiede la coda del disco non esiste già, crearla. Verificate che la directory fornisca sia il modulo di raccolta che il programma di trasmettitore con accesso in lettura/scrittura al file.

   Per ulteriori informazioni sulle autorizzazioni richieste dai file della coda del disco, vedere Autorizzazioni per i file UNIX Sensor.
1. Sul computer in cui è installato Sensor, eseguire il comando seguente per avviare il trasmettitore:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * L&#39;opzione &quot;i&quot; di questo comando avvia il trasmettitore in &quot;modalità interattiva&quot;. Questa modalità visualizza i messaggi del trasmettitore sullo schermo e consente di interagire con il trasmettitore utilizzando i comandi della tastiera.
   * L&#39;opzione &quot;c&quot; indirizza il trasmettitore a creare la coda del disco.
   * L&#39;opzione &quot;f&quot; specifica la posizione del file di configurazione.
   Per ulteriori informazioni sulle opzioni che potete utilizzare quando avviate il trasmettitore, consultate Opzioni della riga di comando del trasmettitore sensore.

1. Verificate che il trasmettitore abbia creato la coda del disco nella posizione specificata nel parametro QueueFile e nella dimensione specificata nel parametro QueueSize.
1. Se la coda non è stata creata correttamente, digitate Ctrl+C per terminare il trasmettitore, quindi eseguite le seguenti operazioni:

   1. Esaminate il file txtlogd.conf e verificate che i parametri QueueFile e QueueSize siano impostati correttamente.
   1. Verificare che il dispositivo a cui è assegnata la coda di dischi sia operativo e che disponga di spazio sufficiente per contenere un file delle dimensioni specificate nel parametro QueueSize.
   1. Effettuare le correzioni necessarie e ripetere la procedura.

## Aggiungere l&#39;agente di raccolta all&#39;applicazione Web {#section-c5b83ae4ebce430aa764f951e849b333}

Per i server WebSphere, il raccoglitore funziona come filtro nel contenitore servlet.

Per aggiungere l&#39;agente di raccolta all&#39;app Web, aprite il file web.xml per il server Web i cui eventi vengono acquisiti da Sensor.

Se Sensor sta acquisendo dati per più server Web sul computer server, è necessario eseguire la procedura seguente per ciascun server Web.

1. Utilizzando un editor di testo, aprite il file httpd.conf per il server Web i cui eventi Sensor acquisiscono.
1. Aggiungete i seguenti `<filter>` elementi e `<filter-mapping>` elementi al file descrittore. Se non avete installato txlogd.conf nella directory /etc, dovete immettere il percorso corretto per questo file nell&#39; `<param-value>` elemento .

   ```
   <filter> 
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>C:/VisualSensor/txlogd.conf</param-value> 
     <description></description> 
     </init-param> 
   </filter> 
   
   <filter-mapping> 
     <filter-name>VSCollectorFilter</filter-name> 
     <url-pattern>/*</url-pattern> 
   </filter-mapping>
   ```

   >[!NOTE]
   >
   >Queste righe sono con distinzione tra maiuscole e minuscole. Digitate esattamente come appaiono sopra.

1. Riavviate l’applicazione Web. Il raccoglitore viene caricato con l&#39;applicazione e inizierà a raccogliere i dati dell&#39;evento e a scriverli nella coda del disco.

## Dichiarare la posizione del Collector e dei file oggetto condivisi {#section-b9c298fa645f4670b2503647d967846f}

Modificate lo script di avvio di Webfers per dichiarare la posizione dei file J2EECollector.jar e libVisual_sciences.so.

1. Aprite il file setupCmdLine.sh nella directory Webfers /bin.
1. Dopo la riga che definisce la variabile $WAS_CLASSPATH, aggiungere la riga seguente:

   ```
   WAS_CLASSPATH="$WAS_CLASSPATH":"$WAS_HOME"/lib/J2EECollector.jar
   ```

1. Dopo il blocco case che definisce la variabile $WAS_LIBPATH, aggiungere la riga seguente:

   ```
   WAS_LIBPATH="$WAS_LIBPATH":/usr/local/visual_sciences
   ```

1. Salvate il file setupCmdLine.sh.

## Prova del sensore {#section-0dae181ef8884f10a57f6cfda8500969}

Verificate che il raccoglitore raccolga i dati dell&#39;evento e che il trasmettitore li trasmetta al server di insight di destinazione.

>[!NOTE]
>
>Per verificare che il trasmettitore possa inviare correttamente i dati dell&#39;evento al server di Insight, accertatevi che il server di Insight di destinazione sia installato ed in esecuzione prima di iniziare il test seguente.

1. Se il trasmettitore non è già in esecuzione, riavviarlo utilizzando il seguente comando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Aprite un browser (su qualsiasi computer) e richiedete una pagina dal server Web su cui è in esecuzione Sensor (accertatevi di selezionare una pagina che il sensore sta monitorando).
1. Dopo aver inviato la richiesta, controllate la console del trasmettitore per i messaggi che indicano l&#39;invio dei dati dell&#39;evento al server di visualizzazione di destinazione.
1. Se Sensor non trasmette correttamente i dati, verificare che:

   * Il server di destinazione Insight è in esecuzione.
   * I parametri ServerAddress e ServerPort sono impostati correttamente in txtlogd.conf. Se è stato specificato ServerAddress utilizzando un nome server, provare a utilizzare il relativo indirizzo IP numerico.
   * Il valore del parametro CertName corrisponde esattamente al nome comune che viene visualizzato sul certificato digitale del server Insight di destinazione.

## Aggiungere il trasmettitore allo script di avvio del sistema {#section-19a38f27c9f44adf88f8910f5ed483a3}

Informazioni sul caricamento automatico del trasmettitore nello script di avvio del sistema.

Per fare in modo che il trasmettitore si carichi automaticamente al riavvio del server Web, aggiungere il seguente comando (che avvia il trasmettitore) allo script di avvio del sistema:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Questo comando avvia il trasmettitore come un demone. I messaggi di funzionamento e di errore generati dal trasmettitore vengono scritti in syslog.

## Acquisizione di dati aggiuntivi {#section-bb1c2bccba9b4bc0b52abdbb4f9d42d7}

I sensori per tutte le piattaforme possono raccogliere qualsiasi dato disponibile nelle intestazioni di richiesta e risposta HTTP.

I sensori per la piattaforma J2EE forniscono un meccanismo per la raccolta di dati non disponibili su altre piattaforme. Il raccoglitore per la piattaforma J2EE (raccoglitore J2EE) si trova sul livello dell&#39;applicazione, che consente di raccogliere dati sensibili che sono disponibili solo per l&#39;applicazione e non devono essere esposti tramite tag di pagina o nelle intestazioni.

>[!NOTE]
>
>Mentre i tag pagina e la modifica dell’intestazione possono nascondere i dati, possono comunque essere consultati da chi esamina il codice sorgente di una pagina o osserva le intestazioni utilizzando gli strumenti plug-in del browser.

Ad esempio, il raccoglitore J2EE può essere utilizzato per acquisire i dati del costo per clic (CPC) per i collegamenti visualizzati su una pagina, le informazioni sul partner sensibile su una pagina e molti altri punti dati. L&#39;ambiente J2EE facilita la modifica dell&#39;APP WEBAPP per acquisire i dati personalizzati utilizzando la nostra classe di raccoglitori.

Quando un sensore per la piattaforma J2EE riceve una richiesta, richiama una classe Collector che importa la funzione appendToLog. La funzione appendToLog aggiunge alla richiesta iniziale i parametri della stringa di query specificati nella funzione appendToLog. Questo determina l&#39;URI della richiesta iniziale contenente coppie nome-valore della stringa di query aggiuntive che corrispondono ai nomi e ai valori dei dati acquisiti. Ad esempio, CPC=20 viene aggiunto alla richiesta iniziale quando il valore di una particolare posizione annuncio o collegamento click-through è 20 centesimi. Insight Server elabora questi valori nel dataset per l&#39;analisi. Un ulteriore vantaggio di questa metodologia di raccolta è dato dal fatto che consente la raccolta di dati aggiuntivi senza creare voci di registro aggiuntive, come potrebbe essere creato utilizzando le metodologie per l&#39;assegnazione dei tag alle pagine.

Per ulteriori informazioni sull&#39;elaborazione, vedere la Guida alla configurazione del set di dati.

Per acquisire dati aggiuntivi da una pagina:

1. Aggiungi il codice seguente nella parte superiore della pagina .jsp da cui vuoi acquisire i dati:

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. Utilizzare il metodo appendToLog() dell&#39;oggetto Collector per aggiungere le coppie nome-valore desiderate alla stringa di query della pagina .jsp richiesta. L’esempio seguente aggiunge &quot;A=1&quot; e &quot;B=2&quot; alla stringa di query della pagina .jsp richiesta per la pagina /index.jsp:

   ```
   <html> 
   <body> 
     <h1>Hello World</h1> 
     <% 
       VSCollector collector = new VSCollector(request, response); 
       collector.appendToLog("A", "1"); 
       collector.appendToLog("B", "2"); 
     %> 
   </body> 
   </html>
   ```

   L&#39;URI della richiesta risultante è /index.jsp?A=1&amp;B=2.

1. Ripetete questa procedura per ogni pagina .jsp da cui desiderate acquisire dati aggiuntivi.

