---
description: Effettuare l'aggiornamento a Workbench dati v6.4.
title: Aggiornamento da 6.3 a 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Upgrading 6.3 to 6.4{#upgrading-to}

Effettuare l&#39;aggiornamento a Workbench dati v6.4.

## Requisiti e raccomandazioni per l&#39;aggiornamento {#section-8704a9ac358246cd81233dd0982d534f}

Per effettuare l&#39;aggiornamento a Workbench dati 6.4, attenersi ai seguenti requisiti e consigli.

>[!IMPORTANT]
>
>È consigliabile utilizzare i file di configurazione predefiniti appena installati e personalizzarli, anziché spostare i file da un&#39;installazione precedente, con le seguenti eccezioni:

* **Aggiungi** processi ****** esclusi per *MS System Center Endpoint Protection nei server* Windows 2012 per i seguenti eseguibili:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   In questo modo saranno consentiti i diritti &quot;white list&quot; per questi eseguibili di interfaccia.

* **Aggiornate il certificato *Trust_ca_cert.pem*sui server**.
* **Riorganizzazione dei profili** di attribuzione.

   * La cartella *Attribution* è stata rinominata in ***Attribution - Premium*** (disponibile nell&#39;installazione predefinita in *Profiles*\*Attribution - Premium*).

   * Il profilo *Premium* è stato rimosso e l&#39;area di lavoro è stata spostata nella nuova cartella ***Attribution - Premium*** .

* **Aggiornate le impostazioni *Attribution-Premium***. Se disponete di profili personalizzati con impostazioni di parametro che ignorano il profilo predefinito di *Adobe SC* , dovete aggiornare i campi personalizzati nei seguenti file di configurazione:

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* A causa di questa riorganizzazione, si desidera rimuovere le vecchie cartelle *Attribuzione* e *Premium* dall&#39;installazione del server.

   **Modificare queste impostazioni**

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 6 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\\ 
   
       4 = string: Attribution\\ 
       5 = string: Premium\\
   ```

   alle seguenti impostazioni:

   ```
   Profile = profileInfo:  
     Active = bool: true 
     Directories = vector: 5 items 
       0 = string: Base\\ 
       1 = string: Geography\\ 
       2 = string: Predictive Analytics\\ 
       3 = string: Adobe SC\
       4 = string: Attribution - Premium\\
   ```

* **Aggiornate i file** Meta.cfg personalizzati (se necessario).

   I **[!DNL Meta.cfg]** file nelle **[!DNL Base\Context and AdobeSC\Context]** cartelle sono stati aggiornati in questa versione.

   Se durante l’installazione si sostituisce il file **meta.cfg** , la copia del profilo deve essere aggiornata con i seguenti parametri e il vettore **di** metadati immesso correttamente:

   ```
   94 = meta: 
     path = string: SegmentExport:CRS Configuration/CRS Attributes 
     acceptable children = vector: 1 items 
       0 = Template: 
         name = string: CRS Attributes 
         value = CRSAttributeConfiguration: 
           Attribute Name = string: 
           Attribute Type(int,string) = string: 
           Field Name = string: 
   
   95 = meta: 
     path = string: SegmentExportQuery:CRS Configuration/Report Suite 
     acceptable children = vector: 1 items 
       0 = Template 
         name = string: Add Report Suite 
         value = string:
   ```

* **Impostare le autorizzazioni** del server di report per generare rapporti di Microsoft Excel sui server Windows 2012.

   1. Impostate l&#39;autorizzazione della cartella principale (**[!DNL E:\ReportServer\]**) su *Everyone = full control*.

   1. Create le seguenti cartelle con le autorizzazioni appropriate:

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >Se si esegue Report Server su Windows Server 2012, è necessario che sia installato Windows Server 2012 R2.

   1. Assegnate &quot;SYSTEM&quot; come proprietario di queste cartelle.

* **Aggiungete i font al server di report.** Nel file **[!DNL ReportServer.cfg]**aggiungere i seguenti font (per tutte le lingue):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Aggiornare la versione di Microsoft Excel ** (se necessario).

   Con il rilascio di Workbench dati 6.4, il supporto per Excel 2007 è stato interrotto. Inoltre, poiché Workbench dati viene eseguito solo su Microsoft Windows per l&#39;architettura a 64 bit, è consigliabile installare anche una versione a 64 bit di Microsoft Excel.

* **Architettura** a 64 bit necessaria per l&#39;installazione di Workstation (Client).
* **Eseguire la procedura guidata** di impostazione della workstation.

   Installa la nuova versione della workstation (client) scaricando e avviando ***InsightSetup.exe*** e analizzando le istruzioni di configurazione. Per impostazione predefinita, i file vengono installati in una nuova posizione:

   I file di programma ora vengono salvati per impostazione predefinita in:

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   I file di dati (profili, certificati, registri di traccia e file utente) ora vengono salvati per impostazione predefinita in:

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Aggiungere i font alla workstation**.

   Nel **[!DNL Insight.cfg]** file, aggiungete i seguenti font (per tutte le lingue):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

