---
description: Segui questi passaggi per avviare il processo di onboarding per Adobe Data Workbench (DWB), un componente di Adobe Analytics Premium (AAP).
title: Istruzioni di configurazione di base per DWB Managed Services
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
exl-id: 49fb6afe-b417-4554-9238-fd6381c00029
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '922'
ht-degree: 2%

---

# Istruzioni di configurazione di base per DWB Managed Services{#basic-onboarding-instructions-for-dwb-managed-services}

Segui questi passaggi per avviare il processo di onboarding per Adobe Data Workbench (DWB), un componente di Adobe Analytics Premium (AAP).

Queste istruzioni di onboarding sono per i clienti che implementano Data Workbench con una singola suite di rapporti utilizzando i servizi gestiti di Adobe senza servizi di consulenza. Se sei un nuovo cliente AAP che implementa DWB, il team di onboarding Adobe sarà il tuo contatto iniziale. Se esegui l’aggiornamento da Adobe Analytics standard o da una versione precedente di DWB, sarà disponibile un Adobe di Customer Success Manager .

## Informazioni di onboarding: Di cosa abbiamo bisogno da te {#section-bdeb9aa26dc14e45a6c90920832becaa}

L’Adobe ti contatterà per:

* Identifica un utente primario per DWB per generare un certificato specifico per tale utente nella directory di rete. L’utente principale fungerà anche da persona ideale per interagire con l’Assistenza clienti di Adobe.
* Identifica la suite di rapporti da caricare in DWB.

I team Adobe di Digital Marketing prenderanno quindi le tue informazioni per creare profili, impostare account e distribuire un file di configurazione per DWB.

**Attività di onboarding di Adobe**

* L’Assistenza clienti Adobe crea un account con licenza DWB. Adobe Customer Care genera un certificato DWB per l’utente principale.
* L’Assistenza clienti Adobe definisce l’utente principale come &quot;utente supportato&quot;, la persona identificata per le chiamate supportate e la risoluzione dei problemi.
* L’Assistenza clienti Adobe carica il pacchetto software sul portale di licenza e software DWB (profilo SoftDocs/Software e Docs) da scaricare nella tua organizzazione.
* Il team TechOps di Adobe prepara gli ambienti di produzione e sviluppo e i relativi profili (per contratto) per DWB.
* Il team TechOps di Adobe configura i feed di dati e gli script di gestione del profilo.
* Il team TechOps di Adobe crea e invia il file di configurazione DWB (Insight.cfg) al team di onboarding Adobe responsabile delle attività di onboarding associate alla tua organizzazione.

Dopo aver personalizzato i feed di dati e aver generato credenziali, certificati e una configurazione di profilo, l’Assistenza clienti Adobe invierà il file di configurazione e le credenziali per effettuare il passaggio successivo.

## Accedere ai file di installazione personalizzati {#section-26962bf57fef435dbd1c5486d4b6f688}

Riceverai questi file di installazione dall’Assistenza clienti Adobe per installare la workstation DWB sul computer client.

* Il file di configurazione DWB personalizzato (Insight.cfg)

   Questo file di configurazione sul computer client includerà le connessioni ai server DWB gestiti.

* Accedi alle credenziali del portale licenze per scaricare la Configurazione guidata DWB e il certificato richiesto (file .pem) con il nome dell&#39;utente principale.

**Download di file di configurazione aggiuntivi**

1. Vai a: license.visualsciences.com per scaricare il certificato di licenza ed eseguibile della procedura guidata di installazione DWB.
1. Immetti l’organizzazione (Nome account), il nome dell’utente principale e la password che hai ricevuto dall’Assistenza clienti Adobe, quindi fai clic su accesso.

   >[!NOTE]
   >
   >Il browser potrebbe richiedere la presentazione di un certificato digitale. In questo caso, fare clic su Annulla per chiudere la finestra di dialogo.

1. Individua il certificato rilasciato per la tua istanza di Adobe Data Workbench (`<PrimaryUser>`.pem) nella sezione Download e scarica.
1. Individua il programma di installazione del client standard nella sezione Download per scaricare la procedura guidata di installazione DWB (file InsightSetup-x.xx.exe).
1. Dopo aver ricevuto e scaricato i file da Adobe Customer Care, esegui l&#39;Installazione guidata DWB per installare il software della workstation sul computer client.

>[!NOTE]
La procedura guidata di installazione DWB illustra l’installazione della workstation client DWB e aiuta a individuare i file Insight.cfg e `<PrimaryUser>`.pem da inserire nelle cartelle richieste. Il file Insight.cfg risiede con il file Insight.exe nella workstation client installata. Il file `<PrimaryUser>`.pem si trova nella cartella Certificati con il file trust_ca_cert.pem . Tutti i file di certificato e di configurazione devono essere presenti affinché DWB funzioni.

Per ulteriori informazioni, vedere la [Configurazione guidata DWB](https://experienceleague.adobe.com/docs/data-workbench/using/install/workstation-setup/install-setup.html).

## Connessione ai server DWB {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

I server gestiti sono identificati nel file Insight.cfg ricevuto dall’Assistenza clienti Adobe e risiede nella workstation client. Adobe TechOps configurerà i server e l’Assistenza clienti Adobe aggiungerà al file Insight.cfg i riferimenti a questi server e profili gestiti prima di inviarli. (Il passaggio 12 della documentazione Configurazione guidata DWB verrà completato.)

>[!NOTE]
Nell’area di lavoro Configurazione workstation sulla workstation client DWB, potrai visualizzare i server e i profili collegati.

**Adobe Managed Services**

・ Adobe TechOps gestisce l&#39;infrastruttura, compresi rete, centro dati, server e storage. Il monitoraggio dell&#39;infrastruttura e la risposta agli avvisi si verificano 24 ore su 24, 7 giorni su 7 per gli avvisi che richiedono l&#39;azione TechOps. Per altri avvisi, TechOps avviserà l&#39;Assistenza clienti Adobe di coordinarsi con te.

・ Adobe TechOps eseguirà la manutenzione e gli aggiornamenti del firmware per i server gestiti. Per la manutenzione che causa tempi di inattività, riceverai notifiche relative alla finestra di manutenzione dall’Assistenza clienti con almeno due settimane di anticipo. Adobe TechOps è in grado di soddisfare le esigenze immediate il più rapidamente possibile. La notifica dipenderà dall&#39;urgenza e verrà risolta una volta che il programma sarà noto.

・ Adobe TechOps imposta un&#39;attività pianificata per la gestione automatica dei dati. I dati dei feed Analytics vengono spostati in DWB per l’elaborazione e la trasformazione ogni sera a partire dalle 21:00 ora della suite di rapporti.

・ Adobe TechOps elaborerà altri Adobe Managed Services tra cui backup dei dati, account FTP, archiviazione dei dati e trasferimento dei dati, se necessario.

・ Adobe TechOps configurerà il cluster di produzione principale in modo che contenga tre mesi di dati continui da reimpostare ed elaborare mensilmente. Gli aggiornamenti alle ricerche (Geografia, DeviceAtlas, Classificazioni standard) verranno eseguiti anche nell’ambito dell’attività di rielaborazione. Per impostazione predefinita, l’attività viene eseguita il primo venerdì di ogni mese. Se necessario, la pianificazione può essere modificata dall’Assistenza clienti.

Per ulteriori informazioni, contatta l’ [Adobe Customer Care](https://helpx.adobe.com/support/programs/enterprise-support-terms.html).
