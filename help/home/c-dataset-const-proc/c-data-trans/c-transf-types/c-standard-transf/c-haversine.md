---
description: In matematica, la formula dell'aversina è un'equazione che dà le distanze di cerchio tra due punti su una sfera identificata dalle loro longitudini e latitudini.
title: Haversine
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
exl-id: e700c0a0-1a1a-4c56-bb4f-1deb1b39b059
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 4%

---

# Haversine{#haversine}

{{eol}}

In matematica, la formula dell&#39;aversina è un&#39;equazione che dà le distanze di cerchio tra due punti su una sfera identificata dalle loro longitudini e latitudini.

Come la formula, la [!DNL Haversine] per trasformare sono necessari due set di [!DNL Latitude] e [!DNL Longitude] impostazioni, utilizzando questi quattro input per calcolare la vera distanza attraverso la Terra tra due posizioni.

Questa distanza può essere rappresentata come chilometri o chilometri cambiando la bandiera &quot;In Chilometri&quot; da falso a vero.

![](assets/cfg_TransformationType_Haversine.png)

| Parametro | Descrizione | Impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. È possibile inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Le condizioni in cui viene applicata questa trasformazione. |  |
| Campo Latitude 1 | La latitudine del punto 1. |  |
| Campo Latitude 2 | La latitudine del punto 2. |  |
| Campo Longitudine 1 | La longitudine del punto 1. |  |
| Campo Longitudine 2 | La longitudine del punto 2. |  |
| Output | Una volta calcolato, il [!DNL Output] Il campo contiene le distanze tra i punti designati come elementi di un Dimension. |  |

Ad esempio, se si codifica in una latitudine e longitudine del loro negozio come Lat1, Lon1 e si utilizza una ricerca IP lunga e lunga per i loro clienti, è possibile determinare le distanze per un negozio dalla maggior parte dei clienti che acquistano o provengono da.

>[!NOTE]
>
>Se desideri identificare le distanze per altre posizioni, ogni singola posizione deve avere un proprio set di campi ultimo e lungo.
