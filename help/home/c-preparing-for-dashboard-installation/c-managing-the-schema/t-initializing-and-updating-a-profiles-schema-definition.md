---
description: Inizializzazione e aggiornamento della definizione dello schema di un profilo
title: Inizializzazione e aggiornamento della definizione dello schema di un profilo
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# Inizializzazione e aggiornamento della definizione dello schema di un profilo{#initializing-and-updating-a-profile-s-schema-definition}

1. Apri il **[!UICONTROL Schema Builder]** per il profilo da configurare.
1. Durante il recupero dello schema dal profilo Insight viene visualizzato un messaggio **[!UICONTROL Loading]** . Il tempo necessario per caricare lo schema dipende dalla complessità del profilo caricato.
1. Al termine, verrà visualizzato un riepilogo delle differenze tra **[!UICONTROL Insight Schema]** nel riquadro a sinistra e **[!UICONTROL Dashboard Schema]** nel riquadro a destra. Questo riepilogo verrà visualizzato nella parte in basso a sinistra della finestra **[!UICONTROL Schema Builder]**.

   >[!NOTE]
   >
   >Quando si imposta lo schema per la prima volta, ogni metrica, dimensione e filtro verrà elencato in modo diverso rispetto allo schema del dashboard. Questo perché al momento gli oggetti schema del dashboard non esistono.

   ![](assets/schema_builder2.png)

1. Fai clic sul pulsante **[!UICONTROL Synchronize with Schema]** per sincronizzare tutte le metriche, le dimensioni e i filtri dalla vista Schema di Insight con la vista Schema del dashboard.
1. Al termine, viene visualizzato un messaggio che indica che non sono state rilevate differenze:

   ![](assets/diff_found.png)

1. Se si verificano degli errori con lo schema del dashboard, ad esempio metriche e dimensioni duplicate, è necessario correggerle manualmente prima di poter salvare.

   >[!NOTE]
   >
   >Puoi rimuovere in modo selettivo dagli utenti finali del dashboard le metriche, le dimensioni o i filtri che non desideri mostrare agli utenti finali. **[!UICONTROL Dashboard Schema]** Riceverai un avviso che segnala che gli elementi non sono presenti nello schema del dashboard, ma questo non impedisce il salvataggio.

1. Quando è pronto, fai clic su **[!UICONTROL Save]** per salvare le modifiche allo schema del dashboard.
1. Il sistema del dashboard utilizzerà questa definizione dello schema per compilare le dimensioni, le metriche e i filtri disponibili per gli utenti finali dell’interfaccia del dashboard.
