---
description: Gestione profili visualizza tutte le directory associate al profilo di lavoro.
solution: Analytics
title: Creare un manager profilo
topic: Data workbench
uuid: e16741e2-740b-4f57-861d-e2f57d30abbc
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Creare un manager profilo{#create-a-profile-manager}

Gestione profili visualizza tutte le directory associate al profilo di lavoro.

È possibile accedere a una sottodirectory dell&#39; [!DNL Profile Manager] elenco senza dover navigare nell&#39;intera struttura di directory. Ad esempio, le opzioni [!DNL Metrics] e di [!DNL Workspaces] menu disponibili nel [!DNL Manage] menu della finestra dell&#39;area di lavoro consentono di aprire rispettivamente le cartelle Metriche di Profile Manager e Aree di lavoro.

Per ulteriori informazioni su [!DNL Profile Manager], consulta [Gestione](https://docs.adobe.com/content/help/en/data-workbench/using/client/ui-analysis-features/cstm-prof-files-mgrs/c-new-prof-mgrs.html)profili.

Per impostazione predefinita, potete accedere ai seguenti manager:

* **[!DNL Metrics Manager]:**Visualizza il contenuto della cartella Metriche del Gestore dei profili. Puoi aprire, modificare, rimuovere o copiare le metriche definite all&#39;interno di ciascun profilo.
* **[!DNL Reports Manager]:**Consente di visualizzare il contenuto della cartella Rapporti del Gestore dei profili. Potete aprire, modificare, rimuovere o copiare[!DNL report.cfg]i file o le aree di lavoro dei rapporti.

* **[!DNL Workspaces Manager]:**Visualizza il contenuto della cartella Workspaces di Profile Manager. Tutti i file per la configurazione delle schede[!DNL Worktop]si trovano qui. Consultate[Personalizzazione delle schede](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-wktp-tabs/c-cstm-wktp-tabs.md)del piano di lavoro.

Workbench dati consente di creare ulteriori gestori di profili che visualizzano una sottodirectory dal [!DNL Profile Manager]. Ogni manager creato deve avere un [!DNL .vw] file che specifica la [!DNL Profile Manager] directory di cui mostra il contenuto e le proprietà della finestra. Potete utilizzare il [!DNL .vw] file per qualsiasi manager fornito come modello.

**Per creare un manager profilo**

1. Nella [!DNL Profile Manager], fate clic sulla **[!UICONTROL Menu]** directory per visualizzarne il contenuto.
1. Nella directory Menu, fare clic sulla **[!UICONTROL Admin]** directory e quindi sulla **[!UICONTROL Profile]** directory. I [!DNL .vw] file per i manager esistenti si trovano qui.
1. Nella colonna del nome *del* profilo, fare clic con il pulsante destro del mouse sul segno di spunta per uno dei [!DNL .vw] file (ad esempio, [!DNL Workspaces.vw]), quindi fare clic **[!UICONTROL Make Local]**.

   Un segno di spunta per il file viene visualizzato nella [!DNL User] colonna.

1. Fare clic con il pulsante destro del mouse sul [!DNL .vw] file nella [!DNL User] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**.
1. Nel [!DNL Profile Path] campo, digitare la [!DNL Profile Manager] directory per la quale si desidera creare un nuovo manager. Accertatevi di includere la barra (/) dopo il nome della directory.

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

1. In Blocco note, fare clic **[!UICONTROL File]** > **[!UICONTROL Save As]** per salvare il file modificato nella cartella di installazione di *Workbench dati*\User\*nome profilo di lavoro*\Menu\Admin\Profile Management.

   Assicuratevi di cambiare il nome del [!DNL .vw] file in modo che rifletta la directory in cui [!DNL Profile Manager] corrisponde.

1. (Facoltativo) Per rendere disponibili le modifiche a tutti gli utenti del profilo di lavoro, fare clic con il pulsante destro del mouse sul [!DNL .vw] file nella [!DNL User] colonna e scegliere **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

