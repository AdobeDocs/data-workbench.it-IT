---
description: All'interno della cartella Workspace della directory di installazione di Data Workbench, un file folder.lock specifica se le aree di lavoro in quella particolare cartella sono bloccate, mentre un file name.lock di workspace specifica se una particolare area di lavoro è bloccata.
title: File Folder.lock e workspace.lock
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# File Folder.lock e workspace.lock{#folder-lock-and-workspace-lock-files}

All&#39;interno della cartella Workspace della directory di installazione di Data Workbench, un file folder.lock specifica se le aree di lavoro in quella particolare cartella sono bloccate, mentre un file name.lock di workspace specifica se una particolare area di lavoro è bloccata.

Quando si bloccano intere cartelle, è possibile bloccarle a livello di cartella Area di lavoro o a livello di sottocartella (scheda). È inoltre possibile bloccare o sbloccare tutte le cartelle (a livello di cartella Area di lavoro), quindi specificare le eccezioni per sottocartelle particolari (utilizzando i file [!DNL folder.lock]) o aree di lavoro particolari (utilizzando i file *nome area di lavoro*.lock).

L&#39;esempio seguente di [!DNL Profile Manager] evidenzia tre elementi:

* Un file [!DNL folder.lock] per la cartella principale Area di lavoro
* Un file [!DNL Monthly Numbers.lock] per il file dell&#39;area di lavoro [!DNL Monthly Numbers.vw]

* Un file [!DNL folder.lock] per la sottocartella Workspace\Custom

![](assets/wsp_Locking_lockFiles.png)

In questo esempio, il file [!DNL Workspaces folder.lock] è impostato su bloccato, che blocca tutte le aree di lavoro in questa istanza di Data Workbench. Il file della sottocartella Area di lavoro\Cartella personalizzata [!DNL folder.lock] è impostato su sbloccato, che sblocca tutte le aree di lavoro nella scheda [!DNL Custom]. Infine, il file [!DNL Monthly Numbers.lock] è impostato su bloccato, che blocca l’area di lavoro Numeri mensili.

## Creazione di file .lock {#section-c4f78b4b43c347368a376904effb41d2}

Puoi creare un file [!DNL new folder.lock] utilizzando l’opzione [!DNL Create menu] in [!DNL Profile Manager] o [!DNL Workspaces Manager]. È inoltre possibile creare un file [!DNL folder.lock] o *nome area di lavoro*.lock copiando e incollando un file esistente [!DNL .lock] nella cartella appropriata, modificando il nome del file (solo per i file *nome area di lavoro*.lock) e modificando l&#39;impostazione nel file, se necessario.

**Per creare un nuovo file folder.lock**

1. In Data Workbench, apri il [!DNL Workspaces Manager] facendo clic con il pulsante destro del mouse all&#39;interno di un&#39;area di lavoro e facendo clic su **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Fare clic sulla cartella per la quale si desidera creare un file [!DNL folder.lock].
1. Nella colonna [!DNL User] relativa alla cartella, fai clic con il pulsante destro del mouse nella cella e fai clic su **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. Viene visualizzato un file [!DNL new folder.lock]. [!DNL New folder.lock] per impostazione predefinita, i file vengono  [] sbloccati.
1. (Facoltativo) Se devi modificare l’impostazione nel file :

   1. Fare clic con il pulsante destro del mouse sul segno di spunta del file.
   1. Fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Viene aperto il file [!DNL folder.lock] .

   1. Modifica l&#39;impostazione su [bloccato].
   1. Salva e chiudi il file.

1. Per impostare questo valore come impostazione per tutti gli utenti che utilizzano lo stesso profilo di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta del file e scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Le aree di lavoro in questa cartella vengono ora bloccate o sbloccate in base alle impostazioni nel nuovo file.

**Per creare un file .lock da un file esistente**

1. In [!DNL Profile Manager] o [!DNL Workspaces Manager] fare clic con il pulsante destro del mouse sul segno di spunta relativo a un file [!DNL .lock] esistente e fare clic su **[!UICONTROL Copy]**.
1. Nella colonna [!DNL User] relativa alla cartella in cui si desidera incollare il file [!DNL .lock], fare clic con il pulsante destro del mouse nella cella e fare clic su **[!UICONTROL Paste]**.
1. Se questo file viene utilizzato per bloccare una singola area di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta relativo al file [!DNL .lock] nella colonna [!DNL User] e modificare il nome nel campo [!DNL File] in modo che corrisponda al nome dell&#39;area di lavoro che si desidera bloccare.

   Ad esempio, per bloccare l&#39;area di lavoro [!DNL Monthly Numbers.vw], denominare il file &quot;[!DNL Monthly Numbers.lock]&quot;.Se questo file viene utilizzato per bloccare una singola area di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta relativo al file [!DNL .lock] nella colonna [!DNL User] e modificare il nome nel campo [!DNL File] in modo che corrisponda al nome dell&#39;area di lavoro che si desidera bloccare. Ad esempio, per bloccare l&#39;area di lavoro [!DNL Monthly Numbers.vw], denominare il file &quot;[!DNL Monthly Numbers.lock]&quot;.

1. Per modificare l’impostazione nel file:

   1. Fare clic con il pulsante destro del mouse sul segno di spunta del file.
   1. Fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. Viene aperto il file [!DNL .lock] .

   1. Modifica l&#39;impostazione su [bloccato] o [sbloccato].
   1. Salva e chiudi il file.

1. Per impostare questo valore come impostazione per tutti gli utenti che utilizzano lo stesso profilo di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta del file e scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Le aree di lavoro selezionate vengono ora bloccate o sbloccate in base alle impostazioni nel nuovo file.
