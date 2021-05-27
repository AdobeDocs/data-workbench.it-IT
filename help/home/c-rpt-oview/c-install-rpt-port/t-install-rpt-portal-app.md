---
description: Report Portal (Portale dei rapporti) è costituito da un set di pagine ASP (application server pages) e file di supporto.
title: Installare i file dell’applicazione del Report Portal (Portale dei rapporti)
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
exl-id: 0eb7805c-d8f6-4cfd-834e-babc1818ebc0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 5%

---

# Installare i file dell’applicazione del Report Portal (Portale dei rapporti){#install-the-report-portal-application-files}

Report Portal (Portale dei rapporti) è costituito da un set di pagine ASP (application server pages) e file di supporto.

Per installare [!DNL Report Portal], è necessario estrarre questi file dal file di distribuzione ricevuto da Adobe e installarli nel computer in cui è in esecuzione Microsoft IIS.

**Per installare i file  [!DNL Report Portal] dell’applicazione**

1. Se non lo hai già fatto, scarica il pacchetto di installazione (.zip file) per [!DNL Report Portal] dal sito FTP di Adobe.
1. Sul computer in cui è in esecuzione IIS, estrarre i file nel pacchetto di installazione in qualsiasi posizione. Questo passaggio installa le seguenti sottocartelle e file nella cartella VSVirtualPortalName .

   | Cartella o file | Descrizione |
   |---|---|
   | [!DNL \data\users.mdb] | Database contenente l&#39;elenco degli utenti [!DNL Report Portal] autorizzati. |
   | [!DNL \PortalASP\] | Cartella contenente i file ASP che compongono [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | Cartella contenente cinque sottocartelle (Core, CSS, HTC, immagini e output) che contengono i file di supporto utilizzati da [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | File di configurazione utilizzato per definire le directory virtuali associate a [!DNL Report Portal] (utilizzato solo con IIS 6.0). |

   La directory ha un aspetto simile al seguente:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >Il nome della directory può essere diverso dal nome mostrato nell’esempio.

1. Rinomina la cartella SVirtualPortalName (o altro nome) in quella che desideri utilizzare come directory virtuale principale del tuo [!DNL Report Portal] (in seguito denominata *PortalName*). Per ulteriori informazioni sulle directory virtuali, consulta la sezione successiva.
