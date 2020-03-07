---
description: Segui questi passaggi per avviare il processo di onboarding per Adobe Data Workbench (DWB), un componente di Adobe Analytics Premium (AAP).
title: Istruzioni di configurazione di base per i servizi gestiti DWB
uuid: ad44a4eb-00ea-49c7-8401-58976d8fe39e
translation-type: tm+mt
source-git-commit: ded50c4eeadea80156c17a4cad985d0ceddd5500

---


# Istruzioni di configurazione di base per i servizi gestiti DWB{#basic-onboarding-instructions-for-dwb-managed-services}

Segui questi passaggi per avviare il processo di onboarding per Adobe Data Workbench (DWB), un componente di Adobe Analytics Premium (AAP).

Queste istruzioni di configurazione sono per i clienti che implementano Workbench dati con una singola suite di rapporti utilizzando i servizi gestiti Adobe senza servizi di consulenza. Se sei un nuovo cliente AAP che implementa DWB, il team Adobe Onboarding sarà il tuo contatto iniziale. Se esegui l’aggiornamento dallo standard Adobe Analytics o da una versione precedente di DWB, un Adobe Customer Success Manager ti fornirà assistenza.

## Informazioni di onboarding: Cosa ci serve da te {#section-bdeb9aa26dc14e45a6c90920832becaa}

Adobe ti contatterà per:

* Identificare un utente principale per DWB per generare un certificato specifico per tale utente nella directory di rete. L&#39;utente principale interagirà anche come persona importante per interagire con l&#39;Assistenza clienti Adobe.
* Identificare la suite di rapporti da caricare in DWB.

I team Adobe Digital Marketing prenderanno quindi le vostre informazioni per creare profili, impostare account e distribuire un file di configurazione per DWB.

**Adobe Onboarding Tasks**

* L&#39;Assistenza clienti Adobe crea un account con licenza DWB. L&#39;Assistenza clienti Adobe genera un certificato DWB per l&#39;utente principale.
* L&#39;Assistenza clienti Adobe definisce l&#39;utente principale come &quot;utente supportato&quot;, la persona identificata per le chiamate supportate e la risoluzione dei problemi.
* L&#39;Assistenza clienti Adobe carica il pacchetto software nel portale della licenza e del software DWB (profilo SoftDocs/Software e Docs) per il download nell&#39;azienda.
* Il team Adobe TechOps prepara gli ambienti di produzione e sviluppo e i loro profili (per contratto) per DWB.
* Il team Adobe TechOps configura i feed di dati e gli script di gestione del profilo.
* Il team Adobe TechOps crea e invia il file di configurazione DWB (Insight.cfg) al team Adobe Onboarding responsabile delle attività di registrazione associate alla tua organizzazione.

Dopo aver personalizzato i feed di dati e generato credenziali, certificati e una configurazione di profilo, l&#39;Assistenza clienti Adobe invierà il file di configurazione e le credenziali per effettuare il passaggio successivo.

## Accesso ai file di installazione personalizzati {#section-26962bf57fef435dbd1c5486d4b6f688}

Questi file di installazione verranno inviati dall&#39;Assistenza clienti Adobe per installare la workstation DWB sul computer client.

* Il file di configurazione DWB personalizzato (Insight.cfg)

   Questo file di configurazione sul computer client includerà le connessioni ai server DWB gestiti.

* Credenziali di accesso per il portale licenze per scaricare la procedura guidata di installazione DWB e il certificato richiesto (file .pem) con il nome dell&#39;utente principale.

**Scaricare altri file di configurazione**

1. Passa a: license.visualsciences.com per scaricare il certificato di licenza ed eseguire la procedura guidata di impostazione DWB.
1. Immettete l&#39;organizzazione (Nome account), il nome dell&#39;utente principale e la password che avete ricevuto dall&#39;Assistenza clienti Adobe, quindi fate clic su Accedi.

   >[!NOTE]
   >
   >Il browser potrebbe richiedere la presentazione di un certificato digitale. In caso contrario, fare clic su Annulla per chiudere la finestra di dialogo.

1. Individua il certificato rilasciato per l’istanza di Adobe Data Workbench (`<PrimaryUser>`.pem) nella sezione Download e scarica.
1. Individuate il programma di installazione client standard nella sezione Download per scaricare la procedura guidata di installazione DWB (file InsightSetup-x.xx.exe).
1. Dopo aver ricevuto e scaricato i file dall&#39;Assistenza clienti Adobe, eseguite la procedura guidata di installazione DWB per installare il software della workstation sul computer client.

>[!NOTE]
DWB Setup Wizard illustra l&#39;installazione della workstation client DWB e spiega come individuare i file Insight.cfg e `<PrimaryUser>`.pem da inserire nelle cartelle richieste. Il file Insight.cfg risiede con il file Insight.exe nella workstation client installata. Il file `<PrimaryUser>`.pem si trova nella cartella Certificati con il file trust_ca_cert.pem. Tutti i file di certificato e di configurazione devono essere presenti affinché DWB funzioni.

Per ulteriori informazioni, consultate Configurazione guidata [](https://docs.adobe.com/content/help/en/data-workbench/using/install/workstation-setup/install-setup.html)DWB.

## Connessione ai server DWB {#section-8e79c4e07c2a4342a5bb8af6ee7be3c9}

I server gestiti sono identificati nel file Insight.cfg ricevuto dall’Assistenza clienti Adobe e risiedono sulla workstation client. Adobe TechOps configurerà i tuoi server e l&#39;Assistenza clienti Adobe aggiungerà al file Insight.cfg i riferimenti a tali server e profili gestiti prima di inviarli. (Le connessioni al server nel passaggio 12 della documentazione di DWB Setup Wizard verranno completate).

>[!NOTE]
Nell&#39;area di lavoro Configurazione workstation della workstation client DWB, potrai vedere i tuoi server e profili connessi.

**Servizi gestiti Adobe**

・ Adobe TechOps gestisce l&#39;infrastruttura, compresi rete, centro dati, server e storage. Il monitoraggio dell&#39;infrastruttura e la risposta agli avvisi si verificano 24 ore su 24, 7 giorni su 7 per gli avvisi che richiedono l&#39;intervento di TechOps. Per altri avvisi, TechOps avviserà l&#39;Assistenza clienti Adobe di coordinarsi con l&#39;utente.

・ Adobe TechOps eseguirà la manutenzione e gli aggiornamenti firmware per i server gestiti. Per la manutenzione che causa tempi di inattività, riceverai notifiche relative alla finestra di manutenzione dall&#39;Assistenza clienti almeno due settimane prima. Adobe TechOps è in grado di soddisfare le esigenze immediate il più rapidamente possibile. La notifica dipenderà dall&#39;urgenza e verrà risolta una volta nota la pianificazione.

・ Adobe TechOps configura un&#39;attività pianificata per la gestione automatica dei dati. I dati dei feed di Analytics vengono spostati in DWB per l&#39;elaborazione e la trasformazione ogni sera a partire dalle 21:00 ora della suite di rapporti.

・ Adobe TechOps elaborerà altri servizi gestiti Adobe, tra cui backup dei dati, account FTP, archiviazione dei dati e trasferimento dei dati, se necessario.

・ Adobe TechOps configurerà il cluster di produzione principale in modo che contenga tre mesi di dati da ripristinare e rielaborare mensilmente. Aggiornamenti alle ricerche (Geografia, DeviceAtlas, Classificazioni standard) verranno eseguiti anche nell&#39;ambito dell&#39;attività di rielaborazione. Per impostazione predefinita, l&#39;attività viene eseguita il primo venerdì di ogni mese. Se necessario, la pianificazione può essere modificata dall&#39;Assistenza clienti.

Per ulteriori informazioni, contatta l’Assistenza [clienti](https://helpx.adobe.com/support/programs/enterprise-support-terms.html)Adobe.
