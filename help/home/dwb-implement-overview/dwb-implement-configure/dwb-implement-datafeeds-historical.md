---
description: Una guida rapida per i passaggi minimi necessari per convalidare e impostare feed di dati storici.
title: Convalida dei feed di dati cronologici
uuid: 83d2d48b-0966-4f4e-9c9c-60473c4546b2
exl-id: 5a5e2cca-2fab-48a0-b58d-a8c46114b9a0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 5%

---

# Convalida dei feed di dati cronologici{#validating-historical-data-feeds}

{{eol}}

Una guida rapida per i passaggi minimi necessari per convalidare e impostare feed di dati storici.

## Passaggi di convalida per la coerenza dei feed di dati {#section-777b2c627a354627a02feb9461e23038}

1. Accedi a *dentatura* (https://oasis.omniture.com/drteeth/)
1. Vai a Amministratore di SiteCatalyst -> Definizione feed dati (nuova)
1. Passa alla posizione del server (es. Dallas, Londra..) A seconda della posizione dell’organizzazione.
1. Fornisci RSID e seleziona il tipo di feed Insight e fai clic su *ricerca*.

   ![](assets/dwb_impl_historical.png)

1. Identifica il nome effettivo del feed per il cliente.
1. Fare clic su Cronologia nella sezione Azioni. ![](assets/dwb_impl_historical1.png)

   Controlla il campo di stato per eventuali errori e nel caso in cui alcuni feed siano in stato di errore, seleziona il feed e fai clic su rielabora. Se l&#39;errore si è verificato per più richieste, invia un&#39;e-mail a *`dataworkbench@adobe.com`* con ID feed e dettagli suite per report da rielaborare.

1. La post-convalida controlla i registri nella cartella raw del percorso NAS.
