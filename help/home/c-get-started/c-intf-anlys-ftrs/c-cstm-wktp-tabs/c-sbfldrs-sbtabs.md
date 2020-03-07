---
description: Per impostazione predefinita, le schede create di recente visualizzano le sottocartelle all'interno della directory associata come sottodirectory gerarchiche a discesa invece che come sottoschede.
solution: Analytics
title: Visualizzare le sottocartelle come schede secondarie
topic: Data workbench
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Visualizzare le sottocartelle come schede secondarie{#display-subfolders-as-subtabs}

Per impostazione predefinita, le schede create di recente visualizzano le sottocartelle all&#39;interno della directory associata come sottodirectory gerarchiche a discesa invece che come sottoschede.

È possibile visualizzare le sottocartelle come schede secondarie (come illustrato nell&#39;esempio seguente) inserendo un [!DNL empty folder.useTabs] file nel nome del profilo *di lavoro*\Workspaces\*tab name folder* all&#39;interno della directory di installazione di Workbench dati.

L&#39;esempio seguente mostra la [!DNL Custom] scheda con sottodirectory a discesa.

![](assets/client-sub.png)

Se inserite un [!DNL empty folder.useTabs] file nella cartella Workspaces\Custom, tutte le sottocartelle all&#39;interno della cartella Custom vengono visualizzate nelle [!DNL Worktop] schede secondarie, come illustrato nell&#39;esempio seguente:

![](assets/client-sub2.png)

**Per visualizzare le sottocartelle come schede secondarie nella finestra di dialogo[!DNL Worktop]**

>[!NOTE]
>
>A ciascun livello di directory deve essere associato un [!DNL Tab Name.useTabs] file per consentire al contenuto della sottocartella di essere visualizzato come sottoschede invece che come sottodirectory gerarchiche a discesa.

1. Nella [!DNL Profile Manager], fate clic **[!UICONTROL Workspaces]** per visualizzarne il contenuto.
1. Nella colonna del nome *del profilo di* lavoro, fare clic con il pulsante destro del mouse sul segno di spunta per uno dei [!DNL folder.useTabs] file e fare clic **[!UICONTROL Copy]**.
1. Fare clic con il pulsante destro del mouse nella [!DNL User] colonna relativa alla cartella Workspaces\*tab name*, quindi fare clic su **[!UICONTROL Paste]**. Le sottocartelle all&#39;interno di tale scheda ora vengono visualizzate come sottoschede.
1. (Facoltativo) Per rendere disponibile questa modifica a tutti gli utenti del profilo di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta bianco del [!DNL new folder.useTabs] file nella [!DNL User] colonna e scegliere **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>.

