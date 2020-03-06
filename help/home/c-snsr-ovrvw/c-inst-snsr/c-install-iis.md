---
description: Istruzioni su come installare e configurare Sensor for Internet Information Services (IIS) 5.x o 6.x in esecuzione in Microsoft Windows Server 2000 o versioni successive.
title: Microsoft IIS su Windows Server 2000 o versione successiva
uuid: 26da0638-82c8-424f-9f00-aab3a940e5a9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Microsoft IIS su Windows Server 2000 o versione successiva{#microsoft-iis-on-windows-server-or-later}

Istruzioni su come installare e configurare Sensor for Internet Information Services (IIS) 5.x o 6.x in esecuzione in Microsoft Windows Server 2000 o versioni successive.

Quando si utilizza IIS 6.x, la registrazione deve essere abilitata affinché il sensore funzioni correttamente. Se la registrazione è stata disabilitata per ridurre l&#39;I/O del disco, è possibile abilitare la registrazione senza scrivere alcun dato nei registri. A questo scopo, abilitare la registrazione, quindi cancellare tutti i campi nella scheda Avanzate della scheda Proprietà per il formato di file registro esteso W3C. Per assistenza, contattate i servizi di consulenza Adobe.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponete già del file di installazione Sensor per il vostro particolare server Web, scaricatelo (o ottenetelo dal rappresentante Adobe) prima di iniziare le seguenti procedure.

Per installare e configurare Sensor, devi eseguire i seguenti passaggi di alto livello:

## 1. Installare i file del programma {#section-9ef8c4e38c244b7d8b6d4bc6c0ad53fd}

Quando si esegue Sensor su Windows IIS, i file del programma e il file della coda del disco devono risiedere nella stessa directory.

Pertanto, prima di installare i file del programma, è necessario determinare dove si desidera mantenere la coda del disco, perché è anche dove si devono installare i file del programma.

Utilizzate la seguente procedura per estrarre e installare i file di programma per Sensor.

1. Sul computer Windows, creare una directory in cui installare i file del programma Sensor. Tenere presente che la coda del disco risiede anche in questa directory, quindi assicurarsi che il dispositivo scelto disponga di spazio sufficiente per contenere una coda delle dimensioni necessarie.

   Ad esempio: C:\VisualSensor

1. Estrarre il contenuto del file di installazione nella directory appena creata. Durante questo passaggio, Sensor installa i file seguenti:

<table id="table_C9E8803E51D046FD8FCCA38F8DAC04D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> File </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> EventMessages.dll </td> 
   <td colname="col2"> Messaggi del visualizzatore eventi. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> qlog.dll </td> 
   <td colname="col2"> Modulo di raccolta (un filtro ISAPI). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TestExperiment.xls </td> 
   <td colname="col2"> <p>Un file foglio di calcolo Excel che gli architetti possono utilizzare per configurare un esperimento controllato. </p> <p>Il sensore non utilizza questo file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificato utilizzato per convalidare il certificato digitale presentato da Insight Server durante il processo di connessione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> TXLog.exe </td> 
   <td colname="col2"> Il programma del trasmettitore. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Il file di configurazione Sensor. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Il pacchetto di installazione contiene un foglio di calcolo denominato TestExperiment.xls. Questo foglio di calcolo è uno strumento che gli architetti usano per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se potete scegliere di farlo). Potreste desiderare, invece, copiare il file in una posizione in cui gli architetti possano accedervi o semplicemente estrarre il file dal pacchetto di installazione in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati di Insight.

## 2. Modifica del file di configurazione {#section-206daf855e664f16af9a96a5cd3e62b1}

Il file txlogd.conf contiene i parametri di configurazione per Sensor.

È necessario modificare il file per specificare, tra l&#39;altro, le dimensioni della coda del disco, l&#39;indirizzo del server di Insight e l&#39;ID che verrà allegato ai dati prodotti da questo sensore. Il file di configurazione contiene i parametri obbligatori e i parametri facoltativi.

* **I parametri** richiesti sono impostazioni che dovete specificare quando installate Sensor. Senza queste impostazioni, il sensore non viene eseguito correttamente.
* **I parametri** facoltativi sono impostazioni predefinite per valori predefiniti (che è possibile modificare) o per abilitare funzioni facoltative.

**Per modificare il file di configurazione Sensor**

1. Aprite il `<SensorDirectory>/txlogd.conf` file in un editor di testo e impostate i parametri richiesti, nonché eventuali parametri opzionali desiderati.

   Per una descrizione dei parametri txlogd.conf, consultate Parametri del file Sensor Txlogd.conf.

   Per esempi di file di configurazione completati, consultate File di configurazione di esempio sensore.

1. Salvate e chiudete il file.

## 3. Avviare il trasmettitore e creare la coda del disco {#section-a0af390ee1954109bcff5d9f09798683}

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

   >[!NOTE]
   >
   >Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

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

## Aggiungere l&#39;agente di raccolta al server Web {#section-682dc480e5574791ac18da104daf7906}

Per IIS, l&#39;agente di raccolta è un filtro ISAPI aggiunto al server Web in IIS.

1. Aprire Gestione IIS utilizzando Start > Strumenti di amministrazione > Gestione Internet Information Services (IIS).
1. Espandere i nodi Computer locale e Siti Web.
1. Fare clic con il pulsante destro del mouse sul sito Web a cui si desidera aggiungere il raccoglitore e selezionare Proprietà.
1. Selezionate la scheda Filtri ISAPI e fate clic su Aggiungi.
1. Nel campo Nome filtro, inserite un nome visualizzato per il filtro. Il nome del filtro consigliato è &quot;Sensor&quot;.
1. Fate clic su Sfoglia, selezionate il file qlog.dll (che si trova nella directory in cui avete installato Sensor), quindi fate clic su OK.
1. Fate clic su OK per aggiungere il filtro.

   Dopo aver aggiunto il filtro, il raccoglitore è immediatamente operativo e pronto per raccogliere i dati. Nella colonna Stato della scheda Filtri ISAPI della Gestione IIS deve essere visualizzata una freccia verso l&#39;alto verde. Potrebbe non essere visibile la freccia verde finché il traffico non scorre attraverso il filtro. In questo caso, è necessario inviare una richiesta al server Web per confermare che il sistema di raccolta funziona correttamente.

Se la freccia verde non viene visualizzata dopo che il traffico scorre verso il raccoglitore, completare i seguenti passaggi:

1. Fate clic su Start > Strumenti di amministrazione > Visualizzatore eventi per verificare la presenza di errori nel visualizzatore eventi.

   >[!NOTE]
   >
   >Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

1. Nel riquadro a sinistra della finestra Visualizzatore eventi, selezionate il registro applicazioni.
1. Nel riquadro a destra, cercate gli eventi con &quot;Adobe&quot; nella colonna Sorgente.
1. Se si verifica un errore, fare doppio clic sull&#39;errore per visualizzare la finestra Proprietà evento.

## Acquisizione di dati aggiuntivi {#section-dcd10073eb1947a5928e4f9b9fa99e3a}

Le pagine Web sono spesso strutturate utilizzando il linguaggio di programmazione ASP (Active Server Pages).

ASP è una tecnologia Microsoft che viene eseguita in IIS. Quando un browser richiede un file ASP, IIS trasmette la richiesta al motore ASP. Il motore ASP legge il file ASP, riga per riga ed esegue gli script nel file. Infine, il file ASP viene restituito al browser come HTML semplice. ASP fornisce oggetti RESPOND o REQUEST che, oltre ad altre utilità, consentono la risposta o la richiesta di query utente o di dati inviati da moduli HTML.

In alcuni casi, è possibile che non si desideri aggiungere i valori immessi nei moduli all&#39;URL visualizzato nella barra degli indirizzi del browser di un utente o visibile all&#39;interno del codice HTML stesso. Uno script ASP sul lato server semplice consente di aggiungere al file di registro i nomi dei campi del modulo e i rispettivi valori senza renderli disponibili nel browser dell&#39;utente né incorporarli nel file HTML. Per acquisire i valori effettivi del modulo immessi in particolari moduli all&#39;interno del sito Web, è necessario aggiungere alcune righe di codice per aggiungere i valori del modulo alla richiesta di registro.

Nella pagina di elaborazione di un modulo, includere il seguente codice per aggiungere i valori del modulo immessi ai dati della richiesta (oltre a scrivere i valori del modulo inviato in un database esterno o in un&#39;altra posizione):

```
var sName= Request.Form("Name"); 
var sCity= Request.Form("City"); 
var sState= Request.Form("State"); 
var sZip= Request.Form("Zip"); 
 
Response.AppendToLog("&v_1=" +  sName); 
Response.AppendToLog("&v_2=" +  sCity); 
Response.AppendToLog("&v_3=" +  sState); 
Response.AppendToLog("&v_4=" +  sZip);
```

Questo processo aggiunge i valori del modulo come definiti ai dati della richiesta per la pagina Elaborazione modulo. All&#39;interno dei dati di registro, i valori aggiunti sarebbero disponibili come stringhe di query nella pagina Elaborazione modulo, come illustrato di seguito. Ad esempio, v_1, v_2, v_3 e v_4 sono ora stringhe di query contenenti i dati immessi nei campi modulo appropriati. La sintassi descritta nell&#39;esempio precedente può essere duplicata per tutti i campi e i valori aggiuntivi del modulo che si desidera acquisire:

```
http://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Se si desidera acquisire tutti i campi e i valori del modulo e renderli disponibili per l&#39;analisi, è possibile utilizzare la sintassi seguente:

```
var formvalues = Response.Form; 
Response.AppendToLog(formvalues);
```

Questo esempio considera tutti i campi modulo presenti nel codice HTML insieme ai rispettivi valori e li aggiunge come stringhe di query alla voce di registro per la pagina Elaborazione modulo. Tenere presente che questo includerebbe tutti i campi nascosti presenti nel modulo.

I dati del registro verranno aumentati come descritto nella tabella seguente:

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_1 | Valore associato alla stringa query NAME | v_1=John Smith |
| v_2 | Valore associato alla stringa query CITY | v_2=Los Angeles |
| v_3 | Valore associato alla stringa di query STATE | v_3=California |
| v_4 | Valore associato alla stringa query ZIP | v_4=90210 |

