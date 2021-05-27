---
description: Le visualizzazioni della tabella di latenza sono tabelle che includono una dimensione di latenza, un tipo di dimensione derivata che misura il tempo trascorso dal verificarsi di un particolare evento.
title: Tabelle di latenza
uuid: 8081540c-f96c-424e-802d-05d1be5a728d
exl-id: 22f6d52f-e1c2-430a-9e69-3440be0ecdea
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 1%

---

# Tabelle di latenza{#latency-tables}

Le visualizzazioni della tabella di latenza sono tabelle che includono una dimensione di latenza, un tipo di dimensione derivata che misura il tempo trascorso dal verificarsi di un particolare evento.

Puoi definire l’evento effettuando selezioni all’interno di una o più visualizzazioni e impostando tali selezioni come evento utilizzando l’opzione del menu di scelta rapida Imposta evento . Le tabelle di latenza sono particolarmente utili per monitorare l’attività relativa a una campagna o a un particolare ordine cliente in cui stai cercando una correlazione temporale.

In [!DNL Site] le tabelle di latenza forniscono informazioni sulle sessioni dei visitatori che si sono verificate fino a sette giorni prima o dopo l’evento, ma è possibile configurare tabelle di latenza per fornire informazioni su diverse dimensioni conteggiate e temporali. Consulta [Configurazione delle tabelle di latenza](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/c-config-ltcy-tbls.md#concept-7175c3defec64556994f0dfcccb7d15c).

Gli elementi della dimensione padre, ad esempio una sessione, che fanno parte dell’evento specifico selezionato, hanno una latenza di zero. A tutti gli altri elementi vengono assegnate delle latenze che riflettono la distanza (nella dimensione temporale appropriata) dall’evento.

L’esempio seguente illustra come utilizzare la tabella di latenza.

**Identificare eventi di valore in relazione a una campagna**

Supponiamo che desideri tenere traccia dell’attività dei clienti nei sette giorni precedenti e successivi alla risposta a una particolare campagna pubblicitaria. Per visualizzare la latenza di una determinata campagna pubblicitaria, imposta la campagna di interesse come evento per la tabella di latenza.

La latenza nell’area di lavoro sottostante si basa sulla selezione di Campaign 11566 (le sessioni in risposta a questa campagna).

![](assets/vis_Latency.png)

Una latenza di &quot;+0 giorni&quot; identifica le sessioni in risposta a Campaign 11566, nonché tutte le altre sessioni per gli stessi clienti che si sono verificate lo stesso giorno.

Una latenza di &quot;-2 giorni&quot; identifica le sessioni per gli stessi clienti che si sono verificate due giorni prima che i clienti rispondessero alla campagna.

Una latenza di &quot;+7 giorni&quot; identifica le sessioni per gli stessi clienti che si sono verificati sette giorni dopo la risposta alla campagna.

Oltre alle procedure elencate nelle sezioni seguenti, è possibile eseguire tutte le stesse operazioni che è possibile eseguire in una tabella, ad esempio gli elementi di ordinamento, gli elementi maschera, aggiungere una legenda di serie, esportare i dati e così via. Per ulteriori informazioni, consulta [Tabelle](../../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).

## Creare una tabella di latenza {#section-31a03031d9854ef7acc2462d4f37678d}

Per creare una tabella di latenza, inizia effettuando una selezione, quindi impostando la selezione come evento per il quale desideri tenere traccia della latenza.

1. Fai clic con il pulsante destro del mouse all’interno di un’area di lavoro e apri le visualizzazioni desiderate, che devono essere basate sulla dimensione numerabile utilizzata per configurare la tabella di latenza.

   Ad esempio, in [!DNL Site] le visualizzazioni devono essere basate su sessioni.

1. Apri una tabella di latenza vuota.
1. Effettua una selezione nell’area di lavoro.
1. Fai clic con il pulsante destro del mouse all’interno della tabella di latenza e fai clic su **[!UICONTROL Set Event]**.

![](assets/vis_Latency_SetEvent.png)

>[!NOTE]
>
>Gli eventi selezionati non persistono a meno che non si salvino le selezioni come dimensione di latenza. Per i passaggi, consulta [Riutilizzo di un Dimension di latenza](../../../home/c-get-started/c-analysis-vis/c-lat-tbls.md#section-29c6483bf9ba476fb1c24ad1df253f46).

## Riutilizzare una tabella di latenza {#section-05f741169d204213b6537dce553e4f73}

Se desideri utilizzare nuovamente la stessa tabella di latenza, puoi salvare la tabella di latenza localmente oppure, se disponi delle autorizzazioni appropriate, puoi salvarla sul server affinché tutti gli utenti di un particolare profilo possano accedervi.

**Salvataggio della tabella di latenza da utilizzare in altre aree di lavoro**

1. Fai clic con il pulsante destro del mouse sul bordo superiore della visualizzazione e fai clic su **[!UICONTROL Save]**. Viene visualizzata la finestra [!DNL Save]. Il percorso di salvataggio predefinito è la cartella User\*profile name*\Work.
1. Nel campo [!DNL File name] , digita un nome descrittivo per la visualizzazione e fai clic su **[!UICONTROL Save]**.

**Per recuperare la tabella di latenza salvata**

1. Fai clic con il pulsante destro del mouse nell’area di lavoro e fai clic su **[!UICONTROL Open]** > **[!UICONTROL File]**. Viene visualizzata la finestra [!DNL Open Visualization].
1. Passa alla tabella di latenza salvata.
1. Seleziona il file di visualizzazione della tabella di latenza ( [!DNL *.vw]) e fai clic su **[!UICONTROL Open]**.

## Riutilizzare una dimensione di latenza {#section-29c6483bf9ba476fb1c24ad1df253f46}

Se desideri utilizzare nuovamente la stessa dimensione di latenza, puoi salvare la dimensione di latenza localmente oppure, se disponi delle autorizzazioni appropriate, puoi salvarla sul server affinché tutti gli utenti di un particolare profilo possano accedervi.

Le dimensioni di latenza create vengono salvate nella directory dei Dimension del profilo e sono disponibili nell’elenco a discesa [!DNL Change Dimension] all’interno di Data Workbench.

**Salvataggio della dimensione di latenza da utilizzare in altre aree di lavoro**

1. Fai clic con il pulsante destro del mouse sull’etichetta di colonna [!DNL Latency] o su uno dei relativi elementi e fai clic su **[!UICONTROL Save Dimension]**. Viene visualizzata la finestra [!DNL Save Dimension As].
1. Seleziona o crea la sottodirectory appropriata all’interno della directory dei Dimension.
1. Nel campo [!DNL File name] , digita un nome descrittivo per la dimensione (ad esempio, [!DNL Latency for Campaign 11565.dim]) e fai clic su **[!UICONTROL Save]**.

**Per recuperare la dimensione di latenza salvata**

1. Fai clic con il pulsante destro del mouse nell’area di lavoro e fai clic su **[!UICONTROL Open]** > **[!UICONTROL File]**. Viene visualizzata la finestra [!DNL Open Visualization].
1. Passa alla visualizzazione della latenza salvata nella cartella User\*profile name*\Dimension .
1. Seleziona il file della dimensione di latenza ( [!DNL *.dim]) e fai clic su **[!UICONTROL Open]**.

## Esportare in Microsoft Excel {#section-3dffa5c3aab14cdaa40c78b81b08fe53}

Per informazioni sull&#39;esportazione di finestre, vedere [Esportazione di dati di finestre](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).

## Esportare in un file TSV {#section-fd921f351c994ed0a94f63d3bd5b5a87}

Per informazioni sull&#39;esportazione di finestre, vedere [Esportazione di dati di finestre](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
