---
description: Per impostazione predefinita, le schede appena create visualizzano le sottocartelle all’interno della directory associata come sottodirectory gerarchiche a discesa, anziché come sottoschede.
title: Visualizzare le sottocartelle come schede secondarie
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Visualizzare le sottocartelle come schede secondarie{#display-subfolders-as-subtabs}

Per impostazione predefinita, le schede appena create visualizzano le sottocartelle all’interno della directory associata come sottodirectory gerarchiche a discesa, anziché come sottoschede.

È possibile visualizzare le sottocartelle come schede secondarie (come mostrato nell&#39;esempio seguente) inserendo un file [!DNL empty folder.useTabs] nella cartella di installazione Data Workbench *nome profilo di lavoro*\Workspaces\*nome scheda* all&#39;interno della directory di installazione.

L’esempio seguente mostra la scheda [!DNL Custom] con sottodirectory a discesa.

![](assets/client-sub.png)

Se si inserisce un file [!DNL empty folder.useTabs] nella cartella Aree di lavoro\Personalizzato, tutte le sottocartelle all&#39;interno della cartella Personalizzato vengono visualizzate nelle schede secondarie [!DNL Worktop], come illustrato nell&#39;esempio seguente:

![](assets/client-sub2.png)

**Per visualizzare le sottocartelle come schede secondarie nel[!DNL Worktop]**

>[!NOTE]
>
>A ogni livello di directory deve essere associato un file [!DNL Tab Name.useTabs] affinché il contenuto della sottocartella venga visualizzato come sottoschede anziché come sottodirectory gerarchiche a discesa.

1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Workspaces]** per visualizzarne il contenuto.
1. Nella colonna *nome profilo di lavoro* fare clic con il pulsante destro del mouse sul segno di spunta relativo a uno dei file [!DNL folder.useTabs] e fare clic su **[!UICONTROL Copy]**.
1. Fai clic con il pulsante destro del mouse nella colonna [!DNL User] relativa alla cartella Workspace\*tab name* e fai clic su **[!UICONTROL Paste]**. Le sottocartelle all’interno di tale scheda vengono ora visualizzate come schede secondarie.
1. (Facoltativo) Per rendere questa modifica disponibile a tutti gli utenti del profilo di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta bianco relativo al file [!DNL new folder.useTabs] nella colonna [!DNL User] e fare clic su **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**.
