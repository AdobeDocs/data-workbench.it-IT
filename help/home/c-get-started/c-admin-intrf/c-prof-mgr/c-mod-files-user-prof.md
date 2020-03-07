---
description: È possibile utilizzare Gestione profili per scaricare i file da modificare.
solution: Analytics
title: Modificare i file locali nel profilo utente
topic: Data workbench
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modificare i file locali nel profilo utente{#modify-local-files-in-the-user-profile}

È possibile utilizzare Gestione profili per scaricare i file da modificare.

È possibile scaricare un file per sovrascrivere il file locale esistente con la versione originale del file oppure aprire, visualizzare e modificare i file a cui non è possibile accedere dai menu dell&#39;area di lavoro.

**Per scaricare un file**

1. In [!DNL Profile Manager], aprite le cartelle e sottocartelle necessarie per individuare il file da scaricare.
1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file, quindi fare clic **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >I file di configurazione ( [!DNL .cfg]), dimensione ( [!DNL .dim]) e metrica ( [!DNL .metric]) possono essere modificati direttamente in una cartella di profilo e salvati nel server senza renderli locali e salvarli separatamente nel server. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file e scegliere **[!UICONTROL Open]** > **in workstation**.

Dopo che il file è stato scaricato nel computer locale, nella [!DNL User] colonna viene visualizzato un segno di spunta che indica che una copia locale del file risiede nella cartella Utente\*profilo* sul computer. Il segno di spunta ha lo stesso colore del segno di spunta nella colonna del nome *del* profilo. Questo indica che il file locale ha la stessa data e ora di modifica del file nella cartella del nome *del* profilo.

**Per modificare il file**

1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file nella [!DNL User] colonna.
1. Fate clic su una delle seguenti opzioni di menu, a seconda di come desiderate modificare il file:

   * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** se state modificando un [!DNL .vw] file o un [!DNL .cfg] file in un’area di lavoro.

   * **Apri** > **in vw. Editor **se state modificando un file .vw per aggiungere nuovi parametri.

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** se si apre un file di testo o si desidera aggiungere nuovi parametri a un [!DNL .cfg] file.

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** se si desidera aprire la cartella in cui si trova il file sul computer

1. Modificate il file come desiderate, quindi salvate il file.

Nella [!DNL Profile Manager], il segno di spunta nella [!DNL User] colonna per il file modificato ha cambiato colore. Ciò indica che il file locale è ora diverso dalla versione presente nella cartella del nome *del* profilo. Se necessario, potete pubblicare la versione rivista del file nel profilo, che potrà essere utilizzata da altri utenti che utilizzano questo profilo.
