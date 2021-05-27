---
description: In matematica, la formula dell'aversina è un'equazione che dà le distanze di cerchio tra due punti su una sfera identificata dalle loro longitudini e latitudini.
title: Haversine
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
exl-id: e700c0a0-1a1a-4c56-bb4f-1deb1b39b059
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 3%

---

# Haversine{#haversine}

In matematica, la formula dell&#39;aversina è un&#39;equazione che dà le distanze di cerchio tra due punti su una sfera identificata dalle loro longitudini e latitudini.

Come la formula, la trasformazione [!DNL Haversine] richiede due set di impostazioni [!DNL Latitude] e [!DNL Longitude], utilizzando questi quattro input per calcolare la distanza effettiva sulla Terra tra due posizioni.

Questa distanza può essere rappresentata come chilometri o chilometri cambiando la bandiera &quot;In Chilometri&quot; da falso a vero.

![](assets/cfg_TransformationType_Haversine.png)

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| Campo Latitude 1 | La latitudine del punto 1. |  |
| Campo Latitude 2 | La latitudine del punto 2. |  |
| Campo Longitudine 1 | La longitudine del punto 1. |  |
| Campo Longitudine 2 | La longitudine del punto 2. |  |
| Uscita | Una volta calcolato, il campo [!DNL Output] contiene le distanze tra i punti designati come elementi in un Dimension. |  |

Ad esempio, se si codifica in una latitudine e longitudine del loro negozio come Lat1, Lon1 e si utilizza una ricerca IP lunga e lunga per i loro clienti, è possibile determinare le distanze per un negozio dalla maggior parte dei clienti che acquistano o provengono da.

>[!NOTE]
>
>Se desideri identificare le distanze per altre posizioni, ogni singola posizione deve avere un proprio set di campi ultimo e lungo.
