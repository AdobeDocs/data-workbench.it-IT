---
description: Per impostazione predefinita, la chiusura di un’area di lavoro sbloccata consente di salvare le modifiche apportate all’area di lavoro.
title: Salvare un’area di lavoro
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
exl-id: 0f1052f5-496c-443e-b29d-5973c16ef527
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# Salvare un’area di lavoro{#save-a-workspace}

Per impostazione predefinita, la chiusura di un’area di lavoro sbloccata consente di salvare le modifiche apportate all’area di lavoro.

Se l&#39;area di lavoro è un&#39;area di lavoro del server, le modifiche vengono salvate solo localmente, a meno che l&#39;area di lavoro aggiornata non venga salvata specificatamente nel server Data Workbench. Per ulteriori informazioni sulle aree di lavoro bloccate, vedere [Sblocco di un&#39;area di lavoro](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).

## Salvare un’area di lavoro localmente {#section-3f331c880f1a490c96844103c2432d61}

Il percorso di salvataggio predefinito è la cartella **Utente\profilo name\Workspaces\tab name** all&#39;interno della directory di installazione di Data Workbench. Ad esempio, se lavori con il profilo Filmati e salvi un’area di lavoro localmente dalla scheda [!UICONTROL Custom] , l’area di lavoro viene salvata nella cartella **User\Movies\Workspaces\Custom** nella directory di installazione di Data Workbench.

**Per salvare le modifiche in un’area di lavoro**

* Nell’area di lavoro, fai clic su **[!UICONTROL File]**, quindi **[!UICONTROL Save]**.

**Per salvare un’area di lavoro esistente come nuova area di lavoro**

1. Nella scheda [!DNL Worktop] desiderata, fai clic sulla miniatura dell’area di lavoro da visualizzare.
1. Nell’area di lavoro, fai clic su **[!UICONTROL File]**, quindi fai clic su **[!UICONTROL Save Copy As]**.
1. Nella finestra di dialogo [!DNL Save Workspace As], specifica il nome e il percorso in cui salvare l&#39;area di lavoro copiata e fai clic su **[!UICONTROL Save]**.

## Salvare un’area di lavoro sul server di Data Workbench {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>Solo gli utenti con le autorizzazioni appropriate possono salvare le aree di lavoro nel server Data Workbench. Per ulteriori informazioni, contattare l&#39;amministratore di sistema.

Il salvataggio delle aree di lavoro nel server di Data Workbench connesso viene anche definito pubblicazione di un’area di lavoro, in quanto rende l’area di lavoro disponibile ad altri utenti. Per impostazione predefinita, le aree di lavoro vengono salvate nella cartella *nome profilo di lavoro*\Workspaces\*nome scheda* del server Data Workbench. Ad esempio, se lavori con il profilo Filmati e salvi un’area di lavoro nel server di Data Workbench connesso dalla scheda [!DNL Custom] , l’area di lavoro viene salvata nella cartella Movies\Workspaces\Custom folder of the Data Workbench server.

**Salvataggio di un&#39;area di lavoro nel server Data Workbench**

* Nella scheda [!DNL Worktop] desiderata, fare clic con il pulsante destro del mouse sulla miniatura dell&#39;area di lavoro che si desidera salvare nel server Data Workbench e fare clic su **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
