---
description: Adobe Data Workbench fornisce strumenti e processi per preparare i tuoi dati in modo che siano conformi alle normative generali sulla protezione dei dati (RGPD).
title: Supporto di Data Workbench per il RGPD
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 4%

---

# Supporto di Data Workbench per il RGPD

Adobe Data Workbench fornisce strumenti e processi per preparare i tuoi dati in modo che siano conformi al [!DNL General Data Protection Regulations] (RGPD).

Come tutte le soluzioni Adobe Analytics, Data Workbench fornisce supporto per il RGPD fornendo pulizia, eliminazione ed etichettatura delle variabili analitiche durante l’elaborazione del feed di dati di Adobe Analytics. Per supportare le implementazioni RGPD, l’Adobe ti consente di impostare i processi per il RGPD in conformità con le autorizzazioni della tua azienda, come stabilito nel tuo accordo con Adobe. Per ulteriori informazioni, consulta [Adobe Analytics e RGPD](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-overview.html?lang=it).

Il regolamento RGPD identifica i ruoli e gli obblighi delle diverse parti responsabili dell’abilitazione all’RGPD (consulta [RGPD e la tua azienda](https://www.adobe.com/it/privacy/general-data-protection-regulation.html)).

* La tua organizzazione agisce come **titolare del trattamento dei dati** per determinare il contesto e la conservazione dei dati personali in base alle tue esigenze e limitazioni. L&#39;Adobe elabora e archivia tali dati per tuo conto.
* L&#39;Adobe agisce come **responsabile del trattamento dei dati** per fornire il software e i servizi necessari per implementare i requisiti RGPD in base all&#39;accordo stipulato con l&#39;Adobe.
* Dopo l&#39;integrazione della Data Workbench con il servizio RGPD e in conformità agli standard RGPD, i visitatori di un sito (i **soggetti dei dati**) possono esercitare il loro &quot;diritto all&#39;oblio&quot; ad Adobe, il responsabile del trattamento dei dati. Per ottenere il diritto di essere dimenticati, in qualità di titolare del trattamento dei dati puoi caricare su Adobe gli ID visitatore contestati da un’interfaccia utente o API. Per ulteriori informazioni, consulta la documentazione [Flusso di lavoro RGPD per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/an-gdpr-workflow.html?lang=en) , inclusa la sezione [invia richieste di accesso e cancellazione](https://experienceleague.adobe.com/docs/analytics/admin/data-governance/gdpr-submit-access-delete.html) .

>[!NOTE]
>
>Per altre origini dati, la tua organizzazione sarà responsabile della pulizia degli ID visitatore contestati da altre origini di registro, come CRM, POS, IVR e altre origini dati non elaborate. I pacchetti di servizi con ambito personalizzato saranno disponibili per fornire supporto alle organizzazioni _fornendo un set completo di file sostitutivi per ogni origine di dati_ che i rivenditori di servizi in corso sono tenuti a supportare o mantenere.

## Aggiornamento di DWB per l’implementazione RGPD

Consulting ti consiglierà il pacchetto di servizi appropriato per rendere conformi le implementazioni esistenti. Contatta il tuo Customer Success Manager (CSM) per ulteriori informazioni.

Se necessario:

* [Effettua l’aggiornamento alla ](https://experienceleague.adobe.com/docs/data-workbench/using/release-notes/release-notes.html) versione più recente di Data Workbench. Per garantire la massima sicurezza, nelle versioni DWB 6.7 sono stati aggiunti nuovi certificati e funzioni di sicurezza necessari per l’integrazione RGPD.
* Se utilizzi i registri eventi TSV Analytics legacy, effettua l’aggiornamento al [feed dati Avro](https://experienceleague.adobe.com/docs/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Se utilizzi un UCP legacy (Unified Customer Process) con Transform per aggiornare i log esistenti, effettua l’aggiornamento al processo corrente. Il processo aggiornato genera direttamente un file di ricerca principale per la mappatura degli ID visitatore tra le origini.
* Standardizzare il flusso di dati per adattarlo al servizio RGPD.
* Stabilisci un pacchetto di servizi con ambito personalizzato per gestire altre origini di registro come CRM, POS, IVR e altre origini dati non elaborate.
* Conferma il periodo predefinito di conservazione dei dati di 25 mesi o più nel contratto Analytics.
