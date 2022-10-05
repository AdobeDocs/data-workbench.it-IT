---
description: Profile Manager (Gestione profili) visualizza tutte le directory associate al profilo di lavoro.
title: Creare un Profile Manager (Gestione profili)
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
exl-id: 43b95473-ab3e-4a80-9b91-7c221e74b096
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 2%

---

# Creare un Profile Manager (Gestione profili){#create-a-profile-manager}

{{eol}}

Profile Manager (Gestione profili) visualizza tutte le directory associate al profilo di lavoro.

È possibile accedere a una sottodirectory del [!DNL Profile Manager] senza dover navigare nell’intera struttura della directory. Ad esempio, il [!DNL Metrics] e [!DNL Workspaces] opzioni di menu disponibili nella [!DNL Manage] nel menu della finestra dell&#39;area di lavoro è possibile aprire rispettivamente le cartelle Metriche di Profile Manager e Aree di lavoro.

Per ulteriori informazioni sulla [!DNL Profile Manager], vedi [Profile Manager](https://experienceleague.adobe.com/docs/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html).

Per impostazione predefinita è possibile accedere ai seguenti manager:

* **[!DNL Metrics Manager]:** Visualizza il contenuto della cartella Metriche di Profile Manager. Puoi aprire, modificare, rimuovere o copiare le metriche definite all’interno di ciascun profilo.
* **[!DNL Reports Manager]:** Visualizza il contenuto della cartella Report di Profile Manager. È possibile aprire, modificare, rimuovere o copiare le aree di lavoro dei rapporti oppure [!DNL report.cfg] file.

* **[!DNL Workspaces Manager]:** Visualizza il contenuto della cartella Workspace di Profile Manager. Tutti i file per la configurazione del [!DNL Worktop]Le schede sono disponibili qui. Vedi [Personalizzazione delle schede dei piani di lavoro](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md).

Data Workbench consente di creare ulteriori gestori di profili che visualizzano una sottodirectory dalla [!DNL Profile Manager]. Ogni manager creato deve avere una [!DNL .vw] file che specifica [!DNL Profile Manager] directory di cui mostra il contenuto e le proprietà di tale finestra. È possibile utilizzare [!DNL .vw] file per uno qualsiasi dei gestori forniti come modello.

**Per creare un Profile Manager**

1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Menu]** per visualizzarne il contenuto.
1. Nella directory Menu, fai clic su **[!UICONTROL Admin]** e quindi la **[!UICONTROL Profile]** directory. La [!DNL .vw] i file per i manager esistenti si trovano qui.
1. In *nome profilo* fare clic con il pulsante destro del mouse sul segno di spunta per la colonna [!DNL .vw] file (ad esempio, [!DNL Workspaces.vw]), quindi fai clic su **[!UICONTROL Make Local]**.

   Nel [!DNL User] colonna.

1. Fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL .vw] nel [!DNL User] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. In [!DNL Profile Path] campo , digita il [!DNL Profile Manager] directory per la quale si desidera creare un nuovo manager. Assicurati di includere la barra (/) dopo il nome della directory.

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

1. In Blocco note, fai clic su **[!UICONTROL File]** > **[!UICONTROL Save As]** per salvare il file modificato nel *Data Workbench cartella di installazione*\User\*nome profilo di lavoro*\Menu\Admin\Profile Management.

   Assicurati di cambiare il nome della [!DNL .vw] per riflettere la directory nel [!DNL Profile Manager] a cui corrisponde.

1. (Facoltativo) Per rendere le modifiche disponibili a tutti gli utenti del profilo di lavoro, fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL .vw] nel [!DNL User] e fai clic su **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>
