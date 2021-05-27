---
description: Server Files Manager visualizza tutte le directory nella directory di installazione del server Data Workbench, inclusi i file di configurazione e di ricerca.
title: Creare un Server Files Manager (Gestore dei file del server)
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# Creare un Server Files Manager (Gestore dei file del server){#create-a-server-files-manager}

Server Files Manager visualizza tutte le directory nella directory di installazione del server Data Workbench, inclusi i file di configurazione e di ricerca.

È possibile accedere a una parte del [!DNL Server Files Manager] senza dover navigare nell’intera struttura della directory o visualizzare solo alcune delle sottodirectory per soddisfare una particolare esigenza. Ad esempio, puoi creare una [!DNL Server Files Manager] separata che visualizza solo le sottodirectory Controllo accessi e Utenti, consentendo di gestire gli utenti e il loro accesso.

Ogni manager creato deve disporre di un file [!DNL .vw]. Puoi utilizzare il file [!DNL Server Files.vw] come modello.

Per ulteriori informazioni su [!DNL Server Files Manager], vedere [Server Files Manager](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**Per creare un Server Files Manager**

1. In [!DNL Profile Manager], fai clic sulla directory **[!UICONTROL Menu]**, quindi sulla directory **[!UICONTROL Admin]**. Il file [!DNL Server Files.vw] si trova qui.
1. Nella colonna *nome profilo*, fai clic con il pulsante destro del mouse sul segno di spunta per il file [!DNL Server Files.vw] e fai clic su **[!UICONTROL Make Local]**. Nella colonna [!DNL User] viene visualizzato un segno di spunta per il file.
1. Fai clic con il pulsante destro del mouse sul segno di spunta per il file [!DNL Server Files.vw] nella colonna [!DNL User] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene aperto il file [!DNL Server Files.vw] .
1. Per rimuovere una directory, fai clic con il pulsante destro del mouse sul bordo superiore del [!DNL Server Files Manager] e fai clic su **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Per aggiungere una directory, fai clic con il pulsante destro del mouse sul bordo superiore del [!DNL Server Files Manager], quindi fai clic su **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Digita l’URI della directory nel campo URI e fai clic su **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >È possibile designare più directory nel campo URI. Ad esempio, se si digita [!DNL Profiles\Marketing\], il gestore dei file del server contiene la sottodirectory Marketing, ma nessun’altra sottodirectory all’interno della directory Profiles .

1. Fai clic con il pulsante destro del mouse sul bordo superiore del [!DNL Server Files Manager] e fai clic su **[!UICONTROL Save]**.
1. Per creare un nuovo manager, modificare il nome del file nel campo [!DNL File Name], quindi fare clic su **[!UICONTROL Save]**. Per sovrascrivere il manager esistente, fai clic su **[!UICONTROL Save]**.
1. (Facoltativo) Per rendere le modifiche disponibili a tutti gli utenti del profilo di lavoro, fai clic con il pulsante destro del mouse sul segno di spunta relativo al file [!DNL .vw] nella colonna [!DNL User] .

   Quindi fate clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
