---
description: Il portale di report è composto da un set di pagine ASP (Application Server Pages) e file di supporto.
solution: Analytics
title: Installare i file dell'applicazione del portale di report
topic: Data workbench
uuid: 483a7401-1bb4-4a71-b8c7-e70ff1b129e7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installare i file dell&#39;applicazione del portale di report{#install-the-report-portal-application-files}

Il portale di report è composto da un set di pagine ASP (Application Server Pages) e file di supporto.

Per installare i file [!DNL Report Portal], è necessario estrarre questi file dal file di distribuzione ricevuto da Adobe e installarli nel computer in cui è in esecuzione Microsoft IIS.

**Per installare i file[!DNL Report Portal]dell&#39;applicazione**

1. Se non lo avete ancora fatto, scaricate il pacchetto di installazione (file .zip) per il [!DNL Report Portal] sito Adobe FTP.
1. Nel computer in cui è in esecuzione IIS, estrarre i file nel pacchetto di installazione in qualsiasi posizione. Questo passaggio installa le sottocartelle e i file seguenti nella cartella VSVirtualPortalName.

   | Cartella o file | Descrizione |
   |---|---|
   | [!DNL \data\users.mdb] | Database contenente l&#39;elenco degli [!DNL Report Portal] utenti autorizzati. |
   | [!DNL \PortalASP\] | Cartella contenente i file ASP che compongono [!DNL Report Portal]. |
   | [!DNL \PortalFiles\] | Cartella contenente cinque sottocartelle (Core, CSS, HTC, Immagini e Output) che contengono i file di supporto utilizzati da [!DNL Report Portal]. |
   | [!DNL ReportPortalSetup.xml] | File di configurazione utilizzato per definire le directory virtuali associate [!DNL Report Portal] (utilizzato solo con IIS 6.0). |

   La directory ha l&#39;aspetto seguente:

   ![](assets/rptPort_scrn_installDir.png)

   >[!NOTE]
   >
   >Il nome della directory può essere diverso dal nome mostrato nell&#39;esempio.

1. Rinominare la cartella VSVirtualPortalName (o altro nome) in quella che si desidera utilizzare come directory virtuale principale del [!DNL Report Portal] (in seguito denominata *PortalName*). Per ulteriori informazioni sulle directory virtuali, vedere la sezione successiva.
