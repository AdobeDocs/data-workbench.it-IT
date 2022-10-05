---
description: Istruzioni dettagliate per l'installazione e la configurazione del sensore per un Apache Server 1.3.x su RedHat Linux 7.x o successivo, SUSE Linux 9.x o successivo, Sun Solaris SPARC 2.6 o successivo, Sun Solaris x86 9 o successivo, FreeBSD 4 o successivo, o Mac OS X PowerPC.
title: Apache Server 1.3.x su Linux, Sun Solaris, FreeBSD o Mac OS X
uuid: bd46dd0f-fe36-4f8b-a87c-8ca7b64da609
exl-id: 087494fb-c8f0-457c-b3db-d9147a739998
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1345'
ht-degree: 2%

---

# Apache Server 1.3.x su Linux, Sun Solaris, FreeBSD o Mac OS X{#apache-server-x-on-linux-sun-solaris-freebsd-or-mac-os-x}

{{eol}}

Istruzioni dettagliate per l&#39;installazione e la configurazione del sensore per un Apache Server 1.3.x su RedHat Linux 7.x o successivo, SUSE Linux 9.x o successivo, Sun Solaris SPARC 2.6 o successivo, Sun Solaris x86 9 o successivo, FreeBSD 4 o successivo, o Mac OS X PowerPC.

I file di programma per Sensor vengono assemblati in un file di installazione ottenuto dal sito di download di Adobe. Se non disponi già del file di installazione di Sensor per il tuo particolare server web, scaricalo (o ottenerlo dal tuo rappresentante di Adobe) prima di iniziare le seguenti procedure.

Per installare e configurare Sensor, devi eseguire i seguenti passaggi di alto livello:

## Installare i file del programma {#section-aae323e252394212bf4096d65fdd280c}

Istruzioni per estrarre e installare i file di programma per Sensor sul computer server.

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

<table id="table_A97CF630633C4543A742D96C302D1138"> 
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
   <td colname="col2"> Modulo di carico del collettore </td> 
   <td colname="col3"> apachePath/libexec </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>txlogd </p> </td> 
   <td colname="col2"> Il programma del trasmettitore </td> 
   <td colname="col3"> <p>/usr/local/bin </p> <p>--O-- </p> <p>/usr/local/sbin </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> txlogd.conf </td> 
   <td colname="col2"> Il file di configurazione Sensor </td> 
   <td colname="col3"> /etc </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trust_ca_cert.pem </td> 
   <td colname="col2"> Certificato utilizzato per convalidare il certificato digitale presentato da Insight Server durante il processo di connessione </td> 
   <td colname="col3"> /usr/local/visual_sciences </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Il pacchetto di installazione contiene un file di foglio di calcolo denominato TestExperiment.xls. Questo foglio di calcolo è uno strumento che gli architetti utilizzano per configurare un esperimento controllato. Il sensore stesso non utilizza questo file, quindi non è necessario installare il file sul computer in cui è in esecuzione Sensor (anche se si può scegliere di farlo). È invece possibile copiare il file in un percorso in cui gli architetti possono accedervi o semplicemente estrarre il file dal pacchetto di installazione, in base alle esigenze. Per ulteriori informazioni sulla sperimentazione controllata, consulta la Guida agli esperimenti controllati da Insight.

**Autorizzazioni sui file del programma**

Autorizzazioni errate sui file di programma causano la maggior parte dei problemi incontrati durante l&#39;installazione di Sensor.

Assicurati di impostare le autorizzazioni esattamente come indicato in questa sezione.

Per impostazione predefinita, i file di programma nel file tar hanno le seguenti autorizzazioni. A seconda della configurazione del sistema, queste impostazioni potrebbero essere modificate (non mascherate) durante l’estrazione dei file. Per ripristinare le autorizzazioni alle impostazioni predefinite consigliate, utilizza i comandi chmod riportati di seguito. Controlla che le directory in cui hai installato i file consentano almeno questo livello di accesso.

| File | Autorizzazioni predefinite | comando chmod |
|---|---|---|
| mod_visual_sciences.so | rwx r-x r-x | chmod 755 |
| txlogd | rwx —x —x | chmod 711 |
| txlogd.conf | rw- rw- r— | chmod 664 |
| trust_ca_cert.pem | rw- rw- r— | chmod 664 |

## Modifica il file di configurazione Sensor {#section-3f22a1c91d7d43b6b4c30f1b7448b17f}

La [!DNL txlogd.conf] il file contiene i parametri di configurazione per Sensor.

È necessario modificare il file per specificare, tra l’altro, le dimensioni della coda del disco, l’indirizzo di Insight Server e l’ID che verrà allegato ai dati prodotti da questo sensore.

Il file di configurazione contiene i parametri richiesti e i parametri facoltativi.

* I parametri richiesti sono impostazioni che è necessario specificare quando si installa Sensor. Senza queste impostazioni, il sensore non viene eseguito correttamente.
* I parametri facoltativi sono impostazioni predefinite per valori predefiniti (che è possibile modificare) o per l’abilitazione di funzionalità facoltative.

Per modificare il file di configurazione Sensor

1. Apri il file /etc/txlogd.conf in un editor di testo e imposta i parametri richiesti ed eventuali parametri facoltativi desiderati.
1. Salva e chiudi il file.

## Avviare il trasmettitore e creare la coda del disco {#section-a453d912ec3d47aa8e40ccacf527119d}

Istruzioni per creare la coda del disco dopo aver configurato il file txlogd.conf.

1. Se la directory in cui si trova la coda del disco non esiste già, crearla. Assicurati che la directory offra sia il modulo di raccolta che il programma del trasmettitore con accesso in lettura/scrittura al file.
1. Sul computer in cui è installato Sensor, eseguire il seguente comando per avviare il trasmettitore:

   ```
   /usr/local/bin/txlogd -ic -f /etc/txlogd.conf
   ```

   * L&#39;opzione &quot;i&quot; in questo comando avvia il trasmettitore in modalità interattiva. Questa modalità visualizza i messaggi del trasmettitore sullo schermo e consente inoltre di interagire con il trasmettitore utilizzando i comandi della tastiera.
   * L&#39;opzione &quot;c&quot; indirizza il trasmettitore a creare la coda del disco.
   * L&#39;opzione &quot;f&quot; specifica la posizione del file di configurazione.

1. Verificare che il trasmettitore abbia creato la coda del disco nella posizione specificata nel parametro QueueFile e delle dimensioni specificate nel parametro QueueSize.
1. Se la coda non è stata creata correttamente, digita Ctrl+C per terminare il trasmettitore, quindi procedi come segue:

   1. Esamina il file txtlogd.conf e verifica che i parametri QueueFile e QueueSize siano impostati correttamente.
   1. Verificare che il dispositivo a cui è assegnata la coda del disco sia operativo e che disponga di spazio sufficiente per contenere un file delle dimensioni specificate nel parametro QueueSize.
   1. Apportare le correzioni necessarie e ripetere la procedura.

## Aggiungere l&#39;agente di raccolta al server Web {#section-a7fb6425956f4f518ae3a7db091b33d2}

Per i server Apache, il raccoglitore è un oggetto dinamico condiviso caricato nel processo del server web.

Per aggiungere il raccoglitore al server web, devi modificare il file httpd.conf come descritto di seguito e riavviare il server web.

Se Sensor acquisisce dati per più server Web sul computer server, è necessario eseguire la procedura seguente per ogni server Web.

1. Utilizzando un editor di testo, apri le [!DNL httpd.conf] file per il server web i cui eventi acquisisce Sensor.
1. Aggiungi le seguenti righe alla fine del file:

   ```
   LoadModule  visual_sciences_module  libexec/mod_visual_sciences.so 
   VisualSciencesConfig  /etc/txlogd.conf 
   AddModule mod_visual_sciences.c
   ```

   >[!NOTE]
   >
   >Queste righe sono sensibili all’uso di maiuscole e minuscole. Digitali esattamente come appaiono sopra.

1. Riavvia il server web. Il raccoglitore viene caricato con il server Web e inizierà a raccogliere i dati dell&#39;evento e a scriverli nella coda del disco.

## Test del sensore {#section-83d9f60b39a6474f9c76bee3e19b2575}

Avvia il trasmettitore e verifica che possa connettersi correttamente a Insight Server e trasmettergli i dati dell’evento.

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
   * La [!DNL ServerAddress] e [!DNL ServerPort] i parametri sono impostati correttamente in [!DNL txtlogd.conf].

   * Se specificato [!DNL ServerAddress] utilizzando un nome server, provare a utilizzare il relativo indirizzo IP numerico. Il valore del [!DNL CertName] Il parametro corrisponde esattamente al nome comune visualizzato nel certificato digitale di Target Insight Server.

## Aggiungi il trasmettitore allo script di avvio del sistema {#section-4e1ffa6e043941ab91411d91d596477a}

Informazioni per garantire che il trasmettitore venga caricato automaticamente al riavvio del server Web.

Aggiungi il seguente comando (che avvia il trasmettitore) allo script di avvio del sistema.

```
/usr/local/bin/txlogd -f /etc/txlogd.conf
```

Questo comando avvia il trasmettitore come un daemon. I messaggi di funzionamento ed errore generati dal trasmettitore vengono scritti nel registro di sistema.

>[!NOTE]
>
>Alcuni utenti di Solaris potrebbero riscontrare un errore di &quot;impossibile acquisire mutex&quot;. Affinché Sensor funzioni correttamente su questi sistemi, è necessario aggiungere o modificare la seguente riga nel file /etc/system:
>
>
```
>semsys:seminfo_semmnu=1024
>```
>
>L&#39;impostazione predefinita di Solaris è 60. In base ai test condotti con Sensor, che utilizza tre semafori per ogni istanza, Adobe consiglia di utilizzare 1024 come impostazione. Questo numero è abbastanza alto da consentire il funzionamento di Sensor insieme a qualsiasi altra applicazione sul server che può richiedere dei semafori, ma non influisce sulle prestazioni. Per sostenere questa raccomandazione, si prega di notare che Adrian Cockcroft ha affermato quanto segue nel suo libro Sun Performance and Tuning (Prentice Hall, ottobre 1994): &quot;I database tendono a utilizzare molte impostazioni di memoria condivisa e semaforo. che non influiscono sulle prestazioni; finché sono abbastanza grandi, i programmi funzioneranno.&quot;
