---
description: Passaggi per installare i componenti Microsoft richiesti.
title: Installazione dei componenti richiesti
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---

# Installazione dei componenti richiesti{#installing-required-components}

{{eol}}

Passaggi per installare i componenti Microsoft richiesti.

1. Installare Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Questa deve essere installata solo dopo l&#39;installazione e la configurazione del ruolo Web IIS.

1. Seguire la procedura guidata e scegliere i valori predefiniti quando richiesto per completare l&#39;installazione.
1. Una volta installato, verificare che il pool di applicazioni ASP.NET v.4.0 sia stato aggiunto all&#39;interno di **[!UICONTROL Application Pools]** elenco in IIS.
1. Installare il database Microsoft SQL Server.

   Utilizzare qualsiasi versione di SQL Server 2008 o 2008 R2 (Express è supportato) con gli strumenti di gestione (Adobe consiglia SQL Server 2008 R2 SP1 - Express Edition). 1. Per un&#39;installazione generica senza istanze SQL Server esistenti in esecuzione in anticipo, selezionare il **[!UICONTROL Default Instance]** l&#39;opzione **[!UICONTROL Instance Configuration]** schermo.
1. Per le altre opzioni di configurazione, seguire la procedura guidata e scegliere le impostazioni predefinite quando richiesto per completare l&#39;installazione.
1. Installa Microsoft Web Deploy v2.0.

   Per la maggior parte degli impianti, il **[!UICONTROL Typical]** l&#39;installazione va bene. Tuttavia, se prevedi di eseguire implementazioni remote, dovrai eseguire un’installazione completa (scegli **[!UICONTROL Complete]**).

   Una volta installati correttamente tutti i prerequisiti, è possibile preparare i server di Data Workbench a comunicare con il dashboard.
