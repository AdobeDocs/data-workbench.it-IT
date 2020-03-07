---
description: Procedura per installare i componenti Microsoft richiesti.
solution: Analytics
title: Installazione dei componenti richiesti
topic: Data workbench
uuid: e23fba09-4684-4daf-8426-ea91169b3348
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installazione dei componenti richiesti{#installing-required-components}

Procedura per installare i componenti Microsoft richiesti.

1. Installare Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Questo deve essere installato solo dopo l&#39;installazione e la configurazione del ruolo Web IIS.

1. Seguite la procedura guidata e scegliete le impostazioni predefinite quando richiesto per completare l’installazione.
1. Una volta installato, verificare che il pool di applicazioni ASP.NET v.4.0 sia stato aggiunto all&#39;interno dell&#39; **[!UICONTROL Application Pools]** elenco in IIS.
1. Installare il database di Microsoft SQL Server.

   Utilizzate qualsiasi versione di SQL Server 2008 o 2008 R2 (Express è supportato) con gli strumenti di gestione (Adobe consiglia SQL Server 2008 R2 SP1 - Express Edition). 1. Per un&#39;installazione generica senza istanze di SQL Server esistenti in esecuzione in anticipo, selezionate l&#39; **[!UICONTROL Default Instance]** opzione nella **[!UICONTROL Instance Configuration]** schermata.
1. Per le altre opzioni di configurazione, seguite la procedura guidata e scegliete le impostazioni predefinite quando richiesto per completare l&#39;installazione.
1. Installazione di Microsoft Web Deploy v2.0.

   Per la maggior parte delle installazioni, l&#39; **[!UICONTROL Typical]** installazione è a posto. Tuttavia, se state pianificando di eseguire distribuzioni remote, dovrete eseguire un&#39;installazione completa (scegliete **[!UICONTROL Complete]**).

   Una volta che tutti i prerequisiti sono stati installati correttamente, è possibile preparare i server workbench dati a comunicare con il dashboard.
