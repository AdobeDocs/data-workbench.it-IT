---
description: Puoi utilizzare Gestione profili per scaricare i file da modificare.
title: Modificare i file locali nel profilo utente
uuid: 839417d1-34db-4b14-a103-8f5297af55b7
exl-id: 187d67a1-e436-4bfd-87ad-17b6c70dbee4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 3%

---

# Modificare i file locali nel profilo utente{#modify-local-files-in-the-user-profile}

{{eol}}

Puoi utilizzare Gestione profili per scaricare i file da modificare.

È possibile scaricare un file per sovrascrivere il file locale esistente con la versione originale del file oppure aprire, visualizzare e modificare i file non accessibili dai menu dell&#39;area di lavoro.

**Per scaricare un file**

1. In [!DNL Profile Manager], apri le cartelle e le sottocartelle necessarie per individuare il file da scaricare.
1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file e fai clic su **[!UICONTROL Make Local]**.

   >[!NOTE]
   >
   >Configurazione ( [!DNL .cfg]), dimensione ( [!DNL .dim]) e metrica ( [!DNL .metric]) possono essere modificati direttamente in una cartella di profilo e salvati sul server senza renderli locali e salvarli separatamente sul server. Fai clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file e fai clic su **[!UICONTROL Open]** > **in workstation**.

Dopo che il file è stato scaricato nel computer locale, viene visualizzato un segno di spunta nel [!DNL User] che indica che una copia locale del file si trova nella cartella Nome profilo* utente del computer. Il segno di spunta è dello stesso colore del segno di spunta nel *nome profilo* colonna. Questo indica che il file locale ha la stessa data e ora di modifica del file nel *nome profilo* cartella.

**Per modificare il file**

1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file nel [!DNL User] colonna.
1. Fare clic su una delle seguenti opzioni di menu, a seconda di come si desidera modificare il file:

   * **[!UICONTROL Open]** > **[!UICONTROL in workstation]** se si modifica un [!DNL .vw] file o [!DNL .cfg] in un’area di lavoro.

   * **Apri** > **in vw. Editor **se stai modificando un file .vw per aggiungere nuovi parametri.

   * **[!UICONTROL Open]** > **[!UICONTROL In Notepad]** se stai aprendo un file di testo o hai bisogno di aggiungere nuovi parametri a un [!DNL .cfg] file.

   * **[!UICONTROL Open]** > **[!UICONTROL folder]** se si desidera aprire la cartella in cui si trova il file nel computer

1. Modifica il file come desiderato, quindi salva il file.

In [!DNL Profile Manager], nota che il segno di spunta nel [!DNL User] il colore della colonna relativa al file modificato è stato modificato. Ciò indica che il file locale è ora diverso dalla versione in *nome profilo* cartella. Se necessario, puoi pubblicare la versione rivista del file nel profilo, affinché altri utenti utilizzino questo profilo.
