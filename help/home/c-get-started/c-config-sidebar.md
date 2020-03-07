---
description: La barra laterale consente di accedere alle funzioni utilizzate regolarmente e mantiene le visualizzazioni quando si passa da un’area di lavoro all’altra.
solution: Analytics
title: Configurare la barra laterale
topic: Data workbench
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurare la barra laterale{#configure-the-sidebar}

La barra laterale consente di accedere alle funzioni utilizzate regolarmente e mantiene le visualizzazioni quando si passa da un’area di lavoro all’altra.

Gli amministratori possono personalizzare una barra laterale per renderla appropriata per diversi gruppi di utenti, quindi distribuire la barra laterale con un profilo.

La barra laterale è ideale per tenere traccia dei filtri e delle sostituzioni locali. Se preferite non usare la barra laterale, potete nasconderla.

## Aggiungere visualizzazioni alla barra laterale {#section-666f70a405db4f8d8eaffa567ffcac06}

1. Avvia Workbench dati.
1. Nella barra laterale, fate clic su **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]**>*. For example, [!DNL Selections Panel], [!DNL Filters Panel], or [!DNL Table].

   Nell&#39;installazione standard di Workbench dati sono disponibili i seguenti pannelli della barra laterale. Altri elementi potrebbero essere disponibili nel profilo specifico:

   * **Pannello Selezioni:** Consente di comprendere le selezioni attive nell’area di lavoro corrente. Gli [!DNL Selections Panel] aggiornamenti vengono eseguiti ogni volta che si effettua una nuova selezione. Per cancellare le selezioni, fate clic **[!UICONTROL x]**. Consulta [Selezione in Visualizzazioni](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746) per informazioni sulla selezione dei dati.
   * **Pannello Filtri:** Facilita il caricamento e l&#39;applicazione dei filtri salvati. Potete caricare più filtri e attivarli o disattivarli singolarmente facendo clic sulla casella di controllo accanto ad essi. Consultate [Filtra editor](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **Pannello Override locale:** Questo pannello mostra le metriche, le dimensioni e i filtri presenti nel profilo che sono stati modificati nella copia personale del profilo. In questo modo è possibile rilevare eventuali differenze tra il modo in cui i dati vengono visualizzati nel client e quello di altri utenti. Quando salvate le modifiche in una metrica, dimensione o filtro sul server, l’override viene rimosso dall’ [!DNL Local Overrides panel]. Se fate clic su un override e quindi su **[!UICONTROL Revert to Server]**, l&#39;override locale viene rimosso e l&#39;elemento viene ripristinato alla versione condivisa.
   * **Legenda metrica:** Aggiunge una legenda metrica. [!DNL Metric legends] consente di visualizzare le metriche di base correlate al profilo e alle statistiche correlate al set di dati (o alla selezione corrente, se è stata effettuata). Consulta Legende [](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b)metriche.
   * **Legenda colore:** Aggiunge una legenda del colore. Puoi colorare le visualizzazioni del codice in base alle metriche, come Conversione e Mantenimento, e utilizzarle in quasi ogni [!DNL Workspace]. Collegando le metriche aziendali ai colori è più facile individuare anomalie, eccezioni e tendenze. Consultate Legende [a](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358)colori.
   * **Annotazione testo:** Aggiunge un pannello Note. [!DNL Text annotations] sono finestre in cui è possibile immettere testo arbitrario per aggiungere informazioni o commenti descrittivi a un [!DNL Workspace]. Vedere [Uso delle annotazioni](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777)di testo.
   * **Tabella:** Aggiunge una tabella. Una tabella può visualizzare una o più metriche in una o più dimensioni di dati. Vedere [Tabelle](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **Apri:** Apre un file salvato.

## Aprire un pannello della barra laterale {#section-cbc8e57491854274a577d47a48c306b8}

Potete aprire un file di visualizzazione della barra laterale da una posizione salvata o dagli Appunti.

1. In the sidebar, click **[!UICONTROL Add]** > **[!UICONTROL Open]**.
1. Fate clic **[!UICONTROL File]** per individuare il [!DNL .vw] file del pannello da aggiungere, oppure fate clic su **[!UICONTROL Last Closed Window]**, per estrarre la visualizzazione dagli Appunti.

   Inoltre, puoi fare clic **[!UICONTROL From Clipboard]** per incollare una visualizzazione copiata negli Appunti. Consultate [Copia del pannello](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1)Barra laterale.

## Copia di un pannello della barra laterale {#section-720ae057632a4b8dbb94412e06a370b1}

1. Fate clic con il pulsante destro del mouse sul bordo superiore del pannello, quindi fate clic su **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. Per incollare il pannello, fate clic su **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**.

## Salvataggio di un pannello della barra laterale {#section-fb19936b12704fb0a4c592abb579db1d}

In un pannello laterale, fate clic con il pulsante destro del mouse nella barra del titolo e fate clic **[!UICONTROL Save]**.

Analogamente, potete aprire una visualizzazione della barra laterale salvata. Workbench dati salva la visualizzazione come [!DNL .vw] file nella posizione specificata.

## Ripristina la barra laterale predefinita {#section-4d14b8771ad747bba799876267f24831}

In the sidebar, click **[!UICONTROL Options]** > **[!UICONTROL Revert]**.

Quando si chiude Workbench dati, il sistema salva la configurazione corrente della barra laterale nel [!DNL sidebar.vw] file nel profilo utente. Quando si apre Workbench dati, il sistema carica il [!DNL sidebar.vw] file dal profilo utente anziché da un profilo principale.

Potete ripristinare una barra laterale predefinita o salvata in precedenza, che elimina la barra laterale dal profilo utente e ricarica la barra laterale dal profilo principale. Gli amministratori possono sostituire la barra laterale predefinita (principale) con una barra laterale locale caricandola dalla barra [!DNL Profile Manager].

## Personalizzare il file del pannello di stato Altro {#section-8d502f3b59cc4331966edec05e896ce1}

Gli amministratori di sistema possono creare formule nel [!DNL More Status Panel.vw]. In questo modo vengono inserite parole contestuali intorno ai valori delle metriche e delle dimensioni e i risultati vengono visualizzati nella barra [!DNL More Status panel] laterale.

Per visualizzare la barra [!DNL More Status panel] laterale, fate clic sulle frecce mostrate nell’esempio seguente.

![](assets/more_status_panel_arrows.png)

La procedura seguente mostra un semplice esempio di come creare uno stato personalizzato che indica quanti giorni ci sono in un dataset:

1. Nella barra [!DNL Profile Manager], fate clic su **[!UICONTROL Sidebar\]**.

1. Nella [!DNL Base_5_3*] colonna, create una copia locale del [!DNL More Status Panel.vw] file.

   A tal fine, fare clic con il pulsante destro del mouse sul segno di spunta del file e fare clic **[!UICONTROL Make Local]**.

1. Aprite il [!DNL More Status Panel.vw] file in [!DNL .vw] [!DNL Editor] o in Blocco note.

   ![](assets/more_status_panel_file.png)

1. Compila i campi [!DNL Context] e [!DNL Items] nella [!DNL Editor]. Per informazioni sulla sintassi, consultate Sintassi [del linguaggio di](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) query.

1. Salvate il file.

   I valori dell&#39;esempio precedente generano una formula di stato visualizzata come segue:

   ![](assets/more_status_panel.png)

