---
description: 'null'
solution: Analytics
title: Inizializzazione e aggiornamento della definizione dello schema di un profilo
topic: Data workbench
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Inizializzazione e aggiornamento della definizione dello schema di un profilo{#initializing-and-updating-a-profile-s-schema-definition}

1. Aprite il **[!UICONTROL Schema Builder]** profilo da impostare.
1. Durante il recupero dello schema dal profilo **[!UICONTROL Loading]** Insight viene visualizzato un messaggio. Il tempo di caricamento dello schema dipende dalla complessità del profilo in fase di caricamento.
1. Al termine, verrà visualizzato un riepilogo delle differenze tra il riquadro **[!UICONTROL Insight Schema]** a sinistra e il riquadro **[!UICONTROL Dashboard Schema]** a destra. Il riepilogo verrà visualizzato nella parte inferiore sinistra della **[!UICONTROL Schema Builder]** finestra.

   >[!NOTE]
   >
   >Quando si imposta lo schema per la prima volta, ogni metrica, dimensione e filtro verrà elencata in modo diverso rispetto allo schema del dashboard. Questo perché al momento gli oggetti schema del dashboard non esistono.

   ![](assets/schema_builder2.png)

1. Fate clic sul **[!UICONTROL Synchronize with Schema]** pulsante per sincronizzare tutte le metriche, le dimensioni e i filtri dalla vista Schema di Insight con la vista Schema dashboard.
1. Al termine, compare un messaggio che indica che non sono state rilevate differenze:

   ![](assets/diff_found.png)

1. Se si verificano errori con lo schema dashboard, ad esempio metriche e dimensioni duplicate, è necessario correggerle manualmente prima di poter salvare.

   >[!NOTE]
   >
   >Potete rimuovere in modo selettivo metriche, dimensioni o filtri da quelle **[!UICONTROL Dashboard Schema]** che non desiderate vengano visualizzate agli utenti finali del dashboard. Viene visualizzato un messaggio di avviso che segnala che gli elementi non sono presenti nello schema del dashboard, ma non ne impedisce il salvataggio.

1. Una volta pronti, fate clic **[!UICONTROL Save]** per salvare le modifiche allo schema del dashboard.
1. Il sistema dashboard utilizzerà questa definizione dello schema per compilare le dimensioni, le metriche e i filtri disponibili per gli utenti finali dell&#39;interfaccia del dashboard.
