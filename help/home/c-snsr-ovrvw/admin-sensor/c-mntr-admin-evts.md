---
description: Per rilevare gli errori del sensore il prima possibile e correggerli prima che causino gravi problemi o interruzioni, è necessario monitorare regolarmente i registri eventi.
solution: Analytics
title: Monitoraggio degli eventi amministrativi
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---


# Monitoraggio degli eventi amministrativi{#monitoring-administrative-events}

Per rilevare gli errori del sensore il prima possibile e correggerli prima che causino gravi problemi o interruzioni, è necessario monitorare regolarmente i registri eventi.

**Frequenza consigliata:** Almeno l&#39;ora

Potete monitorare questi eventi utilizzando il file Visualizzatore eventi di Windows o Unix Syslog e i [!DNL *.sensor-log] file che si trovano per impostazione predefinita nella [!DNL Logs] cartella all&#39;interno della directory di [!DNL Sensor] installazione. Questi file indicano la presenza di errori durante la raccolta dei dati, soprattutto se [!DNL Sensor] non è possibile connettersi alla destinazione [!DNL data workbench server] e inizia la coda dei dati.

## Monitoraggio degli eventi in Windows {#section-7c0443a356af4381bf22259654f5cd17}

Il sensore registra gli errori nel registro applicazioni del visualizzatore eventi di Windows con un&#39;origine &quot; Adobe&quot;.

I messaggi vengono registrati come &quot;Informazioni&quot;, &quot;Avvertenza&quot; o &quot;Errore&quot; a seconda della loro gravità.

**Per aprire il visualizzatore** eventi di Windows:

* Fate clic su **Start > Pannello di controllo Campaign > Strumenti di amministrazione > Visualizzatore** eventi.

## Monitoraggio di eventi su Unix {#section-5de3947891fb47ac88b7c855e545d54a}

Sensor registra gli errori nel [!DNL syslog] demone.

Il demone syslog scrive i messaggi di errore nei file di registro in base alle regole specificate nel file syslog.conf. Gli errori vengono registrati con i flag &quot;LOG_DAEMON&quot; e &quot;LOG_NOTICE&quot; o &quot;LOG_ERR&quot;, a seconda della gravità.

**Per aprire il registro di sistema Unix**

Il registro di sistema Unix si trova in genere in [!DNL /var/adm/messages] o [!DNL /var/log/messages].

Individuate il percorso appropriato e aprite il registro di sistema.

## Informazioni sui formati dei messaggi {#section-a0899add30fd4b2da58a23b9e3324693}

Tutti i messaggi Sensor contengono la stringa &quot;Sensor&quot; e sono numerati per riflettere l&#39;importanza del messaggio visualizzato.

| Numero messaggio | Significato del messaggio | Stringa messaggio |
|---|---|---|
| 1xxx | Informazioni | Info sensore # |
| 2xxx | Attenzione | Avvertenza sensore # |
| 3xxx | Errore di configurazione | Errore sensore # |
| 4xxx | Errore operativo | Errore sensore # |
| 5xxx | Errore interno | Errore sensore # |

>[!NOTE]
>
>Le avvertenze (2xxx) non sono attualmente in uso. Questi numeri sono riservati per utilizzi futuri.

Il vostro strumento di gestione della rete può essere impostato per monitorare i messaggi ogni 5-10 minuti per verificare la presenza di errori con la sorgente &quot;Sensor&quot; e avvisare il personale appropriato dei problemi che possono richiedere l&#39;intervento. Potete scegliere di monitorare il sistema solo per alcuni tipi di messaggi di evento, come la stringa &quot;Errore sensore&quot;. In alternativa, è possibile applicare regole diverse agli eventi preceduti dalle stringhe &quot;Sensor Info&quot;, &quot;Sensor Warning&quot; e &quot;Sensor Error&quot;.

## Identificazione di messaggi importanti {#section-5a20f5dc18ca4012931d194db855e54e}

All&#39;interno dei registri eventi, prestare particolare attenzione ai messaggi relativi alle dimensioni della coda e inviarli immediatamente.

Ad esempio, messaggi come &quot; [!DNL Sensor Info 1012: Adobe disk queue is #% full]&quot; richiedono attenzione.

## Risposta ai messaggi dell&#39;evento sensore {#section-0004c4a169dc4a8882d9bd87dd326ad4}

Tabelle che descrivono gli eventi Sensor e le azioni suggerite per le piattaforme server Web supportate.

**Tutte le piattaforme**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Messaggio evento </th> 
   <th colname="col2" class="entry"> Azione suggerita </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Informazioni sensore 1010: Sensore inizializzato. </td> 
   <td colname="col2"> Nessuna azione richiesta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni sensore 1011: Sensore terminato. Totale clic in coda ## </td> 
   <td colname="col2"> Nessuna azione richiesta. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni sensore 1012:  coda disco Adobe è piena #% </td> 
   <td colname="col2"> Questo messaggio viene registrato ogni volta che l'utilizzo della coda del disco supera una soglia del 10%. Se questa percentuale continua a crescere, è necessario intervenire prima che la coda sia piena e i dati vadano persi. Il problema più probabile è che il sensore ha smesso di comunicare con il server di Insight. Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni sensore 1013: Configurazione sensore modificata </td> 
   <td colname="col2"> Nessuna azione richiesta. Il sensore ha rilevato una modifica in uno dei suoi file di configurazione e si ricaricherà. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni sensore 1014: Problema durante la creazione del generatore di numeri casuali </td> 
   <td colname="col2"> Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni sensore 1016: Nome file di configurazione caricato </td> 
   <td colname="col2"> Nessuna azione richiesta. Il sensore ha caricato correttamente il file di configurazione elencato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni sensore 1017: Nome file di prova caricato </td> 
   <td colname="col2"> Nessuna azione richiesta. Il sensore ha caricato correttamente il file dell'esperimento elencato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 3016: Impossibile caricare il file di configurazione /mypath/myfile </td> 
   <td colname="col2"> Verificate che il file di configurazione Sensor specificato nella configurazione del server Web esista e che disponga delle autorizzazioni necessarie per essere letto dal processo del server Web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensore 3017: Impossibile caricare il file di configurazione controllato dell'esperimento /mypath/myfile </p> </td> 
   <td colname="col2"> <p>Verificate che il file di esperimento controllato specificato in txlogd.conf esista e che il processo di test disponga delle autorizzazioni necessarie per leggere il file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 3018: Impossibile analizzare gli elenchi dei filtri del contenuto. Controllare il file di configurazione del testo </td> 
   <td colname="col2"> Verifica la sintassi delle voci ContentFilterInclude e ContentFilterExclude in txlogd.conf. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 3023: Impossibile creare il blocco (g_lockThrottle) </td> 
   <td colname="col2"> Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 3024: Impossibile creare il blocco (g_lockConfigCheck) </td> 
   <td colname="col2"> Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 4014: Impossibile aprire la coda del disco. </td> 
   <td colname="col2"> Verifica il nome del file QueueFile in txlogd.conf e, se ritenuto corretto, contatta  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 4020: Non è un file di coda </td> 
   <td colname="col2"> Verifica il nome del file QueueFile in txlogd.conf e, se ritenuto corretto, contatta  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 4021: Coda piena </td> 
   <td colname="col2"> Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 4022: Impossibile mappare il blocco di memoria di lunghezza &lt;x&gt; all'offset &lt;y&gt; </td> 
   <td colname="col2"> Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5012: Impossibile creare il mutex. </td> 
   <td colname="col2"> Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5013: Impossibile acquisire il mutex. </td> 
   <td colname="col2"> Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5030: Errore forchetta riprodotta. </td> 
   <td colname="col2"> Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5031: setsid non riuscito. </td> 
   <td colname="col2"> Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5032: Errore forchetta riprodotta. </td> 
   <td colname="col2"> Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5033: chdir non riuscito. </td> 
   <td colname="col2"> Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5034: Segnale ricevuto </td> 
   <td colname="col2"> Il programma è stato probabilmente terminato da un segnale esterno. Se non è possibile determinare l'origine del segnale, contattare  ClientCare di Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5035: Uscita chiamata dall'esterno principale </td> 
   <td colname="col2"> Contattare  Adobe ClientCare. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5036: txlogd è già in esecuzione </td> 
   <td colname="col2"> È già in esecuzione un'altra istanza del daemon di tipi. Arrestate prima l'altra istanza se desiderate eseguirne una nuova. </td> 
  </tr> 
 </tbody> 
</table>

**Server HTTP Apache/IBM**

| Messaggio evento | Azione suggerita |
|---|---|
| Errore sensore 3015: La direttiva VisualSciencesConfig non è presente in httpd.conf. | Errore di configurazione. La direttiva VisualSciencesConfig deve essere in httpd.conf con un parametro che corrisponde alla posizione di txlogd.conf. |
| Errore sensore 3019: vys-cookie non è stato chiamato prima di vys-log. Contattare il supporto tecnico. | Contattare  Adobe ClientCare. |
| Errore sensore 3025: Sottoreplica i punti a se stesso | Contattare  Adobe ClientCare. |

**AOL Server**

| Messaggio evento | Azione suggerita |
|---|---|
| Errore sensore 3015: ns/server/[server]/modulo/sezione[modulo] mancante nel file di configurazione AOLServer. | Errore di configurazione. Corretto come indicato in errore. |
| Errore sensore 3019: vys-cookie non è stato chiamato prima di vys-log. Contattare il supporto tecnico. Contattare  Adobe ClientCare. | Contattare il supporto tecnico. Contattare  Adobe ClientCare. |
| Errore sensore 3020: VisualSciencesConfig mancante come prima voce nella sezione della [sezione] nel file di configurazione AOLServer. | Errore di configurazione. Corretto come indicato in errore. |
| Errore sensore 3021: VisualSciencesConfig non contiene un valore nella sezione [sezione] del file di configurazione AOLServer. | Errore di configurazione. Corretto come indicato in errore. |

**Server Web iPlanet e Java System**

| Messaggio evento | Azione suggerita |
|---|---|
| Errore sensore 3011: È richiesta la direttiva Init. Ad esempio Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | Errore di configurazione. Manca la direttiva iPlanet init. |
| Errore sensore 3015: config-file non specificato nella direttiva iPlanet Init | Errore di configurazione. Il percorso del file di configurazione non è stato specificato nella direttiva iPlanet Init. |
| Errore sensore 3019: vys-cookie non è stato chiamato prima di vys-log. Controllare il file di configurazione | vys-cookie deve essere specificato come prima direttiva NameTrans per ogni server virtuale del software. |

