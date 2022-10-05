---
description: Server Files Manager visualizza tutte le directory nella directory di installazione del server Data Workbench, inclusi i file di configurazione e di ricerca.
title: Creare un Server Files Manager (Gestore dei file del server)
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
exl-id: 9e0c8144-0f52-4e46-85d8-c2dcd60ddcb8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 3%

---

# Creare un Server Files Manager (Gestore dei file del server){#create-a-server-files-manager}

{{eol}}

Server Files Manager visualizza tutte le directory nella directory di installazione del server Data Workbench, inclusi i file di configurazione e di ricerca.

È possibile accedere a una parte del [!DNL Server Files Manager] senza dover navigare nella sua intera struttura di directory o visualizzare solo alcune delle sottodirectory per soddisfare una particolare esigenza. Ad esempio, è possibile creare un [!DNL Server Files Manager] visualizza solo le sottodirectory Controllo accessi e Utenti , che consentono di gestire gli utenti e il loro accesso.

Ogni manager creato deve avere una [!DNL .vw] file. È possibile utilizzare [!DNL Server Files.vw] come modello.

Per ulteriori informazioni sulla [!DNL Server Files Manager], vedi [Server Files Manager](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4).

**Per creare un Server Files Manager**

1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Menu]** directory, quindi **[!UICONTROL Admin]** directory. La [!DNL Server Files.vw] il file si trova qui.
1. In *nome profilo* fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL Server Files.vw] e fai clic su **[!UICONTROL Make Local]**. Nel [!DNL User] colonna.
1. Fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL Server Files.vw] nel [!DNL User] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La [!DNL Server Files.vw] viene aperto il file .
1. Per rimuovere una directory, fai clic con il pulsante destro del mouse sul bordo superiore della [!DNL Server Files Manager] e fai clic su **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Per aggiungere una directory, fai clic con il pulsante destro del mouse sul bordo superiore della [!DNL Server Files Manager], fai clic su **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Digita l’URI della directory nel campo URI e fai clic su **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >È possibile designare più directory nel campo URI. Ad esempio, se digiti [!DNL Profiles\Marketing\], il gestore dei file del server contiene la sottodirectory Marketing, ma nessun’altra sottodirectory all’interno della directory Profiles .

1. Fai clic con il pulsante destro del mouse sul bordo superiore del [!DNL Server Files Manager] e fai clic su **[!UICONTROL Save]**.
1. Per creare un nuovo manager, modificare il nome del file nel [!DNL File Name] campo , quindi fai clic su **[!UICONTROL Save]**. Per sovrascrivere il manager esistente, fai clic su **[!UICONTROL Save]**.
1. (Facoltativo) Per rendere le modifiche disponibili a tutti gli utenti del profilo di lavoro, fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL .vw] nel [!DNL User] colonna.

   Quindi fate clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
