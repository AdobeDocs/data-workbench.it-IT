---
description: Istruzioni dettagliate per l'installazione e la configurazione di Sensor per le implementazioni J2EE in esecuzione su RedHat Linux 7.x o versioni successive, Sun Solaris SPARC 2.6 o versioni successive o Sun Solaris x86 9 o versioni successive.
title: Server JBoss, Tomcat e WebLogic su RedHat Linux o Sun Solaris
uuid: 7977fb9b-1737-4e1d-80c6-aabf968974dd
exl-id: 09c2f266-2ecc-42fc-98b6-b91f8883af0c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1823'
ht-degree: 1%

---

# Server JBoss, Tomcat e WebLogic su RedHat Linux o Sun Solaris{#jboss-tomcat-and-weblogic-servers-on-redhat-linux-or-sun-solaris}

{{eol}}

Istruzioni dettagliate per l&#39;installazione e la configurazione di Sensor per le implementazioni J2EE in esecuzione su RedHat Linux 7.x o versioni successive, Sun Solaris SPARC 2.6 o versioni successive o Sun Solaris x86 9 o versioni successive.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponi già del file di installazione di Sensor per il tuo particolare server web, scaricalo (o ottenerlo dal tuo rappresentante di Adobe) prima di iniziare le seguenti procedure.

Le implementazioni J2EE supportate includono:

* JBoss Server 3.2.x o successivo
* Apache Jakarta Tomcat Server 4.1 o successivo
* WebLogic Server 6.x o successivo

Per installare e configurare Sensor, devi eseguire le seguenti operazioni:

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedura per estrarre e installare i file di programma per Sensor.

1. Accedi come utente principale o come utente con autorità radice.
1. Decomprimi e decomprimi il file di installazione utilizzando il seguente comando:

   * Su Linux:

      ```
      tar -zxf installationFilename.tar.gz
      ```

   * Su Solaris:

      ```
      unzip -d installationFilename.tar.gz 
       tar -xf installationFilename.tar
      ```

1. Copia i file di programma decompattati nelle directory identificate nella tabella seguente:

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
   <td colname="col3"> <i> IBMHttpServer/modules</i> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Il programma del trasmettitore. </td> 
   <td colname="col3"> <p><i>/usr/local/bin</i> </p> <p><i>—OPPURE—</i> </p> <p><i>/usr/local/sbin</i> </p> </td> 
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
>Il pacchetto di installazione contiene un file di foglio di calcolo denominato TestExperiment.xls. Questo foglio di calcolo è uno strumento che gli architetti utilizzano per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se è possibile scegliere di farlo). È invece possibile copiare il file in un percorso in cui gli architetti possono accedervi o semplicemente estrarre il file dal pacchetto di installazione, in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati da Insight.

**Autorizzazioni sui file del programma**

>[!NOTE]
>
>Autorizzazioni errate sui file di programma causano la maggior parte dei problemi incontrati durante l&#39;installazione di Sensor. Assicurati di impostare le autorizzazioni esattamente come indicato in questa sezione.
>
>Per impostazione predefinita, i file di programma nel file tar hanno le seguenti autorizzazioni. A seconda della configurazione del sistema, queste impostazioni potrebbero essere modificate (non mascherate) durante l’estrazione dei file. Per ripristinare le autorizzazioni alle impostazioni predefinite consigliate, utilizza i comandi chmod riportati di seguito. Controlla che le directory in cui hai installato i file consentano almeno questo livello di accesso.

| File | Autorizzazioni predefinite | comando chmod |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 775 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- r— r— | chmod 664 |
| trust_ca_cert.pem | rw- r— r— | chmod 664 |

## Modificare il file di configurazione del sensore {#section-2e2f1875a5304cdfa2cbcd0680683cfd}

La [!DNL txlogd.conf] il file contiene i parametri di configurazione per Sensor.

È necessario modificare questo file per specificare, tra l’altro, le dimensioni e la posizione del file della coda del disco, l’indirizzo di Insight Server e l’ID che verrà allegato ai dati dell’evento prodotti da questo sensore.

Il file di configurazione contiene i parametri richiesti e i parametri facoltativi.

* **Parametri richiesti** sono impostazioni che è necessario specificare quando si installa Sensor. Senza queste impostazioni, il sensore non viene eseguito correttamente.
* **Parametri opzionali** sono impostazioni predefinite per valori predefiniti (che è possibile modificare) o per l’abilitazione di funzionalità facoltative.

**Per modificare il file di configurazione Sensor**

* Apri [!DNL /etc/txlogd.conf] in un editor di testo e imposta i parametri richiesti ed eventuali parametri facoltativi desiderati.
* Salva e chiudi il file.

**Per modificare il file di configurazione Sensor**

1. Apri [!DNL /etc/txlogd.conf] in un editor di testo e imposta i parametri richiesti ed eventuali parametri facoltativi desiderati.
1. Salva e chiudi il file.

## Avviare il trasmettitore e creare la coda del disco {#section-55630de65f264274aefd771da2002852}

Dopo aver configurato il file txlogd.conf, è possibile avviare il programma del trasmettitore, registrarlo come servizio Windows e creare la coda del disco.

1. Se la directory in cui si trova la coda del disco non esiste già, crearla. Assicurati che la directory offra sia il modulo di raccolta che il programma del trasmettitore con accesso in lettura/scrittura al file.

   Per ulteriori informazioni sulle autorizzazioni richieste dai file della coda del disco, vedere Autorizzazioni dei file UNIX di Sensor.
1. Sul computer in cui è installato Sensor, eseguire il seguente comando per avviare il trasmettitore:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * L&#39;opzione &quot;i&quot; in questo comando avvia il trasmettitore in &quot;modalità interattiva&quot;. Questa modalità visualizza i messaggi del trasmettitore sullo schermo e consente inoltre di interagire con il trasmettitore utilizzando i comandi della tastiera.
   * L&#39;opzione &quot;c&quot; indirizza il trasmettitore a creare la coda del disco.
   * L&#39;opzione &quot;f&quot; specifica la posizione del file di configurazione.

   Per ulteriori informazioni sulle opzioni che è possibile utilizzare quando si avvia il trasmettitore, vedere Opzioni della riga di comando del Sensor Transmitter.

1. Verificare che il trasmettitore abbia creato la coda del disco nella posizione specificata nel parametro QueueFile e delle dimensioni specificate nel parametro QueueSize.
1. Se la coda non è stata creata correttamente, digita Ctrl+C per terminare il trasmettitore, quindi procedi come segue:

   1. Esamina il file txtlogd.conf e verifica che i parametri QueueFile e QueueSize siano impostati correttamente.
   1. Verificare che il dispositivo a cui è assegnata la coda del disco sia operativo e che disponga di spazio sufficiente per contenere un file delle dimensioni specificate nel parametro QueueSize.
   1. Apportare le correzioni necessarie e ripetere la procedura.

## Aggiungere l&#39;agente di raccolta al server Web {#section-c5b83ae4ebce430aa764f951e849b333}

Per i server Apache, il raccoglitore è un oggetto dinamico condiviso caricato nel processo del server web.

Per aggiungere il raccoglitore al server web, devi modificare il [!DNL httpd.conf] come descritto di seguito e riavvia il server web.

>[!NOTE]
>
>Se Sensor acquisisce dati per più server Web sul computer server, è necessario eseguire la procedura seguente per ogni server Web.

1. Utilizzando un editor di testo, apri le [!DNL httpd.conf]file per il server web i cui eventi acquisisce Sensor.
1. Aggiungi quanto segue `<filter>` e `<filter-mapping>` al file descrittore. Se non hai installato txlogd.conf nella directory /etc, devi immettere il percorso corretto di questo file nel `<param-value>` elemento:

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
   >Queste righe sono sensibili all’uso di maiuscole e minuscole. Digitali esattamente come appaiono sopra.

1. Riavviare il processo del server Web (non è necessario riavviare l&#39;intero computer server, è sufficiente riavviare il processo del server Web). Il raccoglitore viene caricato con il server Web e inizia a raccogliere i dati dell&#39;evento e a scriverli nella coda del disco.

## Test del sensore {#section-0dae181ef8884f10a57f6cfda8500969}

Verifica che il raccoglitore stia raccogliendo i dati dell’evento e che il trasmettitore lo stia trasmettendo al target Insight Server.

>[!NOTE]
>
>Per verificare che il trasmettitore possa inviare correttamente i dati dell’evento a Insight Server, assicurati che Insight Server di destinazione sia installato ed in esecuzione prima di iniziare il test seguente.

1. Se il trasmettitore non è già in esecuzione, riavviarlo utilizzando il seguente comando:

   ```
   /usr/local/bin/txlogd -i -f /etc/txlogd.conf 
   ```

1. Apri un browser (su qualsiasi computer) e richiedi una pagina dal server web su cui è in esecuzione Sensor (assicurati di selezionare una pagina che Sensor sta monitorando).
1. Dopo aver effettuato la richiesta, controlla nella console del trasmettitore i messaggi che indicano che sta inviando dati evento a Insight Server di destinazione.
1. Se il sensore non trasmette correttamente i dati, verifica che:

   * Target Insight Server è in esecuzione.
   * I parametri ServerAddress e ServerPort sono impostati correttamente in txtlogd.conf. Se ServerAddress è stato specificato utilizzando un nome server, provare a utilizzare il relativo indirizzo IP numerico.
   * Il valore del parametro CertName corrisponde esattamente al nome comune visualizzato nel certificato digitale di Target Insight Server.

## Aggiungi il trasmettitore allo script di avvio del sistema {#section-19a38f27c9f44adf88f8910f5ed483a3}

Informazioni sul caricamento automatico del trasmettitore nello script di avvio del sistema.

Per garantire che il trasmettitore venga caricato automaticamente al riavvio del server Web, aggiungi il seguente comando (che avvia il trasmettitore) allo script di avvio del sistema:

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Questo comando avvia il trasmettitore come un daemon. I messaggi di funzionamento ed errore generati dal trasmettitore sono scritti in [!DNL syslog].

L&#39;impostazione predefinita di Solaris è 60. In base ai test condotti con Sensor, che utilizza tre semafori per ogni istanza, Adobe consiglia di utilizzare 1024 come impostazione. Questo numero è abbastanza alto da consentire il funzionamento di Sensor insieme a qualsiasi altra applicazione sul server che può richiedere dei semafori, ma non influisce sulle prestazioni. Per sostenere questa raccomandazione, si prega di notare che Adrian Cockcroft ha affermato quanto segue nel suo libro Sun Performance and Tuning (Prentice Hall, ottobre 1994): &quot;I database tendono a utilizzare molte impostazioni di memoria condivisa e semaforo. che non influiscono sulle prestazioni; finché sono abbastanza grandi, i programmi funzioneranno.&quot;

## Acquisizione di dati aggiuntivi {#section-9483b663cbd0432daaca50c1089c7fca}

I sensori per tutte le piattaforme possono raccogliere qualsiasi dato disponibile nelle intestazioni di richiesta e risposta HTTP.

I sensori per la piattaforma J2EE forniscono un meccanismo per la raccolta di dati che non è disponibile su altre piattaforme. Il raccoglitore per la piattaforma J2EE (J2EE Collector) si trova sul livello dell&#39;applicazione, che gli consente di raccogliere dati sensibili disponibili solo per l&#39;applicazione e che non devono essere esposti tramite tag di pagina o nelle intestazioni.

>[!NOTE]
>
>Anche se i tag pagina e la modifica dell’intestazione possono nascondere i dati, sono comunque disponibili per coloro che esaminano il codice sorgente di una pagina o guardano le intestazioni utilizzando gli strumenti plug-in del browser.

Ad esempio, il raccoglitore J2EE può essere utilizzato per acquisire i dati di costo per clic (CPC) per i collegamenti visualizzati su una pagina, le informazioni sensibili dei partner su una pagina e molti altri punti di dati. L’ambiente J2EE ti consente di modificare facilmente la tua WEBAPP per acquisire questi dati personalizzati utilizzando la nostra classe Collector.

Quando un sensore per la piattaforma J2EE riceve una richiesta, richiama una classe di raccolta che importa la funzione appendToLog. La funzione appendToLog aggiunge alla richiesta iniziale i parametri della stringa di query specificati nella funzione appendToLog . Questo determina l’URI della richiesta iniziale contenente coppie nome-valore della stringa di query aggiuntive corrispondenti ai nomi e ai valori dei dati che vengono acquisiti. Ad esempio, CPC=20 verrebbe aggiunto alla richiesta iniziale quando il valore di un particolare posizionamento di annunci o collegamento click-through è di 20 centesimi. Insight Server elabora questi valori nel set di dati per l’analisi. Un ulteriore vantaggio di questa metodologia di raccolta è che consente la raccolta di dati aggiuntivi senza creare voci di registro aggiuntive, come potrebbe essere creato utilizzando le metodologie di assegnazione tag delle pagine.

Per ulteriori informazioni sull&#39;elaborazione, consulta la Guida alla configurazione del set di dati .

**Per acquisire dati aggiuntivi da una pagina**

1. Aggiungi il codice seguente nella parte superiore della pagina .jsp da cui desideri acquisire i dati:

   ```
   <%@ page import="com.visualsciences.collector.VSCollector" %>
   ```

1. Utilizzare il metodo appendToLog() dell&#39;oggetto Collector per aggiungere le coppie nome-valore desiderate alla stringa di query della pagina .jsp richiesta. L’esempio seguente aggiunge &quot;A=1&quot; e &quot;B=2&quot; alla stringa di query della pagina richiesta .jsp per la pagina /index.jsp :

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

   L’URI di richiesta risultante è /index.jsp?A=1&amp;B=2.

1. Ripeti questa procedura per ogni pagina .jsp da cui desideri acquisire dati aggiuntivi.
