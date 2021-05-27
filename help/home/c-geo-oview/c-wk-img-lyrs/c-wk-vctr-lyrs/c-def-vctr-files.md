---
description: È possibile creare un livello vettoriale che faccia riferimento a uno o più file vettoriali (.vec), contenente i dati che definiscono i vettori da disegnare sul globo.
title: Definizione di livelli vettoriali con riferimento a file vettoriali
uuid: 162d4ecc-d305-42e3-a5d4-0c1609a40f29
exl-id: c6da3cd9-f42a-4e9c-ae48-9f4ffdc42f7b
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 7%

---

# Definizione di livelli vettoriali con riferimento a file vettoriali{#defining-vector-layers-referencing-vector-files}

È possibile creare un livello vettoriale che faccia riferimento a uno o più file vettoriali (.vec), contenente i dati che definiscono i vettori da disegnare sul globo.

Per definire un livello vettoriale che faccia riferimento a uno o più file [!DNL .vec]è necessario disporre dei seguenti elementi:

* Uno o più file [!DNL .vec]contenenti i dati utilizzati per disegnare i vettori sul globo.

   >[!NOTE]
   >
   >Per ottenere i file [!DNL .vec] da utilizzare con i livelli vettoriali, contatta l’Adobe.

* File di livello che specifica la posizione dei file [!DNL .vec]. Per ulteriori informazioni sul formato richiesto del file di livello, vedere [Formato del file di livello vettoriale](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-def-vctr-files.md#section-530d03f41ede4a339aebbb680e15240a).

   >[!NOTE]
   >
   >Il file [!DNL Boundaries.layer] fornito con il profilo [!DNL Geography] è un livello vettoriale che fa riferimento ai file [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec] e [!DNL mwisland.vec].

## Formato file livello vettoriale {#section-530d03f41ede4a339aebbb680e15240a}

Ogni file di livello vettoriale che fa riferimento a file [!DNL .vec]deve essere formattato utilizzando il seguente modello:

```
Layer = VectorLayer:
  Vec Files = vector: n items
    0 = string: Maps\\.vec file 1
    1 = string: Maps\\.vec file 2
    . . .
    n-1 = string: Maps\\.vec file n
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

| Parametro | Descrizione |
|---|---|
| File Vec | Percorso/i del file [!DNL .vec] contenente i dati vettoriali. |
| Colore | Il vettore del colore RGB, espresso come (rosso, verde, blu). Per ogni colore del vettore, è possibile immettere un valore compreso tra 0,0 e 1,0. Ad esempio, (1.0, 0.0, 0.0) è rosso chiaro e (0,5, 0,5, 0,5) è grigio. |
| Alfa | Controlla la trasparenza dei vettori mostrati sul globo. L&#39;intervallo è compreso tra 0 e 1, mentre 0 è il più trasparente. |
| Larghezza | Facoltativo. Imposta la larghezza dei dati in pixel. L&#39;intervallo consigliato è da 1 a 4. |
| Fattore errore | Controlla la precisione con cui vengono disegnati i vettori. Per valori più grandi, i vettori vengono disegnati con minore precisione ma più velocemente. Il valore predefinito è 5. |

Il file [!DNL Boundaries.layer] viene formattato come segue:

```
 Boundaries.layer file is formatted as follows:
Layer = VectorLayer:
  Vec Files = vector: 5 items
    0 = string: Maps\\mwnation.vec
    1 = string: Maps\\mwstate.vec
    2 = string: Maps\\mwcoast.vec
    3 = string: Maps\\mwlake.vec
    4 = string: Maps\\mwisland.vec
  Color = v3d: (.5,.5,1)
  Alpha = double: .5
  Error Factor = double: 4
```
