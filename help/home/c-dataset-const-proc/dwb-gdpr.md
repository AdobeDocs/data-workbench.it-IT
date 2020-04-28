---
description: Adobe Data Workbench fornisce strumenti e processi per preparare i dati in modo che siano conformi alle General Data Protection Regulations (GDPR).
solution: Analytics
title: Supporto di Workbench dati per GDPR
topic: Data workbench
translation-type: tm+mt
source-git-commit: 89a17210bb6f941309b283e54aa8485c5e823595

---


# Supporto di Workbench dati per GDPR

Adobe Data Workbench fornisce strumenti e processi per preparare i dati in modo che siano conformi al [!DNL General Data Protection Regulations] (GDPR).

Come tutte le soluzioni Adobe Analytics, Workbench dati fornisce supporto per il GDPR fornendo pulizia, eliminazione ed etichettatura delle variabili analitiche durante l&#39;elaborazione del feed di dati di Adobe Analytics. Per supportare le implementazioni GDPR, Adobe consente di configurare i processi per il GDPR in conformità con le autorizzazioni aziendali stabilite nel contratto con Adobe. Per ulteriori informazioni, consulta [Adobe Analytics e GDPR](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html).

Il regolamento GDPR identifica i ruoli e gli obblighi dei diversi soggetti responsabili dell&#39;abilitazione al GDPR (vedi [GDPR e Your Business](https://www.adobe.com/it/privacy/general-data-protection-regulation.html)).

* La tua organizzazione agisce come **titolare del trattamento** dei dati per determinare il contesto e la conservazione dei dati personali in base alle tue esigenze e limitazioni. Adobe quindi elabora e memorizza tali dati per conto dell&#39;utente.
* Adobe funge da **elaboratore** dati per fornire software e servizi per l&#39;implementazione dei requisiti GDPR in base all&#39;accordo con Adobe.
* Dopo l&#39;integrazione di Workbench dati con il servizio GDPR e secondo gli standard GDPR, i visitatori di un sito (i soggetti **dei** dati) possono esercitare il loro &quot;diritto di essere dimenticati&quot; da Adobe, il processore dei dati. Per ottenere il diritto di essere dimenticati, il controller dei dati può caricare gli ID visitatore contestati in Adobe da un’interfaccia utente o da un’API. Per ulteriori informazioni, consulta la documentazione sul flusso di lavoro [GDPR di](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) Adobe Analytics, inclusa la sezione relativa alle richieste [di](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) invio ed eliminazione di accesso.

>[!Note]
>
>Per altre origini dati, la tua organizzazione sarà responsabile della pulizia degli ID visitatore contestati da altre origini log, come CRM, POS, IVR e altre origini dati non utilizzate. I pacchetti di servizi con ambito personalizzato saranno disponibili per fornire supporto alle organizzazioni, _fornendo un set completo di file sostitutivi per ogni origine_ dati o altre opzioni personalizzate.

## Aggiornamento di DWB per l’implementazione GDPR

Consulenza consiglierà sul pacchetto di servizi appropriato per rendere conformi le implementazioni esistenti. Per ulteriori informazioni, contattare il Customer Success Manager (CSM).

Se necessario:

* [Eseguire l&#39;aggiornamento alla versione](https://docs.adobe.com/content/help/en/data-workbench/using/release-notes/release-notes.html) più recente di Workbench dati. Per garantire la massima sicurezza, nelle versioni DWB 6.7 sono stati aggiunti nuovi certificati e nuove funzioni di sicurezza, necessari per l&#39;integrazione con GDPR.
* Se si utilizzano i registri eventi TSV Analytics precedenti, eseguire l&#39;aggiornamento al feed [dati](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)Avro.
* Se si utilizza un UCP legacy (Unified Customer Process) con Transform per aggiornare i log esistenti, eseguire l&#39;aggiornamento al processo corrente. Il processo aggiornato genera direttamente un file di ricerca master per la mappatura degli ID visitatore tra le origini.
* Standardizzare il flusso di dati per soddisfare il servizio GDPR.
* Stabilire un pacchetto di servizi con ambito personalizzato per gestire altre origini di registro come CRM, POS, IVR e altre origini dati non elaborate.
* Conferma il periodo predefinito di conservazione dei dati di almeno 25 mesi nel contratto Analytics.
