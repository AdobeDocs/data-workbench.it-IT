---
description: Istruzioni dettagliate per l'installazione e la configurazione del sensore per le implementazioni J2EE eseguite su RedHat Linux 7.x o versioni successive, Sun Solaris SPARC 2.6 o versioni successive, o Sun Solaris x86 9 o versioni successive.
title: Server JBoss, Tomcat e WebLogic su RedHat Linux o Sun Solaris
uuid: 7977fb9b-1737-4e1d-80c6-aabf968974dd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Server JBoss, Tomcat e WebLogic su RedHat Linux o Sun Solaris{#jboss-tomcat-and-weblogic-servers-on-redhat-linux-or-sun-solaris}

Istruzioni dettagliate per l&#39;installazione e la configurazione del sensore per le implementazioni J2EE eseguite su RedHat Linux 7.x o versioni successive, Sun Solaris SPARC 2.6 o versioni successive, o Sun Solaris x86 9 o versioni successive.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponete già del file di installazione Sensor per il vostro particolare server Web, scaricatelo (o ottenetelo dal rappresentante Adobe) prima di iniziare le seguenti procedure.

Le implementazioni J2EE supportate includono:

* JBoss Server 3.2.x o successivo
* Apache Jakarta Tomcat Server 4.1 o successivo
* WebLogic Server 6.x o successivo

Per installare e configurare Sensor, devi eseguire le seguenti operazioni:

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedura per estrarre e installare i file di programma per Sensor.

1. Accedete come utente principale o come utente con autorizzazione principale.
1. Decomprimete e decomprimete il file di installazione utilizzando il seguente comando:

   * In Linux:

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * Su Solaris:

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
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

| File | Autorizzazioni predefinite | chmod, comando |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- r— r— | chmod 664 |
| trust_ca_cert.pem | rw- r— r— | chmod 664 |

## Modificare il file di configurazione Sensor {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

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

## Aggiungere l&#39;agente di raccolta al server Web {#section-c5b83ae4ebce430aa764f951e849b333}

Per i server Apache, l&#39;agente di raccolta è un oggetto condiviso dinamico caricato nel processo del server Web.

Per aggiungere l’agente di raccolta al server Web, è necessario modificare il [!DNL httpd.conf] file come descritto di seguito e riavviare il server Web.

>[!NOTE]
>
>Se Sensor sta acquisendo dati per più server Web sul computer server, è necessario eseguire la procedura seguente per ciascun server Web.

1. Utilizzando un editor di testo, aprite il [!DNL httpd.conf]file per il server Web i cui eventi Sensor acquisiscono.
1. Aggiungete i seguenti `<filter>` elementi e `<filter-mapping>` elementi al file descrittore. Se non avete installato txlogd.conf nella directory /etc, dovete immettere il percorso corretto per questo file nell&#39; `<param-value>` elemento:

   ```
   <filter>
     <filter-name>VSCollectorFilter</filter-name> 
     <description></description> 
     <filter-class> 
         com.visualsciences.collector.VSCollectorFilter 
       </filter-class> 
     <init-param> 
       <param-name>configPath</param-name> 
       <param-value>/etc/txlogd.conf</param-value> 
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

1. Riavviate il processo del server Web (non è necessario riavviare l&#39;intero computer del server, ma è sufficiente riavviare il processo del server Web). L&#39;agente di raccolta viene caricato con il server Web e inizia a raccogliere i dati dell&#39;evento e a scriverli nella coda del disco.

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

Questo comando avvia il trasmettitore come un demone. I messaggi operativi ed di errore generati dal trasmettitore sono scritti [!DNL syslog].

L&#39;impostazione predefinita di Solaris è 60. In base ai test condotti con Sensor, che utilizza tre semafori per ogni istanza, Adobe consiglia di usare 1024 come impostazione. Questo numero è sufficientemente elevato da consentire il funzionamento del sensore insieme ad altre applicazioni sul server che possono richiedere dei semafori, ma non influisce sulle prestazioni. Per sostenere questa raccomandazione, si prega di notare che Adrian Cockcroft ha dichiarato quanto segue nel suo libro Sun Performance and Tuning (Prentice Hall, ottobre 1994): &quot;I database tendono a utilizzare un sacco di memoria condivisa e di impostazioni del semaforo. che non incidono sulle prestazioni; fintanto che sono abbastanza grandi, i programmi funzioneranno.&quot;

## Acquisizione di dati aggiuntivi {#section-9483b663cbd0432daaca50c1089c7fca}

I sensori per tutte le piattaforme possono raccogliere qualsiasi dato disponibile nelle intestazioni di richiesta e risposta HTTP.

I sensori per la piattaforma J2EE forniscono un meccanismo per la raccolta di dati non disponibili su altre piattaforme. Il raccoglitore per la piattaforma J2EE (raccoglitore J2EE) si trova sul livello dell&#39;applicazione, che consente di raccogliere dati sensibili che sono disponibili solo per l&#39;applicazione e non devono essere esposti tramite tag di pagina o nelle intestazioni.

>[!NOTE]
>
>Mentre i tag pagina e la modifica dell’intestazione possono nascondere i dati, possono comunque essere consultati da chi esamina il codice sorgente di una pagina o osserva le intestazioni utilizzando gli strumenti plug-in del browser.

Ad esempio, il raccoglitore J2EE può essere utilizzato per acquisire i dati del costo per clic (CPC) per i collegamenti visualizzati su una pagina, le informazioni sul partner sensibile su una pagina e molti altri punti dati. L&#39;ambiente J2EE facilita la modifica dell&#39;APP WEBAPP per acquisire i dati personalizzati utilizzando la nostra classe di raccoglitori.

Quando un sensore per la piattaforma J2EE riceve una richiesta, richiama una classe Collector che importa la funzione appendToLog. La funzione appendToLog aggiunge alla richiesta iniziale i parametri della stringa di query specificati nella funzione appendToLog. Questo determina l&#39;URI della richiesta iniziale contenente coppie nome-valore della stringa di query aggiuntive che corrispondono ai nomi e ai valori dei dati acquisiti. Ad esempio, CPC=20 viene aggiunto alla richiesta iniziale quando il valore di una particolare posizione annuncio o collegamento click-through è 20 centesimi. Insight Server elabora questi valori nel dataset per l&#39;analisi. Un ulteriore vantaggio di questa metodologia di raccolta è dato dal fatto che consente la raccolta di dati aggiuntivi senza creare voci di registro aggiuntive, come potrebbe essere creato utilizzando le metodologie per l&#39;assegnazione dei tag alle pagine.

Per ulteriori informazioni sull&#39;elaborazione, vedere la Guida alla configurazione del set di dati.

**Per acquisire dati aggiuntivi da una pagina**

1. Aggiungete il codice seguente nella parte superiore della pagina .jsp da cui desiderate acquisire i dati:

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

