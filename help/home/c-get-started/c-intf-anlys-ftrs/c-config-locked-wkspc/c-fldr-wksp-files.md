---
description: All'interno della cartella Workspaces della directory di installazione di Data Workbench, un file folder.lock specifica se le aree di lavoro in quella particolare cartella sono bloccate, mentre un file name.lock di workspace specifica se una particolare area di lavoro è bloccata.
title: File Folder.lock e workspace.lock
uuid: d4c69e16-0596-4542-854f-bc614167ae80
exl-id: 980b8692-8aa5-481f-b6bc-33836d8a3a76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 1%

---

# File Folder.lock e workspace.lock{#folder-lock-and-workspace-lock-files}

{{eol}}

All&#39;interno della cartella Workspaces della directory di installazione di Data Workbench, un file folder.lock specifica se le aree di lavoro in quella particolare cartella sono bloccate, mentre un file name.lock di workspace specifica se una particolare area di lavoro è bloccata.

Quando si bloccano intere cartelle, è possibile bloccarle a livello di cartella Area di lavoro o a livello di sottocartella (scheda). È inoltre possibile bloccare o sbloccare tutte le cartelle (a livello di cartella Area di lavoro), quindi specificare le eccezioni per particolari sottocartelle (utilizzando [!DNL folder.lock] file) o particolari aree di lavoro (utilizzando *nome area di lavoro*.lock).

L&#39;esempio seguente del [!DNL Profile Manager] evidenzia tre elementi:

* A [!DNL folder.lock] file per la cartella principale Area di lavoro
* A [!DNL Monthly Numbers.lock] per [!DNL Monthly Numbers.vw] file workspace

* A [!DNL folder.lock] file per la sottocartella Area di lavoro\Personalizzato

![](assets/wsp_Locking_lockFiles.png)

In questo esempio, la [!DNL Workspaces folder.lock] file è impostato su bloccato, che blocca tutte le aree di lavoro in questa istanza di Data Workbench. Cartella di lavoro\Cartella personalizzata [!DNL folder.lock] il file è impostato su sbloccato, che sblocca tutte le aree di lavoro nel [!DNL Custom] scheda . Infine, la [!DNL Monthly Numbers.lock] il file è impostato su bloccato, che blocca l’area di lavoro Numeri mensili.

## Creazione di file .lock {#section-c4f78b4b43c347368a376904effb41d2}

Puoi creare una [!DNL new folder.lock] utilizzando [!DNL Create menu] in [!DNL Profile Manager] o [!DNL Workspaces Manager]. Puoi anche creare una [!DNL folder.lock] o *nome area di lavoro*.lock copiando e incollando un file esistente [!DNL .lock] nella cartella appropriata, modificando il nome del file (per *nome area di lavoro*.lock (solo file) e, se necessario, modificare l&#39;impostazione nel file.

**Per creare un nuovo file folder.lock**

1. In Data Workbench, apri la [!DNL Workspaces Manager] facendo clic con il pulsante destro del mouse all’interno di un’area di lavoro e facendo clic su **[!UICONTROL Manage]** > **[!UICONTROL Profile]** > **[!UICONTROL Workspaces Manager]**.
1. Fare clic sulla cartella per la quale si desidera creare una [!DNL folder.lock] file.
1. In [!DNL User] fare clic con il pulsante destro del mouse nella cella e fare clic su **[!UICONTROL Create]** > **[!UICONTROL folder.lock]**. A [!DNL new folder.lock] viene visualizzato il file . [!DNL New folder.lock] i file sono impostati su [sbloccato] per impostazione predefinita.
1. (Facoltativo) Se devi modificare l’impostazione nel file :

   1. Fare clic con il pulsante destro del mouse sul segno di spunta del file.
   1. Fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. La [!DNL folder.lock] viene aperto il file .

   1. Cambia l’impostazione in [bloccato].
   1. Salva e chiudi il file.

1. Per impostare questo valore come impostazione per tutti gli utenti che utilizzano lo stesso profilo di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta del file e fare clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Le aree di lavoro in questa cartella vengono ora bloccate o sbloccate in base alle impostazioni nel nuovo file.

**Per creare un file .lock da un file esistente**

1. In [!DNL Profile Manager] o [!DNL Workspaces Manager], fai clic con il pulsante destro del mouse sul segno di spunta per un [!DNL .lock] e fai clic su **[!UICONTROL Copy]**.
1. In [!DNL User] della cartella in cui si desidera incollare [!DNL .lock] file, fare clic con il pulsante destro del mouse nella cella e fare clic su **[!UICONTROL Paste]**.
1. Se questo file viene utilizzato per bloccare una singola area di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta per [!DNL .lock] nel [!DNL User] e modificarne il nome nella colonna [!DNL File] per corrispondere al nome dell’area di lavoro che si desidera bloccare.

   Ad esempio, per bloccare il [!DNL Monthly Numbers.vw] workspace, assegnare un nome al file &quot; [!DNL Monthly Numbers.lock].&quot;Se questo file viene utilizzato per bloccare una singola area di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta per [!DNL .lock] nel [!DNL User] e modificarne il nome nella colonna [!DNL File] per corrispondere al nome dell’area di lavoro che si desidera bloccare. Ad esempio, per bloccare il [!DNL Monthly Numbers.vw] workspace, assegnare un nome al file &quot; [!DNL Monthly Numbers.lock].&quot;

1. Per modificare l’impostazione nel file:

   1. Fare clic con il pulsante destro del mouse sul segno di spunta del file.
   1. Fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Notepad]**. La [!DNL .lock] viene aperto il file .

   1. Cambia l’impostazione in [bloccato] o [sbloccato].
   1. Salva e chiudi il file.

1. Per impostare questo valore come impostazione per tutti gli utenti che utilizzano lo stesso profilo di lavoro, fare clic con il pulsante destro del mouse sul segno di spunta del file e fare clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL working profile name]**>*.

Le aree di lavoro selezionate vengono ora bloccate o sbloccate in base alle impostazioni nel nuovo file.
