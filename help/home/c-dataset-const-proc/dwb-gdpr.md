---
description: Adobe Data Workbench fornisce strumenti e processi per preparare i tuoi dati in modo che siano conformi alle normative generali sulla protezione dei dati (RGPD).
title: Supporto di Data Workbench per il RGPD
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 4%

---

# Supporto di Data Workbench per il RGPD

{{eol}}

Adobe Data Workbench fornisce strumenti e processi per preparare i dati a rispettare le [!DNL General Data Protection Regulations] (RGPD).

Come tutte le soluzioni Adobe Analytics, Data Workbench fornisce supporto per il RGPD fornendo pulizia, eliminazione ed etichettatura delle variabili analitiche durante l’elaborazione del feed di dati di Adobe Analytics. Per supportare le implementazioni RGPD, l’Adobe ti consente di impostare i processi per il RGPD in conformità con le autorizzazioni della tua azienda, come stabilito nel tuo accordo con Adobe. Vedi [Adobe Analytics e RGPD per ulteriori informazioni](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=it).

Il regolamento RGPD identifica i ruoli e gli obblighi dei diversi soggetti responsabili dell’abilitazione all’RGPD (vedi [RGPD e la tua azienda](https://www.adobe.com/it/privacy/general-data-protection-regulation.html)).

* La tua organizzazione agisce come **titolare dei dati** determinare il contesto e la conservazione dei dati personali in base alle esigenze e ai vincoli dell’utente. L&#39;Adobe elabora e archivia tali dati per tuo conto.
* L&#39;Adobe agisce come **elaboratore dati** fornire il software e i servizi necessari per implementare i requisiti RGPD in base all’accordo stipulato con l’Adobe.
* Dopo l’integrazione della Data Workbench con il servizio RGPD e in conformità agli standard RGPD, i visitatori di un sito (il **soggetti interessati**) può esercitare il loro &quot;diritto all&#39;oblio&quot; per Adobe, il responsabile del trattamento dei dati. Per ottenere il diritto di essere dimenticati, in qualità di titolare del trattamento dei dati puoi caricare su Adobe gli ID visitatore contestati da un’interfaccia utente o API. Consulta la sezione [Flusso di lavoro di Adobe Analytics per il RGPD](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-workflow.html?lang=en) documentazione per ulteriori informazioni, tra cui [invia richieste di accesso ed eliminazione](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-submit-access-delete.html) sezione .

>[!NOTE]
>
>Per altre origini dati, la tua organizzazione sarà responsabile della pulizia degli ID visitatore contestati da altre origini di registro, come CRM, POS, IVR e altre origini dati non elaborate. I pacchetti di servizi con ambito personalizzato saranno disponibili per fornire supporto alle organizzazioni da parte di _fornitura di un set completo di file sostitutivi per ogni origine dati_ che i conservatori del servizio continuativo siano tenuti a supportare o mantenere.

## Aggiornamento di DWB per l’implementazione RGPD

Consulting ti consiglierà il pacchetto di servizi appropriato per rendere conformi le implementazioni esistenti. Contatta il tuo Customer Success Manager (CSM) per ulteriori informazioni.

Se necessario:

* [Aggiornamento alla versione più recente](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) della Data Workbench. Per garantire la massima sicurezza, nelle versioni DWB 6.7 sono stati aggiunti nuovi certificati e funzioni di sicurezza necessari per l’integrazione RGPD.
* Se utilizzi i registri eventi TSV Analytics legacy, effettua l’aggiornamento al [Feed di dati Avro](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Se utilizzi un UCP legacy (Unified Customer Process) con Transform per aggiornare i log esistenti, effettua l’aggiornamento al processo corrente. Il processo aggiornato genera direttamente un file di ricerca principale per la mappatura degli ID visitatore tra le origini.
* Standardizzare il flusso di dati per adattarlo al servizio RGPD.
* Stabilisci un pacchetto di servizi con ambito personalizzato per gestire altre origini di registro come CRM, POS, IVR e altre origini dati non elaborate.
* Conferma il periodo predefinito di conservazione dei dati di 25 mesi o più nel contratto Analytics.
