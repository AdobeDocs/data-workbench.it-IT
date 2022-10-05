---
description: Segui questi passaggi per eseguire l’aggiornamento alla versione v6.4 di Data Workbench.
title: Upgrading 6.3 a 6.4
uuid: 2461c1ab-cf99-4fb5-b431-d7062df7a53d
exl-id: 540deb86-2463-4820-b67a-a32d68b4346e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 0%

---

# Upgrading 6.3 a 6.4{#upgrading-to}

{{eol}}

Segui questi passaggi per eseguire l’aggiornamento alla versione v6.4 di Data Workbench.

## Requisiti di aggiornamento e Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Segui questi requisiti e consigli durante l’aggiornamento alla Data Workbench 6.4.

>[!IMPORTANT]
>
>È consigliabile utilizzare i file di configurazione predefiniti appena installati e personalizzarli, anziché spostare i file da un’installazione precedente, con le seguenti eccezioni:

* **Aggiungi** ***Processi esclusi*** per *MS System Center Endpoint Protection nei server Windows 2012* per i seguenti eseguibili:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   In questo modo verranno abilitati i diritti inserire nell&#39;elenco Consentiti per questi eseguibili di interfaccia.

* **Aggiorna *Trust_ca_cert.pem* certificato sui server**.
* **Riorganizzazione dei profili di attribuzione**.

   * La *Attribuzione* la cartella è stata rinominata in ***Attribuzione - Premium*** (nell&#39;installazione predefinita in *Profili*\*Attribution - Premium*).

   * La *Premium* il profilo è stato rimosso e l’area di lavoro è stata spostata nel nuovo ***Attribuzione - Premium*** cartella.

* **Aggiorna *Attribution-Premium* impostazioni**. Se hai profili personalizzati con impostazioni di parametro che sostituiscono quelle predefinite *Adobe SC* quindi devi aggiornare i campi personalizzati nei seguenti file di configurazione:

   * **[!DNL Decoding Instructions.cfg]**
   * **[!DNL SC Fields.cfg]**

* A causa di questa riorganizzazione, si desidera rimuovere il vecchio *Attribuzione* e *Premium* cartelle dall&#39;installazione del server.

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

* **Aggiorna file Meta.cfg personalizzati** (se necessario).

   La **[!DNL Meta.cfg]** file in **[!DNL Base\Context and AdobeSC\Context]** le cartelle sono state aggiornate in questa versione.

   Se sovrascrivi **meta.cfg** durante l’installazione, la copia del profilo deve essere aggiornata con questi parametri e la **vettore metadati** inserito in modo appropriato:

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

* **Impostare le autorizzazioni del server di rapporto** per generare rapporti di Microsoft Excel Sui server Windows 2012.

   1. Imposta l&#39;autorizzazione della cartella principale (**[!DNL E:\ReportServer\]**) a *Tutti = controllo completo*.

   1. Crea le seguenti cartelle con le autorizzazioni appropriate:

      ```
      C:\Windows\SysWOW64\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\INetCac‌he 
      C:\Windows\System32\config\systemprofile\Desktop 
      C:\Windows\SysWOW64\config\systemprofile\Desktop
      ```

      >[!NOTE]
      >
      >Se si esegue Report Server su Windows Server 2012, è necessario che sia installato Windows Server 2012 R2.

   1. Assegnare &quot;SYSTEM&quot; come proprietario di queste cartelle.

* **Aggiungi font al server di rapporto.** Nel **[!DNL ReportServer.cfg]**file, aggiungi questi font (per tutte le lingue):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```

* **Aggiorna la tua versione di Microsoft Excel ** (se necessario).

   Con il rilascio della Data Workbench 6.4, il supporto per Excel 2007 è stato interrotto. Anche perché Data Workbench viene eseguito solo su Microsoft Windows per l&#39;architettura a 64 bit, si consiglia di installare anche una versione a 64 bit di Microsoft Excel.

* **Architettura a 64 bit** richiesto per l&#39;installazione di Workstation (Client).
* **Eseguire la procedura guidata di installazione della workstation**.

   Installa la nuova versione della workstation (client) scaricando e avviando ***InsightSetup.exe*** ed esaminare le istruzioni di configurazione. Per impostazione predefinita, i file verranno installati in una nuova posizione:

   I file di programma vengono ora salvati per impostazione predefinita in:

   ```
   C:\Program Files\Adobe\Adobe Analytics\Data Workbench
   ```

   I file di dati (profili, certificati, registri di traccia e file utente) vengono ora salvati per impostazione predefinita in:

   ```
   C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
   ```

* **Aggiungi font alla workstation**.

   In **[!DNL Insight.cfg]** aggiungi i seguenti font (per tutte le lingue):

   ```
   Fonts = vector: 3 items 
     0 = string: Arial 
     1 = string: SimSun 
     2 = string: MS Mincho
   ```
