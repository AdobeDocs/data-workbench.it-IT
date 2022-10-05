---
description: Per rilevare gli errori del sensore il prima possibile e ripararli prima che causino problemi o interruzioni importanti, è necessario monitorare regolarmente i log eventi.
title: Monitoraggio degli eventi amministrativi (sensore)
uuid: c43d6509-6950-4436-8d6c-be7b00664f05
exl-id: 70894074-b8aa-4f6c-87d1-d0403f4c3319
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1093'
ht-degree: 0%

---

# Monitoraggio degli eventi amministrativi{#monitoring-administrative-events}

{{eol}}

Per rilevare gli errori del sensore il prima possibile e ripararli prima che causino problemi o interruzioni importanti, è necessario monitorare regolarmente i log eventi.

**Frequenza consigliata:** Almeno ogni ora

È possibile monitorare questi eventi utilizzando il file Visualizzatore eventi di Windows o Unix Syslog e [!DNL *.sensor-log] i file che si trovano per impostazione predefinita in [!DNL Logs] nella cartella [!DNL Sensor] directory di installazione. Questi file indicano la presenza di errori durante la raccolta dei dati, soprattutto se [!DNL Sensor] impossibile connettersi alla destinazione [!DNL data workbench server] e inizia a mettere in coda i dati.

## Monitoraggio degli eventi in Windows {#section-7c0443a356af4381bf22259654f5cd17}

Il sensore registra gli errori nel Registro applicazioni del Visualizzatore eventi di Windows con un&#39;origine di &quot;Adobe&quot;.

I messaggi vengono registrati come &quot;Informazioni&quot;, &quot;Avviso&quot; o &quot;Errore&quot; a seconda della loro gravità.

**Per aprire il Visualizzatore eventi di Windows**:

* Fai clic su **Start > Pannello di controllo Campaign > Strumenti di amministrazione > Visualizzatore eventi**.

## Monitoraggio di eventi su Unix {#section-5de3947891fb47ac88b7c855e545d54a}

Il sensore registra gli errori nel [!DNL syslog] daemon.

Il daemon syslog scrive i messaggi di errore nei file di log in base alle regole specificate nel file syslog.conf. Gli errori vengono registrati con i flag &quot;LOG_DAEMON&quot; e &quot;LOG_NOTICE&quot; o &quot;LOG_ERR&quot;, a seconda della gravità.

**Per aprire il registro di sistema Unix**

Il registro di sistema Unix si trova in genere in [!DNL /var/adm/messages] o [!DNL /var/log/messages].

Individua il percorso appropriato e apri il registro di sistema.

## Informazioni sui formati dei messaggi {#section-a0899add30fd4b2da58a23b9e3324693}

Tutti i messaggi Sensor contengono la stringa &quot;Sensor&quot; e sono numerati per riflettere l&#39;importanza della visualizzazione del messaggio.

| Numero messaggio | Significato del messaggio | Stringa messaggio |
|---|---|---|
| 1xxx | Informativo | Info sensore # |
| 2 xxx | Avvertenza | N. avviso sensore |
| 3xxx | Errore di configurazione | Errore sensore # |
| 4xxx | Errore operativo | Errore sensore # |
| 5xxx | Errore interno | Errore sensore # |

>[!NOTE]
>
>Gli avvisi (2xxx) non sono attualmente in uso. Questi numeri sono riservati per utilizzi futuri.

Il tuo strumento di gestione della rete può essere impostato per monitorare i tuoi messaggi ogni 5-10 minuti per gli errori con la sorgente &quot;Sensor&quot; e avvisare il personale appropriato sui problemi che possono richiedere l&#39;intervento. Puoi scegliere di monitorare il sistema solo per alcuni tipi di messaggi Evento, ad esempio la stringa &quot;Errore sensore&quot;. In alternativa, puoi applicare regole diverse agli eventi con le stringhe &quot;Sensor Info&quot;, &quot;Sensor Warning&quot; e &quot;Sensor Error&quot; (Informazioni sensore).

## Identificazione di messaggi importanti {#section-5a20f5dc18ca4012931d194db855e54e}

All’interno dei registri eventi, devi prestare particolare attenzione ai messaggi relativi alle dimensioni della coda e inviarli immediatamente.

Ad esempio, messaggi come &quot; [!DNL Sensor Info 1012: Adobe disk queue is #% full]&quot;Ho bisogno di attenzione.

## Risposta ai messaggi evento del sensore {#section-0004c4a169dc4a8882d9bd87dd326ad4}

Tabelle che descrivono gli eventi Sensor e le azioni suggerite per le piattaforme web server supportate.

**Tutte le piattaforme**

<table id="table_F8835AC0AD8F43E2B4494D8D35EBC0FD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Messaggio evento </th> 
   <th colname="col2" class="entry"> Azione consigliata </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Informazioni sensore 1010: Sensore inizializzato. </td> 
   <td colname="col2"> Non è richiesta alcuna azione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Info sensore 1011: Sensore terminato. Totale clic in coda ## </td> 
   <td colname="col2"> Non è richiesta alcuna azione. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni sensore 1012: La coda del disco di Adobe è piena #% </td> 
   <td colname="col2"> Questo messaggio viene registrato ogni volta che l'utilizzo della coda del disco supera una soglia del 10%. Se questa percentuale continua a crescere, è necessario intervenire prima che la coda sia piena e i dati vadano persi. Il problema più probabile è che il sensore abbia smesso di comunicare con Insight Server. Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Info sensore 1013: Configurazione del sensore modificata </td> 
   <td colname="col2"> Non è richiesta alcuna azione. Il sensore ha rilevato una modifica in uno dei suoi file di configurazione e si ricaricherà. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Info sensore 1014: Problema durante il seeding del generatore di numeri casuali </td> 
   <td colname="col2"> Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni sensore 1016: Nome file di configurazione caricato </td> 
   <td colname="col2"> Non è richiesta alcuna azione. Il sensore ha caricato correttamente il file di configurazione elencato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni sensore 1017: Nome file di esperimento caricato </td> 
   <td colname="col2"> Non è richiesta alcuna azione. Il sensore ha caricato correttamente il file dell'esperimento elencato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 3016: Impossibile caricare il file di configurazione /mypath/myfile </td> 
   <td colname="col2"> Verifica che esista il file di configurazione Sensor specificato nella configurazione del server web e che disponga delle autorizzazioni necessarie per essere letto dal processo del server web. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensore 3017: Impossibile caricare il file di configurazione dell'esperimento controllato /mypath/myfile </p> </td> 
   <td colname="col2"> <p>Verifica che esista il file sperimentale controllato specificato in txlogd.conf e che il processo txlogd disponga delle autorizzazioni necessarie per leggere il file. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 3018: Impossibile analizzare gli elenchi dei filtri del contenuto. Controlla il file di configurazione txlogd </td> 
   <td colname="col2"> Verifica la sintassi delle voci ContentFilterInclude e ContentFilterExclude in txlogd.conf. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 3023: Impossibile creare il blocco (g_lockThrottle) </td> 
   <td colname="col2"> Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 3024: Impossibile creare il blocco (g_lockConfigCheck) </td> 
   <td colname="col2"> Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 4014: Impossibile aprire la coda del disco. </td> 
   <td colname="col2"> Verifica il nome del file QueueFile in txlogd.conf e, se ritenuto corretto, contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 4020: File non in coda </td> 
   <td colname="col2"> Verifica il nome del file QueueFile in txlogd.conf e, se ritenuto corretto, contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 4021: La coda è piena </td> 
   <td colname="col2"> Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 4022: Impossibile mappare il blocco di memoria di lunghezza &lt;x&gt; offset &lt;y&gt; </td> 
   <td colname="col2"> Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5012: Impossibile creare mutex. </td> 
   <td colname="col2"> Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5013: Impossibile acquisire mutex. </td> 
   <td colname="col2"> Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5030: Errore di forchetta. </td> 
   <td colname="col2"> Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5031: setsid non riuscito. </td> 
   <td colname="col2"> Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5032: Errore di forchetta. </td> 
   <td colname="col2"> Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5033: chdir non è riuscito. </td> 
   <td colname="col2"> Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5034: Segnale ricevuto </td> 
   <td colname="col2"> È probabile che il programma sia stato terminato da un segnale esterno. Se non è possibile determinare l'origine del segnale, contatta l'assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5035: Uscita chiamata dall'esterno principale </td> 
   <td colname="col2"> Contatta l’Assistenza clienti Adobe. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Errore sensore 5036: txlogd è già in esecuzione </td> 
   <td colname="col2"> Un'altra istanza del daemon txlogd è già in esecuzione. Interrompi prima l'altra istanza se desideri eseguirne una nuova. </td> 
  </tr> 
 </tbody> 
</table>

**Server HTTP Apache/IBM**

| Messaggio evento | Azione consigliata |
|---|---|
| Errore sensore 3015: Direttiva VisualSciencesConfig mancante in httpd.conf. | Errore di configurazione. La direttiva VisualSciencesConfig deve essere in httpd.conf con un parametro che rappresenta la posizione di txlogd.conf. |
| Errore sensore 3019: vys-cookie non chiamato prima di vys-log. Contattare il supporto tecnico. | Contatta l’Assistenza clienti Adobe. |
| Errore sensore 3025: La sottorichiesta fa riferimento a se stessa | Contatta l’Assistenza clienti Adobe. |

**Server AOL**

| Messaggio evento | Azione consigliata |
|---|---|
| Errore sensore 3015: ns/server/[server]/module/[modulo] sezione mancante nel file di configurazione AOLServer. | Errore di configurazione. Correggi come indicato in errore. |
| Errore sensore 3019: vys-cookie non chiamato prima di vys-log. Contattare il supporto tecnico. Contatta l’Assistenza clienti Adobe. | Contattare il supporto tecnico. Contatta l’Assistenza clienti Adobe. |
| Errore sensore 3020: VisualSciencesConfig mancante come prima voce in [sezione] nel file di configurazione di AOLServer. | Errore di configurazione. Correggi come indicato in errore. |
| Errore sensore 3021: Valore mancante in VisualSciencesConfig [sezione] nel file di configurazione di AOLServer. | Errore di configurazione. Correggi come indicato in errore. |

**Server web di sistema iPlanet e Java**

| Messaggio evento | Azione consigliata |
|---|---|
| Errore sensore 3011: È necessaria la direttiva Init. Come Init fn=vys-init config-file=&quot;/mypath/myfile&quot; | Errore di configurazione. La direttiva iPlanet init è mancante. |
| Errore sensore 3015: config-file non specificato nella direttiva iPlanet Init | Errore di configurazione. Il percorso del file di configurazione non è stato fornito nella direttiva iPlanet Init. |
| Errore sensore 3019: vys-cookie non chiamato prima di vys-log. Controlla il file di configurazione | vys-cookie deve essere specificato come prima direttiva NameTrans per ogni server virtuale software. |
