---
description: Questi passaggi si applicano solo alla creazione di sottomenu e voci di menu per il menu Finestra di Workspace.
solution: Analytics
title: Creazione di un menu e di una voce di menu dell’area di lavoro
topic: Data workbench
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creazione di un menu e di una voce di menu dell’area di lavoro{#create-a-workspace-menu-and-menu-item}

Questi passaggi si applicano solo alla creazione di sottomenu e voci di menu per il menu Finestra di Workspace.

Puoi personalizzare i menu delle metriche e delle dimensioni creando nuove cartelle e nuove metriche e dimensioni derivate. Per ulteriori informazioni, consultate [Creazione e modifica di metriche](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) derivate e [Creazione e modifica di dimensioni](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93)derivate.

**Per creare un nuovo menu della finestra di un&#39;area di lavoro**

1. Nella [!DNL Profile Manager], fate clic sulla **[!UICONTROL Menu]** directory per visualizzarne il contenuto.
1. Nella [!DNL User] colonna relativa alla directory Menu, fare clic su **[!UICONTROL Create]** > **[!UICONTROL Folder]**. Nella [!DNL File] colonna per [!DNL Menu]viene visualizzata una cartella denominata Nuova cartella.

   >[!NOTE]
   >
   >È inoltre possibile creare una nuova cartella per qualsiasi sottodirectory all&#39;interno della directory Menu.

1. Per rinominare la nuova cartella, fate clic con il pulsante destro del mouse nella [!DNL User] colonna della cartella e digitate il nuovo nome nel parametro Dir.
1. Aggiungete i file desiderati alla nuova cartella.
1. (Facoltativo) Nella [!DNL User] colonna relativa alla nuova cartella, fate clic su **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Un [!DNL order.txt] file viene visualizzato nella [!DNL File] colonna relativa alla nuova cartella e nella [!DNL User] colonna viene visualizzato un segno di spunta per il nuovo file.

1. (Facoltativo) Modificate il [!DNL order.txt] file come necessario. Consultate [Personalizzazione dei menu tramite i file](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.
1. (Facoltativo) Per rendere disponibili le modifiche a tutti gli utenti del profilo di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta bianco della cartella nella [!DNL User] colonna e fare clic su **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Aggiunta di una nuova voce di menu a un menu esistente**

1. Completa uno dei seguenti passaggi:

   * Create un nuovo elemento (visualizzazione, annotazione e così via) da aggiungere a un menu:

      1. Aprire un&#39;area di lavoro in Workbench dati e creare l&#39;elemento desiderato.
      1. Salvate l’elemento nella seguente directory:

         *Directory* di installazione del workbench dati \User\*nome profilo di lavoro*\Work

      1. Nella [!DNL Profile Manager], fate clic sulla **[!UICONTROL Work]** directory per visualizzarne il contenuto.
      1. Nella [!DNL User] colonna, fare clic con il pulsante destro del mouse sul segno di spunta per il file desiderato e fare clic **[!UICONTROL Copy]**.
      1. Nella [!DNL User] colonna della cartella desiderata, fate clic su **[!UICONTROL Paste]**.

         Una copia del file viene visualizzata nella [!DNL File] colonna relativa alla nuova cartella e un segno di spunta per il nuovo file viene visualizzato nella [!DNL User] colonna.
   * Copiate e incollate un elemento esistente da un menu (cartella) a un altro:

      1. Nella [!DNL Profile Manager], fate clic sulla **[!UICONTROL Menu]** directory per visualizzarne il contenuto.
      1. Nella colonna del nome *del profilo di* lavoro, fare clic con il pulsante destro del mouse sul segno di spunta per il file desiderato e fare clic **[!UICONTROL Make Local]**.
      1. Fare clic con il pulsante destro del mouse sul segno di spunta per il file nella [!DNL User] colonna e fare clic **[!UICONTROL Copy]**.
      1. Nella [!DNL User] colonna della cartella desiderata, fate clic su **[!UICONTROL Paste]**. Una copia del file viene visualizzata nella [!DNL File] colonna relativa alla nuova cartella e un segno di spunta per il nuovo file viene visualizzato nella [!DNL User] colonna.


1. (Facoltativo) Modificate il [!DNL order.txt] file come necessario. Consultate [Personalizzazione dei menu tramite i file](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999)Order.txt.
1. (Facoltativo) Per rendere disponibili le modifiche a tutti gli utenti del profilo di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta bianco di ciascun file nella [!DNL User] colonna e fare clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Facoltativo) Per evitare che una voce di menu venga visualizzata in più menu, è necessario eliminare il file corrispondente dalla cartella originale facendo clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna del nome *del profilo di* lavoro e facendo clic su **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Ripetere questo passaggio per il segno di spunta del file nella [!DNL User] colonna.

