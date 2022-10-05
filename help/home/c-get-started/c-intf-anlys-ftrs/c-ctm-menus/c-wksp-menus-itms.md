---
description: Questi passaggi si applicano solo alla creazione di sottomenu e voci di menu per il menu Finestra di Workspace.
title: Creazione di un menu e di una voce di menu dell’area di lavoro
uuid: 9565fe7a-fa4c-42b6-9aa5-b652a2d62796
exl-id: 26f2b85c-ab23-41a4-bf4b-9e507952fede
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 3%

---

# Creazione di un menu e di una voce di menu dell’area di lavoro{#create-a-workspace-menu-and-menu-item}

{{eol}}

Questi passaggi si applicano solo alla creazione di sottomenu e voci di menu per il menu Finestra di Workspace.

Puoi personalizzare i menu delle metriche e delle dimensioni creando nuove cartelle e nuove metriche e dimensioni derivate. Per ulteriori informazioni, consulta [Creazione e modifica di metriche derivate](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-drvd-mtrcs.md#concept-e41723b342a849309874b26232224a40) e [Creazione e modifica di Dimension derivati](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

**Creazione di un nuovo menu della finestra dell&#39;area di lavoro**

1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Menu]** per visualizzarne il contenuto.
1. In [!DNL User] per la directory Menu, fare clic su **[!UICONTROL Create]** > **[!UICONTROL Folder]**. Nella cartella viene visualizzata una cartella denominata Nuova cartella [!DNL File] colonna per [!DNL Menu].

   >[!NOTE]
   >
   >È inoltre possibile creare una nuova cartella per qualsiasi sottodirectory all’interno della directory Menu.

1. Rinomina la nuova cartella facendo clic con il pulsante destro del mouse nel [!DNL User] per la cartella e digita il nuovo nome nel parametro Dir.
1. Aggiungi i file desiderati alla nuova cartella.
1. (Facoltativo) In [!DNL User] per la nuova cartella, fai clic su **[!UICONTROL Create]** > **[!UICONTROL order.txt]**.

   Un [!DNL order.txt] il file viene visualizzato nel [!DNL File] per la nuova cartella e un segno di spunta per il nuovo file viene visualizzato nel [!DNL User] colonna.

1. (Facoltativo) Modifica il [!DNL order.txt] se necessario. Vedi [Personalizzazione dei menu tramite i file Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Facoltativo) Per rendere le modifiche disponibili a tutti gli utenti del profilo di lavoro, fai clic con il pulsante destro del mouse sul segno di spunta bianco della cartella nella [!DNL User] e fai clic su **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL working profile name]**>*.

**Per aggiungere una nuova voce di menu a un menu esistente**

1. Completa uno dei seguenti passaggi:

   * Crea un nuovo elemento (visualizzazione, annotazione e così via) da aggiungere a un menu:

      1. Apri un’area di lavoro in Data Workbench e crea l’elemento desiderato.
      1. Salva l&#39;elemento nella seguente directory:

         *Directory di installazione di Data Workbench*\User\*nome profilo di lavoro*\Work

      1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Work]** per visualizzarne il contenuto.
      1. In [!DNL User] fare clic con il pulsante destro del mouse sul segno di spunta del file desiderato e fare clic su **[!UICONTROL Copy]**.
      1. In [!DNL User] per la cartella desiderata, fai clic su **[!UICONTROL Paste]**.

         Una copia del file viene visualizzata nel [!DNL File] per la nuova cartella e un segno di spunta per il nuovo file viene visualizzato nel [!DNL User] colonna.
   * Copiare e incollare un elemento esistente da un menu (cartella) a un altro:

      1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Menu]** per visualizzarne il contenuto.
      1. In *nome profilo di lavoro* fare clic con il pulsante destro del mouse sul segno di spunta del file desiderato e fare clic su **[!UICONTROL Make Local]**.
      1. Fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL User] e fai clic su **[!UICONTROL Copy]**.
      1. In [!DNL User] per la cartella desiderata, fai clic su **[!UICONTROL Paste]**. Una copia del file viene visualizzata nel [!DNL File] per la nuova cartella e un segno di spunta per il nuovo file viene visualizzato nel [!DNL User] colonna.


1. (Facoltativo) Modifica il [!DNL order.txt] se necessario. Vedi [Personalizzazione dei menu tramite i file Order.txt](../../../../home/c-get-started/c-intf-anlys-ftrs/c-ctm-menus/t-cstm-menus-ordr-files.md#task-a391800a8dd444deb3e1516d5189f999).
1. (Facoltativo) Per rendere le modifiche disponibili a tutti gli utenti del profilo di lavoro, fai clic con il pulsante destro del mouse sul segno di spunta bianco di ciascun file nel [!DNL User] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.
1. (Facoltativo) Per evitare che una voce di menu venga visualizzata in più menu, è necessario eliminare il file corrispondente dalla cartella originale facendo clic con il pulsante destro del mouse sul segno di spunta del file *nome profilo di lavoro* colonna e clic **[!UICONTROL Remove]** > **[!UICONTROL Yes]**.

   Ripeti questo passaggio per il segno di spunta del file nel [!DNL User] colonna.
