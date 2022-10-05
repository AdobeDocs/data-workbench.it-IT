---
description: Istruzioni per l'installazione e la configurazione di Sensor per Sun Java System Application Server Standard Edition 7 in esecuzione in Windows Server 2000 o versione successiva.
title: Sun Java Server su Windows Server 2000 o versione successiva
uuid: 43f3eee0-2633-4bda-af6c-6c15433dd539
exl-id: 33f24073-8eff-4bf6-8f83-7a122d1505d8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '956'
ht-degree: 1%

---

# Sun Java Server su Windows Server 2000 o versione successiva{#sun-java-server-on-windows-server-or-later}

{{eol}}

Istruzioni per l&#39;installazione e la configurazione di Sensor per Sun Java System Application Server Standard Edition 7 in esecuzione in Windows Server 2000 o versione successiva.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponi già del file di installazione di Sensor per il tuo particolare server web, scaricalo (o ottenerlo dal tuo rappresentante di Adobe) prima di iniziare le seguenti procedure.

Sensor supporta i seguenti server in esecuzione in RedHat Linux 7.x o successivo o Sun Solaris SPARC 2.6 o successivo:

Per installare e configurare Sensor, devi eseguire le seguenti operazioni:

## Installare i file del programma {#section-2f3e85083b4f4aa989a85997330e86ae}

Procedura per estrarre e installare i file di programma per Sensor sul server.

1. Su Netscape Enterprise, iPlanet, Sun ONE o Sun Java System Server, creare una directory in cui installare i file del programma Sensor. Tenere presente che la coda del disco si trova in questa directory, quindi assicurarsi che il dispositivo scelto abbia spazio sufficiente per contenere una coda delle dimensioni necessarie.

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
   <td colname="col1"> saf_visual_sciences.dll </td> 
   <td colname="col2"> Modulo di caricamento del raccoglitore. </td> 
   <td colname="col3"> <i>/usr/local/aolserver/ visual_sciences</i> </td> 
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

1. Per confermare che il trasmettitore è in esecuzione correttamente, fai clic su Start > Pannello di controllo Campaign > Strumenti di amministrazione > Servizi. Nell&#39;elenco dei servizi, individuare la voce per Sensor e confermare che il suo stato è Avviato e che il suo tipo di avvio è Automatico. Quindi chiudere il pannello di controllo Servizi.
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

## Modificare lo script di avvio {#section-19a38f27c9f44adf88f8910f5ed483a3}

Nel file init.conf (ad esempio, C:\Sun\AppServer7\domains\domain1\server1\config\ init.conf), aggiungi le seguenti righe alla fine del file:

```
Init fn="load-modules" shlib="C:/VisualSciences/saf_visual_sciences.dll" 
funcs="vys-cookie,vys-log,vys-init,vys-content-type" 
Init fn="vys-init" config-file="C:/VisualSciences/txlogd.conf"
```

Nel file obj.conf (ad esempio, C:\Sun\AppServer7\domains\domain1\server1\config\ server1-obj.conf), aggiungi le seguenti righe direttamente sotto il `<Object name="default">` linea:

```
NameTrans fn="vys-cookie" 
ObjectType fn="vys-content-type" 
AddLog fn="vys-log"
```
