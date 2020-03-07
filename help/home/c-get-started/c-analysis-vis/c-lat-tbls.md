---
description: Le visualizzazioni della tabella di latenza sono tabelle che includono una dimensione di latenza, che è un tipo di dimensione derivata che misura il tempo trascorso dal verificarsi di un particolare evento.
solution: Analytics
title: Tabelle di latenza
topic: Data workbench
uuid: 8081540c-f96c-424e-802d-05d1be5a728d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Tabelle di latenza{#latency-tables}

Le visualizzazioni della tabella di latenza sono tabelle che includono una dimensione di latenza, che è un tipo di dimensione derivata che misura il tempo trascorso dal verificarsi di un particolare evento.

Potete definire l’evento effettuando le selezioni all’interno di una o più visualizzazioni e impostando tali selezioni come evento utilizzando l’opzione di menu di scelta rapida Imposta evento. Le tabelle di latenza sono particolarmente utili per tenere traccia dell’attività relativa a una campagna o a un particolare ordine cliente in cui si sta cercando una correlazione temporale.

Nelle tabelle di [!DNL Site]latenza sono incluse informazioni sulle sessioni dei visitatori che si sono verificate fino a sette giorni prima o dopo l’evento, ma è possibile configurare le tabelle di latenza per fornire informazioni sulle diverse dimensioni contabili e temporali. Consultate [Configurazione delle tabelle](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/c-config-ltcy-tbls.md#concept-7175c3defec64556994f0dfcccb7d15c)di latenza.

Gli elementi della dimensione padre, ad esempio una sessione, che fanno parte dell&#39;evento specifico selezionato, hanno una latenza pari a zero. A tutti gli altri elementi sono assegnate delle latenze che riflettono la distanza (nella dimensione temporale appropriata) dall&#39;evento.

L&#39;esempio seguente illustra come utilizzare la tabella di latenza.

**Identificare gli eventi dei valori in relazione a una campagna**

Supponiamo che desideriate monitorare l&#39;attività dei clienti nei sette giorni precedenti e successivi alla risposta a una particolare campagna pubblicitaria. Per visualizzare la latenza per una particolare campagna pubblicitaria, imposta la campagna di interesse come evento per la tabella di latenza.

La latenza nell&#39;area di lavoro sottostante è basata sulla selezione di Campaign 11566 (le sessioni in risposta a questa campagna).

![](assets/vis_Latency.png)

Una latenza di &quot;+0 giorni&quot; identifica le sessioni in risposta a Campaign 11566, così come tutte le altre sessioni per gli stessi clienti che si sono verificati nello stesso giorno.

Una latenza di &quot;-2 giorni&quot; identifica le sessioni per gli stessi clienti che si sono verificati due giorni prima che i clienti rispondessero alla campagna.

Una latenza di &quot;+7 giorni&quot; identifica le sessioni per gli stessi clienti che si sono verificati sette giorni dopo che hanno risposto alla campagna.

Oltre alle procedure elencate nelle sezioni seguenti, è possibile eseguire tutte le stesse operazioni che è possibile eseguire in una tabella, come gli elementi di ordinamento, gli elementi maschera, l&#39;aggiunta di una legenda di serie, l&#39;esportazione di dati e così via. For more information, see [Tables](../../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).

## Creare una tabella di latenza {#section-31a03031d9854ef7acc2462d4f37678d}

Per creare una tabella di latenza, si inizia effettuando una selezione, quindi impostando la selezione come evento per il quale si desidera tenere traccia della latenza.

1. Fai clic con il pulsante destro del mouse all’interno di un’area di lavoro e apri le visualizzazioni desiderate, che devono essere basate sulla dimensione numerabile utilizzata per configurare la tabella di latenza.

   Ad esempio, [!DNL Site] le visualizzazioni devono essere basate su sessioni.

1. Aprite una tabella di latenza vuota.
1. Effettuate una selezione nell’area di lavoro.
1. Fare clic con il pulsante destro del mouse all&#39;interno della tabella di latenza e scegliere **[!UICONTROL Set Event]**.

![](assets/vis_Latency_SetEvent.png)

>[!NOTE]
>
>Gli eventi selezionati non persistono a meno che non si salvino le selezioni come una dimensione di latenza. Per i passaggi, consultate [Riutilizzo di una dimensione](../../../home/c-get-started/c-analysis-vis/c-lat-tbls.md#section-29c6483bf9ba476fb1c24ad1df253f46)di latenza.

## Riutilizzare una tabella di latenza {#section-05f741169d204213b6537dce553e4f73}

Se desiderate utilizzare di nuovo la stessa tabella di latenza, potete salvare la tabella di latenza localmente oppure, se disponete delle autorizzazioni appropriate, potete salvarla sul server per tutti gli utenti di un particolare profilo a cui accedere.

**Salvataggio della tabella di latenza per l&#39;utilizzo in altre aree di lavoro**

1. Fai clic con il pulsante destro del mouse sul bordo superiore della visualizzazione e fai clic **[!UICONTROL Save]**. Viene [!DNL Save] visualizzata la finestra. Il percorso di salvataggio predefinito è la cartella Utente\*nome profilo*\Work.
1. Nel [!DNL File name] campo, digita un nome descrittivo per la visualizzazione e fai clic su **[!UICONTROL Save]**.

**Per recuperare la tabella di latenza salvata**

1. Fare clic con il pulsante destro del mouse nell&#39;area di lavoro e scegliere **[!UICONTROL Open]** > **[!UICONTROL File]**. Viene [!DNL Open Visualization] visualizzata la finestra.
1. Passate alla tabella di latenza salvata.
1. Selezionare il file di visualizzazione della tabella di latenza ( [!DNL *.vw]) e fare clic su **[!UICONTROL Open]**.

## Riutilizzare una dimensione di latenza {#section-29c6483bf9ba476fb1c24ad1df253f46}

Se desiderate utilizzare nuovamente la stessa dimensione di latenza, potete salvare la dimensione di latenza localmente oppure, se disponete delle autorizzazioni appropriate, potete salvarla sul server per tutti gli utenti di un particolare profilo a cui accedere.

Le eventuali dimensioni di latenza create vengono salvate nella directory Dimensions del profilo e sono disponibili nell&#39;elenco a [!DNL Change Dimension] discesa in Workbench dati.

**Salvataggio della dimensione della latenza per l&#39;utilizzo in altre aree di lavoro**

1. Fare clic con il pulsante destro del mouse sull&#39;etichetta della [!DNL Latency] colonna o su uno dei suoi elementi, quindi scegliere **[!UICONTROL Save Dimension]**. Viene [!DNL Save Dimension As] visualizzata la finestra.
1. Selezionare o creare la sottodirectory appropriata all&#39;interno della directory Dimensions.
1. Nel [!DNL File name] campo, digitate un nome descrittivo per la dimensione (ad esempio, [!DNL Latency for Campaign 11565.dim]) e fate clic su **[!UICONTROL Save]**.

**Per recuperare la dimensione di latenza salvata**

1. Fare clic con il pulsante destro del mouse nell&#39;area di lavoro e scegliere **[!UICONTROL Open]** > **[!UICONTROL File]**. Viene [!DNL Open Visualization] visualizzata la finestra.
1. Passate alla visualizzazione della latenza salvata nella cartella Utente\*nome profilo*\Dimensions.
1. Selezionate il file della dimensione della latenza ( [!DNL *.dim]) e fate clic su **[!UICONTROL Open]**.

## Esporta in Microsoft Excel {#section-3dffa5c3aab14cdaa40c78b81b08fe53}

Per informazioni sull&#39;esportazione delle finestre, vedere [Esportazione dei dati](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)delle finestre.

## Esportazione in un file TSV {#section-fd921f351c994ed0a94f63d3bd5b5a87}

Per informazioni sull&#39;esportazione delle finestre, vedere [Esportazione dei dati](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)delle finestre.
