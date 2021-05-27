---
description: Procedura per installare i componenti Microsoft richiesti.
title: Installazione dei componenti richiesti
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---

# Installazione dei componenti richiesti{#installing-required-components}

Procedura per installare i componenti Microsoft richiesti.

1. Installare Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Questa deve essere installata solo dopo l&#39;installazione e la configurazione del ruolo Web IIS.

1. Seguire la procedura guidata e scegliere i valori predefiniti quando richiesto per completare l&#39;installazione.
1. Una volta installato, verificare che il pool di applicazioni ASP.NET v.4.0 sia stato aggiunto all&#39;interno dell&#39;elenco **[!UICONTROL Application Pools]** in IIS.
1. Installare il database di Microsoft SQL Server.

   Utilizzare qualsiasi versione di SQL Server 2008 o 2008 R2 (Express è supportato) con gli strumenti di gestione (Adobe consiglia SQL Server 2008 R2 SP1 - Express Edition). 1. Per un&#39;installazione generica senza istanze SQL Server esistenti in esecuzione in anticipo, selezionare l&#39;opzione **[!UICONTROL Default Instance]** nella schermata **[!UICONTROL Instance Configuration]**.
1. Per le altre opzioni di configurazione, seguire la procedura guidata e scegliere le impostazioni predefinite quando richiesto per completare l&#39;installazione.
1. Installare Microsoft Web Deploy v2.0.

   Per la maggior parte delle installazioni, l&#39;installazione di **[!UICONTROL Typical]** va bene. Tuttavia, se prevedi di eseguire distribuzioni remote, dovrai eseguire un’installazione completa (scegli **[!UICONTROL Complete]**).

   Una volta installati correttamente tutti i prerequisiti, è possibile preparare i server di Data Workbench a comunicare con il dashboard.
