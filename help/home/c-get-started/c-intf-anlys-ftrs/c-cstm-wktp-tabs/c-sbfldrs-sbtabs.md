---
description: Per impostazione predefinita, le schede appena create visualizzano le sottocartelle all’interno della directory associata come sottodirectory gerarchiche a discesa, anziché come sottoschede.
title: Visualizzare le sottocartelle come schede secondarie
uuid: b4d7c6dd-d5ad-4b93-ba67-65a69e11eefc
exl-id: 6a05852b-3efc-4e71-9782-d4cc3a687a26
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 3%

---

# Visualizzare le sottocartelle come schede secondarie{#display-subfolders-as-subtabs}

{{eol}}

Per impostazione predefinita, le schede appena create visualizzano le sottocartelle all’interno della directory associata come sottodirectory gerarchiche a discesa, anziché come sottoschede.

È possibile visualizzare le sottocartelle come schede secondarie (come mostrato nell’esempio seguente) posizionando un [!DNL empty folder.useTabs] nel *nome profilo di lavoro*\Workspace\*cartella nome scheda* nella directory di installazione di Data Workbench.

L’esempio seguente mostra le [!DNL Custom] scheda con sottodirectory a discesa.

![](assets/client-sub.png)

Se si inserisce un [!DNL empty folder.useTabs] nella cartella Aree di lavoro\Personalizzato vengono visualizzate tutte le sottocartelle all&#39;interno della cartella Personalizzato nella cartella [!DNL Worktop] come schede secondarie, come illustrato nell’esempio seguente:

![](assets/client-sub2.png)

**Per visualizzare le sottocartelle come schede secondarie nel[!DNL Worktop]**

>[!NOTE]
>
>Ogni livello di directory deve avere un [!DNL Tab Name.useTabs] il contenuto della sottocartella deve essere visualizzato come sottoschede anziché come sottodirectory gerarchiche a discesa.

1. In [!DNL Profile Manager], fai clic su **[!UICONTROL Workspaces]** per visualizzarne il contenuto.
1. In *nome profilo di lavoro* fare clic con il pulsante destro del mouse sul segno di spunta per una delle colonne [!DNL folder.useTabs] file e fai clic su **[!UICONTROL Copy]**.
1. Fai clic con il pulsante destro del mouse nel [!DNL User] colonna per la cartella Workspace\*nome scheda* e fai clic su **[!UICONTROL Paste]**. Le sottocartelle all’interno di tale scheda vengono ora visualizzate come schede secondarie.
1. (Facoltativo) Per rendere questa modifica disponibile a tutti gli utenti del profilo di lavoro, fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL new folder.useTabs] nel [!DNL User] e fai clic su **[!UICONTROL Save to]** > &lt; **[!UICONTROL working profile name]**>
