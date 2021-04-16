---
description: Profile Manager (Gestione profili) visualizza tutte le directory associate al profilo di lavoro.
title: Creare un Profile Manager (Gestione profili)
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 2%

---

# Creare un Profile Manager (Gestione profili){#create-a-profile-manager}

Profile Manager (Gestione profili) visualizza tutte le directory associate al profilo di lavoro.

È possibile accedere a una sottodirectory del [!DNL Profile Manager] senza dover navigare nell’intera struttura della directory. Ad esempio, le opzioni di menu [!DNL Metrics] e [!DNL Workspaces] disponibili nel menu [!DNL Manage] della finestra dell’area di lavoro consentono di aprire rispettivamente le cartelle Metriche di Profile Manager e Aree di lavoro.

Per ulteriori informazioni su [!DNL Profile Manager], consulta [Profile Manager](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Per impostazione predefinita è possibile accedere ai seguenti manager:

* **[!DNL Metrics Manager]:** visualizza il contenuto della cartella Metriche di Profile Manager. Puoi aprire, modificare, rimuovere o copiare le metriche definite all’interno di ciascun profilo.
* **[!DNL Reports Manager]:** visualizza il contenuto della cartella Report di Profile Manager. È possibile aprire, modificare, rimuovere o copiare file di report o [!DNL report.cfg] aree di lavoro.

* **[!DNL Workspaces Manager]:** visualizza il contenuto della cartella Workspace del Profile Manager. Tutti i file per la configurazione delle schede di [!DNL Worktop] si trovano qui. Consulta [Personalizzazione delle schede dei piani di lavoro](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Data Workbench consente di creare ulteriori gestori di profili che visualizzano una sottodirectory dal percorso [!DNL Profile Manager]. Ogni manager creato deve disporre di un file [!DNL .vw] che specifica la directory [!DNL Profile Manager] di cui mostra il contenuto e le proprietà di tale finestra. Puoi utilizzare il file [!DNL .vw] per uno qualsiasi dei manager specificati come modello.

**Per creare un Profile Manager**

1. In [!DNL Profile Manager], fai clic sulla directory **[!UICONTROL Menu]** per visualizzarne il contenuto.
1. Nella directory Menu, fare clic sulla directory **[!UICONTROL Admin]** e quindi sulla directory **[!UICONTROL Profile]**. I file [!DNL .vw] per i manager esistenti si trovano qui.
1. Nella colonna *nome profilo* fare clic con il pulsante destro del mouse sul segno di spunta relativo a uno dei file [!DNL .vw] (ad esempio, [!DNL Workspaces.vw]), quindi fare clic su **[!UICONTROL Make Local]**.

   Nella colonna [!DNL User] viene visualizzato un segno di spunta per il file.

1. Fai clic con il pulsante destro del mouse sul segno di spunta per il file [!DNL .vw] nella colonna [!DNL User] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Nel campo [!DNL Profile Path] digitare la directory [!DNL Profile Manager] per la quale si desidera creare un nuovo manager. Assicurati di includere la barra (/) dopo il nome della directory.

   ```
   window = simpleBorderWindow:
   client = scrollWindow: 
   client = fileManager:
     Profile Path = string: directory name/
     size = v3d: (820, 5649, 0)
     scroll_offset = v3d: (0, 0, 0)
     size = v3d: (830, 881, 0)
     pos = v3d: (525, 162, 0)
     size = v3d: (830, 900, 0)
   ```

1. Nel Blocco note, fai clic su **[!UICONTROL File]** > **[!UICONTROL Save As]** per salvare il file modificato nella cartella di installazione *Data Workbench*\User\*nome profilo di lavoro*\Menu\Admin\Profile Management.

   Assicurati di cambiare il nome del file [!DNL .vw] in modo che rifletta la directory nel [!DNL Profile Manager] a cui corrisponde.

1. (Facoltativo) Per rendere le modifiche disponibili a tutti gli utenti del profilo di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta relativo al file [!DNL .vw] nella colonna [!DNL User] e fare clic su **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**.
