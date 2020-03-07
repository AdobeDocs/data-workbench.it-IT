---
description: Server Files Manager visualizza tutte le directory della directory di installazione del server Workbench dati, compresi i file di configurazione e di ricerca.
solution: Analytics
title: Creare un server Files Manager
topic: Data workbench
uuid: 9fb2163d-3756-40d2-9817-4a89bd8a38c9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creare un server Files Manager{#create-a-server-files-manager}

Server Files Manager visualizza tutte le directory della directory di installazione del server Workbench dati, compresi i file di configurazione e di ricerca.

È possibile accedere a una parte della directory [!DNL Server Files Manager] senza dover navigare nell&#39;intera struttura di directory o visualizzare solo alcune delle sottodirectory per rispondere a particolari esigenze. Ad esempio, potrebbe essere utile creare un&#39;altra directory [!DNL Server Files Manager] che visualizzi solo le sottodirectory Controllo accesso e Utenti, consentendo di gestire gli utenti e il loro accesso.

Ogni manager creato deve avere un [!DNL .vw] file. Potete usare il [!DNL Server Files.vw] file come modello.

Per ulteriori informazioni su [!DNL Server Files Manager], vedere [Gestione](../../../../home/c-get-started/c-admin-intrf/c-svr-files-mgr.md#concept-73a0808487c8424285ae7302f53bc5f4)file server.

**Per creare una Server Files Manager**

1. In [!DNL Profile Manager], fare clic sulla **[!UICONTROL Menu]** directory, quindi sulla **[!UICONTROL Admin]** directory. Il [!DNL Server Files.vw] file si trova qui.
1. Nella colonna del nome *del* profilo, fare clic con il pulsante destro del mouse sul segno di spunta del [!DNL Server Files.vw] file e fare clic **[!UICONTROL Make Local]**. Un segno di spunta per il file viene visualizzato nella [!DNL User] colonna.
1. Fare clic con il pulsante destro del mouse sul [!DNL Server Files.vw] file nella [!DNL User] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Si apre il [!DNL Server Files.vw] file.
1. Per rimuovere una directory, fare clic con il pulsante destro del mouse sul bordo superiore del [!DNL Server Files Manager] file e scegliere **[!UICONTROL Server Directories]** > **[!UICONTROL Remove]** > *&lt;**[!UICONTROL directory name]**>*.
1. Per aggiungere una directory, fare clic con il pulsante destro del mouse sul bordo superiore della directory [!DNL Server Files Manager], quindi scegliere **[!UICONTROL Server Directories]** > **[!UICONTROL Add]** > **[!UICONTROL Directory]**.

   Digitate l’URI della directory nel campo URI e fate clic **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Potete designare più directory nel campo URI. Ad esempio, se digitate [!DNL Profiles\Marketing\], il gestore file server contiene la sottodirectory Marketing, ma nessun&#39;altra sottodirectory all&#39;interno della directory Profiles.

1. Fare clic con il pulsante destro del mouse sulla parte superiore del bordo superiore [!DNL Server Files Manager] e quindi scegliere **[!UICONTROL Save]**.
1. Per creare un nuovo manager, modificate il nome del file nel [!DNL File Name] campo, quindi fate clic su **[!UICONTROL Save]**. Per sovrascrivere il manager esistente, fate clic su **[!UICONTROL Save]**.
1. (Facoltativo) Per rendere disponibili le modifiche a tutti gli utenti del profilo di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta del [!DNL .vw] file nella [!DNL User] colonna.

   Quindi fate clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

