---
description: Istruzioni dettagliate per l'installazione e la configurazione di Sensor per JBoss Server 4.0.5 o versione successiva in esecuzione in Microsoft Windows Server 2000 o versione successiva.
title: Server JBoss su Windows Server 2000 o versione successiva
uuid: b0501749-9479-484b-8876-fe3001825f8d
exl-id: d9001bc4-f3ef-4d26-9190-807194d20ada
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 1%

---

# Server JBoss su Windows Server 2000 o versione successiva{#jboss-server-on-windows-server-or-later}

{{eol}}

Istruzioni dettagliate per l&#39;installazione e la configurazione di Sensor per JBoss Server 4.0.5 o versione successiva in esecuzione in Microsoft Windows Server 2000 o versione successiva.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponi già del file di installazione di Sensor per il tuo particolare server web, scaricalo (o ottenerlo dal tuo rappresentante di Adobe) prima di iniziare le seguenti procedure.

Le implementazioni J2EE supportate includono:

* JBoss Server 4.0.5 o successivo in esecuzione su Microsoft Windows Server 2000 o versione successiva.

Per installare e configurare Sensor, devi eseguire le seguenti operazioni:

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedura per estrarre e installare i file di programma per Sensor.

1. Sul server JBoss, crea una directory in cui installare i file del programma Sensor. Tenere presente che la coda del disco si trova in questa directory, quindi assicurarsi che il dispositivo scelto abbia spazio sufficiente per contenere una coda delle dimensioni necessarie.

   ```
   C:\VisualSensor
   ```

1. Estrai il contenuto del file di installazione nella directory appena creata. Durante questo passaggio, Sensor installa i seguenti file:

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
>Il pacchetto di installazione contiene un file di foglio di calcolo denominato [!DNL TestExperiment.xls]. Questo foglio di calcolo è uno strumento che gli architetti utilizzano per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se è possibile scegliere di farlo). È invece possibile copiare il file in un percorso in cui gli architetti possono accedervi o semplicemente estrarre il file dal pacchetto di installazione, in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati da Insight.

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

1. Dal menu Start in Windows, selezionare Accessori > Prompt dei comandi.
1. Nella finestra del prompt dei comandi, passare alla directory in cui è stato installato Sensor ed eseguire il seguente comando:

   ```
   txlog /regserver
   ```

   Questo comando avvia il trasmettitore, crea la coda del disco e registra Sensor come servizio Windows.

1. Per confermare che il trasmettitore è in esecuzione correttamente, fai clic su Start > Pannello di controllo Campaign > Strumenti di amministrazione > Servizi.

   >[!NOTE]
   >
   >Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

   1. Nell&#39;elenco dei servizi, individuare la voce per Sensor e confermare che il suo stato è Avviato e che il suo tipo di avvio è Automatico.
   1. Chiudere il pannello di controllo Servizi.

1. Per verificare se il trasmettitore ha riscontrato errori durante l&#39;avvio, fai clic su Start > Pannello di controllo Campaign > Strumenti di amministrazione > Visualizzatore eventi per aprire il Visualizzatore eventi.

   1. Nel riquadro a sinistra della finestra Visualizzatore eventi selezionare il registro Applicazioni.
   1. Nel riquadro a destra, cerca gli eventi con &quot;Adobe&quot; nella colonna Origine.
   1. Se si trova un errore da &quot;Adobe&quot;, fare doppio clic sull&#39;errore per visualizzare la finestra Proprietà evento. Questa finestra fornisce informazioni dettagliate sull’errore.

1. Al termine dell&#39;esame del registro Applicazioni, chiudere il Visualizzatore eventi.
1. Verificare che il trasmettitore abbia creato la coda del disco (Diskq2000.log) nella directory in cui sono stati installati i file del programma Sensor e che si tratti della dimensione specificata nel parametro QueueSize nel file txlogd.conf.

   Se la coda non è stata creata correttamente:

   1. Esamina il file txtlogd.conf e verifica che il parametro QueueSize sia impostato correttamente.
   1. Verificare che il dispositivo su cui è installato Sensor disponga di spazio sufficiente per contenere un file delle dimensioni specificate nel parametro QueueSize.
   1. Utilizzando il pannello di controllo Servizi in Windows, arrestare il trasmettitore.
   1. Elimina il file della coda.
   1. Registra nuovamente Sensor come servizio Windows: dal menu Start in Windows, selezionare Accessori > Prompt dei comandi. Nella finestra del prompt dei comandi, passare alla directory in cui è stato installato Sensor ed eseguire il seguente comando:

      ```
      txlog /regserver
      ```

Il trasmettitore è progettato per funzionare continuamente. Se si riavvia il computer, il trasmettitore si riavvia automaticamente. Se è necessario avviare e arrestare il trasmettitore manualmente, è possibile farlo utilizzando il pannello di controllo Servizi di Windows.

## Aggiungere l&#39;agente di raccolta al server Web {#section-c5b83ae4ebce430aa764f951e849b333}

Per i server JBoss, il raccoglitore funziona come filtro nel contenitore servlet.

Per aggiungere il raccoglitore al server web, devi modificare il [!DNL web.xml] come descritto di seguito e riavvia l&#39;applicazione web.

1. Utilizzando un editor di testo, apri le [!DNL web.xml] file per il server web i cui eventi acquisisce Sensor.
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
   >Queste righe sono sensibili all’uso di maiuscole e minuscole. Digitali esattamente come appaiono sopra.

1. Riavviare il processo del server Web (non è necessario riavviare l&#39;intero computer server, è sufficiente riavviare il processo del server Web). Il raccoglitore viene caricato con il server Web e inizia a raccogliere i dati dell&#39;evento e a scriverli nella coda del disco.

## Modificare lo script di avvio {#section-0dae181ef8884f10a57f6cfda8500969}

Prima di modificare lo script di avvio, assicurati che la variabile JAVA_HOME sia definita nell’ambiente Windows.

In [!DNL run.bat] file (ad esempio, C:\jboss-4.0.5.GA\bin\run.bat), aggiungi le seguenti righe vicino alla fine del file poco prima delle righe &quot;echo&quot; che precedono il comando di avvio del server JBoss:

```
set JBOSS_CLASSPATH=%JBOSS_CLASSPATH%;C:\jboss-4.0.5.GA\server\default\lib\javax.servlet.jar;C:\VisualSciences\J2EECollector.jar 
set JAVA_OPTS=%JAVA_OPTS% -Djava.library.path=C:\VisualSciences
```

## Acquisizione di dati aggiuntivi {#section-9483b663cbd0432daaca50c1089c7fca}

È possibile acquisire dati di misurazione aggiuntivi da applicazioni web basate su J2EE utilizzando la funzionalità appendToLog() .

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
