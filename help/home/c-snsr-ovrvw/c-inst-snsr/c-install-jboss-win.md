---
description: Istruzioni dettagliate per l'installazione e la configurazione del sensore per JBoss Server 4.0.5 o versione successiva in esecuzione in Microsoft Windows Server 2000 o versione successiva.
title: Server JBoss su Windows Server 2000 o versione successiva
uuid: b0501749-9479-484b-8876-fe3001825f8d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Server JBoss su Windows Server 2000 o versione successiva{#jboss-server-on-windows-server-or-later}

Istruzioni dettagliate per l&#39;installazione e la configurazione del sensore per JBoss Server 4.0.5 o versione successiva in esecuzione in Microsoft Windows Server 2000 o versione successiva.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponete già del file di installazione Sensor per il vostro particolare server Web, scaricatelo (o ottenetelo dal rappresentante Adobe) prima di iniziare le seguenti procedure.

Le implementazioni J2EE supportate includono:

* JBoss Server 4.0.5 o versione successiva in esecuzione su Microsoft Windows Server 2000 o versione successiva.

Per installare e configurare Sensor, devi eseguire le seguenti operazioni:

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedura per estrarre e installare i file di programma per Sensor.

1. Sul server JBoss, create una directory in cui installare i file del programma Sensor. Tenere presente che la coda del disco si trova in questa directory, quindi assicurarsi che il dispositivo scelto disponga di spazio sufficiente per contenere una coda delle dimensioni necessarie.

   ```
   C:\VisualSensor
   ```

1. Estrarre il contenuto del file di installazione nella directory appena creata. Durante questo passaggio, Sensor installa i file seguenti:

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
>Il pacchetto di installazione contiene un foglio di calcolo denominato [!DNL TestExperiment.xls]. Questo foglio di calcolo è uno strumento che gli architetti usano per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se potete scegliere di farlo). Potreste desiderare, invece, copiare il file in una posizione in cui gli architetti possano accedervi o semplicemente estrarre il file dal pacchetto di installazione in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati di Insight.

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

1. Dal menu Start in Windows, selezionate Accessori > Prompt dei comandi.
1. Nella finestra del prompt dei comandi, andate alla directory in cui avete installato Sensor ed eseguite il seguente comando:

   ```
   txlog /regserver
   ```

   Questo comando avvia il trasmettitore, crea la coda del disco e registra Sensor come servizio Windows.

1. Per confermare che il trasmettitore funziona correttamente, fate clic su Start > Pannello di controllo > Strumenti di amministrazione > Servizi.

   >[!NOTE]
   >
   >Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

   1. Nell&#39;elenco dei servizi, individuare la voce per Sensor e confermare che il suo stato è Avviato e il suo tipo di avvio è Automatico.
   1. Chiudere il pannello di controllo Servizi.

1. Per verificare se il trasmettitore ha riscontrato degli errori durante l’avvio, fate clic su Start > Pannello di controllo > Strumenti di amministrazione > Visualizzatore eventi per aprire il visualizzatore eventi.

   1. Nel riquadro a sinistra della finestra Visualizzatore eventi, selezionate il registro Applicazioni.
   1. Nel riquadro a destra, cercate gli eventi con &quot;Adobe&quot; nella colonna Sorgente.
   1. Se si verifica un errore in &quot;Adobe&quot;, fare doppio clic sull&#39;errore per visualizzare la finestra Proprietà evento. Questa finestra fornisce informazioni dettagliate sull&#39;errore.

1. Al termine dell&#39;esame del registro Applicazioni, chiudete il visualizzatore eventi.
1. Verificare che il trasmettitore abbia creato la coda del disco (Diskq2000.log) nella directory in cui sono stati installati i file del programma Sensor e che si tratti della dimensione specificata nel parametro QueueSize nel file txlogd.conf.

   Se la coda non è stata creata correttamente:

   1. Esaminate il file txtlogd.conf e verificate che il parametro QueueSize sia impostato correttamente.
   1. Verificare che il dispositivo su cui è installato Sensor disponga di spazio sufficiente per contenere un file delle dimensioni specificate nel parametro QueueSize.
   1. Con il pannello di controllo Servizi in Windows, arrestare il trasmettitore.
   1. Eliminare il file della coda.
   1. Registrare nuovamente il sensore come servizio Windows: dal menu Start in Windows, selezionate Accessori > Prompt dei comandi. Nella finestra del prompt dei comandi, andate alla directory in cui avete installato Sensor ed eseguite il seguente comando:

      ```
      txlog /regserver
      ```

Il trasmettitore è progettato per funzionare in modo continuo. Se si riavvia il computer, il trasmettitore si riavvia automaticamente. Se è necessario avviare e arrestare manualmente il trasmettitore, è possibile farlo utilizzando il pannello di controllo Servizi in Windows.

## Aggiungere l&#39;agente di raccolta al server Web {#section-c5b83ae4ebce430aa764f951e849b333}

Per i server JBoss, l&#39;agente di raccolta funziona come un filtro nel contenitore servlet.

Per aggiungere l’agente di raccolta al server Web, è necessario modificare il [!DNL web.xml] file come descritto di seguito e riavviare l’applicazione Web.

1. Utilizzando un editor di testo, aprite il [!DNL web.xml] file per il server Web i cui eventi Sensor acquisisce.
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

1. Riavviate il processo del server Web (non è necessario riavviare l&#39;intero computer del server, ma è sufficiente riavviare il processo del server Web). L&#39;agente di raccolta viene caricato con il server Web e inizia a raccogliere i dati dell&#39;evento e a scriverli nella coda del disco.

## Modificare lo script di avvio {#section-0dae181ef8884f10a57f6cfda8500969}

Prima di modificare lo script di avvio, assicurarsi che la variabile JAVA_HOME sia definita nell&#39;ambiente Windows.

Nel [!DNL run.bat] file (ad esempio, C:\jboss-4.0.5.GA\bin\run.bat), aggiungete le seguenti righe accanto alla fine del file subito prima delle righe &quot;echo&quot; che precedono il comando di avvio del server JBoss:

```
set JBOSS_CLASSPATH=%JBOSS_CLASSPATH%;C:\jboss-4.0.5.GA\server\default\lib\javax.servlet.jar;C:\VisualSciences\J2EECollector.jar 
set JAVA_OPTS=%JAVA_OPTS% -Djava.library.path=C:\VisualSciences
```

## Acquisizione di dati aggiuntivi {#section-9483b663cbd0432daaca50c1089c7fca}

È possibile acquisire dati di misurazione aggiuntivi dalle applicazioni Web basate su J2EE utilizzando la funzionalità appendToLog().

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

