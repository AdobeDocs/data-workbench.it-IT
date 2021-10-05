---
description: Installa e configura Sensor per Microsoft IIS 7.x o 8.x in esecuzione in Microsoft Windows Server 2008 o versione successiva.
title: Microsoft IIS su Windows Server 2008 o versione successiva
uuid: 7fd8da68-1553-4395-b13e-b08a6ee1948e
exl-id: cc909daa-60c0-4188-8e90-035c41bf3105
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '1589'
ht-degree: 1%

---

# Microsoft IIS su Windows Server 2008 o versione successiva{#microsoft-iis-on-windows-server-or-later}

Installa e configura Sensor per Microsoft IIS 7.x o 8.x in esecuzione in Microsoft Windows Server 2008 o versione successiva.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponi già del file di installazione di Sensor per il tuo particolare server web, scaricalo (o ottenerlo dal tuo rappresentante di Adobe) prima di iniziare le seguenti procedure.

Per installare e configurare Sensor, devi eseguire i seguenti passaggi di alto livello:

1. [Installare i file del programma](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-cb51e5932a6d40c5b00758a7a51b7578)
1. [Modifica il file di configurazione Sensor](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-1e1590a92222430e92066292512ae0df)
1. [Avviare il trasmettitore e creare la coda del disco](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-2b8dfd06996d4ab49998eeb99bd9f5f0)
1. [Aggiungi il raccoglitore al server web](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-088960c986cf449cb712152298b3518d)
1. [Acquisire dati aggiuntivi](../../../home/c-snsr-ovrvw/c-inst-snsr/c-install-iis-win8.md#section-98db9625efdc4b60bfd76f7adf4af74d)

## Installare i file del programma {#section-cb51e5932a6d40c5b00758a7a51b7578}

Quando si esegue Sensor su Windows IIS, i file del programma e il file della coda del disco devono trovarsi nella stessa directory.

Prima di installare i file di programma, determinare prima dove si desidera mantenere la coda del disco perché è in questo punto che è necessario installare i file di programma.

Segui la procedura seguente per estrarre e installare i file di programma per Sensor.

1. Sul computer Windows, creare una directory in cui installare i file del programma Sensor. Tenere presente che la coda del disco si trova anche in questa directory, quindi assicurarsi che il dispositivo scelto abbia spazio sufficiente per contenere una coda delle dimensioni necessarie.

   Ad esempio: C:\VisualSensor

1. Estrai il contenuto del file di installazione nella directory appena creata. Durante questo passaggio, Sensor installa i seguenti file:

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
   <td colname="col2"> Messaggi del Visualizzatore eventi. </td>
  </tr>
  <tr>
   <td colname="col1"> qlog.dll </td>
   <td colname="col2"> Il modulo di raccolta (un filtro ISAPI). </td>
  </tr>
  <tr>
   <td colname="col1"> TestExperiment.xls </td>
   <td colname="col2"> <p>File di foglio di calcolo Excel che gli architetti possono utilizzare per configurare un esperimento controllato. </p> <p>Il sensore non utilizza questo file. </p> </td>
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
>Il pacchetto di installazione contiene un file di foglio di calcolo denominato TestExperiment.xls. Questo foglio di calcolo è uno strumento utilizzato dagli architetti per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se è possibile scegliere di farlo). È invece possibile copiare il file in un percorso in cui gli architetti possono accedervi o semplicemente estrarre il file dal pacchetto di installazione, in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati da Insight.

## Modifica il file di configurazione Sensor {#section-1e1590a92222430e92066292512ae0df}

Il file txlogd.conf contiene i parametri di configurazione per Sensor.

È necessario modificare il file per specificare, tra l’altro, le dimensioni della coda del disco, l’indirizzo di Insight Server e l’ID che verrà allegato ai dati prodotti da questo sensore. Il file di configurazione contiene i parametri richiesti e i parametri facoltativi.

* **I** parametri richiesti sono impostazioni che è necessario specificare quando si installa Sensor. Senza queste impostazioni, il sensore non viene eseguito correttamente.
* **I** parametri facoltativi sono impostazioni predefinite per valori predefiniti (che è possibile modificare) o per l&#39;abilitazione di funzionalità facoltative.

**Per modificare il file di configurazione Sensor**

1. Apri il file `<SensorDirectory>/txlogd.conf` in un editor di testo e imposta i parametri richiesti ed eventuali parametri facoltativi desiderati.

   Per le descrizioni dei parametri [!DNL txlogd.conf], consulta [Parametri del file Sensor Txlogd.conf](../../../home/c-snsr-ovrvw/sensor-txlogd-params/sensor-txlogd-params.md#concept-4bb629f058894b4abc65a31eb02eebed).

1. Salva e chiudi il file.

## Avviare il trasmettitore e creare la coda del disco {#section-2b8dfd06996d4ab49998eeb99bd9f5f0}

Dopo aver configurato il file [!DNL txlogd.conf]è possibile avviare il programma del trasmettitore, registrarlo come servizio Windows e creare la coda del disco.

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

   >[!NOTE]
   >
   >Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

   1. Nel riquadro a sinistra della finestra Visualizzatore eventi selezionare il registro Applicazioni.
   1. Nel riquadro a destra, cerca gli eventi con &quot;Adobe&quot; nella colonna Origine.
   1. Se si trova un errore da &quot;Adobe&quot;, fare doppio clic sull&#39;errore per visualizzare la finestra Proprietà evento. Questa finestra fornisce informazioni dettagliate sull’errore.

1. Al termine dell&#39;esame del registro Applicazioni, chiudere il Visualizzatore eventi.
1. Verificare che il trasmettitore abbia creato la coda del disco (Diskq2008.log) nella directory in cui sono stati installati i file del programma Sensor e che si tratti della dimensione specificata nel parametro QueueSize nel file txlogd.conf.

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

## Aggiungi il raccoglitore al server web {#section-088960c986cf449cb712152298b3518d}

Per IIS, il raccoglitore è un filtro ISAPI aggiunto al server Web in IIS.

1. Apri IIS Manager utilizzando **Start > Strumenti di amministrazione > Internet Information Services (IIS) Manager**.
1. Espandi i nodi **Computer locale** e **Sites**.
1. Seleziona il sito web e fai doppio clic su **Filtri ISAPI** nel riquadro a destra.
1. Nel riquadro **Azioni** fare clic su **Aggiungi**.

1. Nel campo **Nome filtro** , immetti un nome visualizzato per il filtro. Il nome del filtro suggerito è &quot;Sensor&quot;.
1. Fare clic su **Sfoglia**, selezionare il file qlog.dll (che si trova nella directory in cui è installato Sensor), quindi fare clic su **OK**.

1. Fai clic su **OK** per aggiungere il filtro.

   Dopo aver aggiunto il filtro, il raccoglitore è immediatamente operativo e pronto per raccogliere i dati.

Se la freccia verde non viene visualizzata dopo il flusso del traffico verso il raccoglitore, completa i seguenti passaggi:

1. Fai clic su Start > Strumenti di amministrazione > Visualizzatore eventi per verificare la presenza di errori nel Visualizzatore eventi.

   >[!NOTE]
   >
   >Questa sequenza di comandi può variare a seconda della versione di Windows in uso.

1. Nel riquadro a sinistra della finestra Visualizzatore eventi, selezionare il registro **Applicazione**.
1. Nel riquadro a destra, cerca gli eventi con &quot;Adobe&quot; nella colonna **Origine**.
1. Se si verifica un errore, fare doppio clic sull&#39;errore per visualizzare la finestra **Proprietà evento**.

## Acquisire dati aggiuntivi {#section-98db9625efdc4b60bfd76f7adf4af74d}

Le pagine web sono spesso strutturate utilizzando il linguaggio di programmazione ASP (Active Server Pages).

ASP è una tecnologia Microsoft in esecuzione in IIS. Quando un browser richiede un file ASP, IIS passa la richiesta al motore ASP. Il motore ASP legge il file ASP, riga per riga ed esegue gli script nel file. Infine, il file ASP viene restituito al browser come HTML normale. ASP fornisce oggetti RESPOND o REQUEST che, oltre ad altre utilità, consentono la risposta o la richiesta di query utente o dati inviati da moduli HTML.

In alcuni casi, è possibile che non si desideri aggiungere i valori immessi nei moduli all’URL visualizzato nella barra degli indirizzi del browser di un utente o visualizzabile all’interno del codice HTML stesso. Uno script ASP semplice lato server consente di aggiungere al file di registro i nomi dei campi del modulo e i relativi valori senza renderli disponibili nel browser dell’utente o incorporarli nel file HTML. Per acquisire i valori effettivi del modulo immessi in particolari moduli all’interno del sito web, è necessario aggiungere alcune righe di codice per aggiungere i valori del modulo alla richiesta di registro.

Nella pagina di elaborazione di un modulo, includere il codice seguente per aggiungere i valori del modulo immesso ai dati della richiesta (oltre a scrivere i valori del modulo inviato in un database esterno o in un altro percorso):

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

Questo processo aggiunge i valori del modulo come definiti ai dati della richiesta per la pagina Elaborazione del modulo. All’interno dei dati di registro, i valori aggiunti sarebbero disponibili come stringhe di query nella pagina Elaborazione modulo, come illustrato di seguito. Ad esempio, v_1, v_2, v_3 e v_4 sono stringhe di query contenenti i dati immessi nei campi modulo appropriati. La sintassi descritta nell’esempio precedente può essere duplicata per tutti i campi e i valori modulo aggiuntivi che si desidera acquisire:

```
https://www.myserver.com/path/to/formprocessingpage.asp?v_1=John+Smith&v_2=Los+Angeles&v_3=California&v_4=90210
```

Se si desidera acquisire e rendere disponibili per l’analisi tutti i campi e i valori del modulo, è possibile utilizzare la sintassi seguente:

```
var formvalues = Response.Form;
Response.AppendToLog(formvalues);
```

Questo esempio prende tutti i campi modulo presenti all’interno di HTML insieme ai rispettivi valori e li aggiunge come stringhe di query alla voce di registro per la pagina Elaborazione modulo. Tieni presente che questo includerebbe tutti i campi nascosti presenti all’interno del modulo.

I dati del registro vengono aumentati come descritto nella tabella seguente:

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_1 | Valore associato alla stringa di query NAME | v_1=John Smith |
| v_2 | Valore associato alla stringa di query CITY | v_2=Los Angeles |
| v_3 | Valore associato alla stringa di query STATE | v_3=California |
| v_4 | Valore associato alla stringa di query ZIP | v_4=90210 |

<!-- <a id="section_55C623AC973246DC9EBECD48DA1EE0F7"></a> -->
