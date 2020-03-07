---
description: In matematica, la formula dell'aversina è un'equazione che dà distanze circolari tra due punti su una sfera identificata dalle loro longitudini e latitudini.
solution: Analytics
title: Haversine
topic: Data workbench
uuid: 835fa9dd-db70-4498-a03e-59595bc041fe
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Haversine{#haversine}

In matematica, la formula dell&#39;aversina è un&#39;equazione che dà distanze circolari tra due punti su una sfera identificata dalle loro longitudini e latitudini.

Come la formula, la [!DNL Haversine] trasformazione richiede due set di [!DNL Latitude] impostazioni e [!DNL Longitude] impostazioni, utilizzando questi quattro input per calcolare la distanza reale tra due posizioni sulla Terra.

Questa distanza può essere rappresentata come chilometri o chilometri cambiando il flag &quot;In chilometri&quot; da falso a vero.

![](assets/cfg_TransformationType_Haversine.png)

| Parametro | Descrizione | impostazione predefinita |
|---|---|---|
| Nome | Nome descrittivo della trasformazione. Potete inserire un nome qualsiasi qui. |  |
| Commenti | Facoltativo. Note sulla trasformazione. |  |
| Condizione | Condizioni in cui viene applicata la trasformazione. |  |
| Campo Latitude 1 | Latitudine del punto 1. |  |
| Campo Latitude 2 | Latitudine del punto 2. |  |
| Campo Longitudine 1 | La longitudine del punto 1. |  |
| Campo Longitudine 2 | La longitudine del punto 2. |  |
| Uscita | Una volta calcolato, il [!DNL Output] campo contiene le distanze tra i punti indicati come elementi in una dimensione. |  |

Ad esempio, se codificate in latitudine e longitudine il loro store come Lat1, Lon1 e utilizzate una ricerca IP lunga e lunga per i loro clienti, è possibile determinare le distanze verso un negozio che la maggior parte dei clienti acquista o da cui proviene.

>[!NOTE]
>
>Se si desidera identificare le distanze per altre posizioni, ogni singola posizione deve avere un proprio set di campi lat e lon.

