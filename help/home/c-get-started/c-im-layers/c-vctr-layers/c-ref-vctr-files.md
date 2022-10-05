---
description: È possibile creare un livello vettoriale che faccia riferimento a uno o più file vettoriali (.vec), contenente i dati che definiscono i vettori da disegnare sul globo.
title: Definire i livelli vettoriali che fanno riferimento a file vettoriali
uuid: fe6639fb-98fb-4246-9cc1-1a928df6ae0a
exl-id: d78fa7ea-e2a9-42b7-9071-5f72409c5b7a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '281'
ht-degree: 7%

---

# Definire i livelli vettoriali che fanno riferimento a file vettoriali{#define-vector-layers-referencing-vector-files}

{{eol}}

È possibile creare un livello vettoriale che faccia riferimento a uno o più file vettoriali (.vec), contenente i dati che definiscono i vettori da disegnare sul globo.

Per definire un livello vettoriale che faccia riferimento a uno o più [!DNL .vec] file, devi disporre dei seguenti elementi:

* **Uno o più [!DNL .vec] file** che contengono i dati utilizzati per disegnare i vettori sul globo.

   >[!NOTE]
   >
   >Per ottenere [!DNL .vec] file da utilizzare con i livelli vettoriali, contattare Adobe.

* **Un file di livello** specifica la posizione della [!DNL .vec] file. Per ulteriori informazioni sul formato richiesto del file di livello, vedi [Formato file livello vettoriale](../../../../home/c-get-started/c-im-layers/c-vctr-layers/c-ref-vctr-files.md#section-83a0077cf0c8479b9e7b2939bc761af1).

   >[!NOTE]
   >
   >La [!DNL Boundaries.layer] file, fornito con [!DNL Geography] è un livello vettoriale che fa riferimento a [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec]e [!DNL mwisland.vec] file.

## Formato del file del livello vettoriale {#section-83a0077cf0c8479b9e7b2939bc761af1}

Ciascun file vettoriale che fa riferimento a [!DNL .vec] i file devono essere formattati utilizzando il seguente modello:

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
| File Vec | Percorso/i verso il [!DNL .vec] file contenenti i dati vettoriali. |
| Colore | Il vettore del colore RGB, espresso come (rosso, verde, blu). Per ogni colore del vettore, è possibile immettere un valore compreso tra 0,0 e 1,0. Ad esempio, (1.0, 0.0, 0.0) è rosso chiaro e (0,5, 0,5, 0,5) è grigio. |
| Alfa | Controlla la trasparenza dei vettori mostrati sul globo. L&#39;intervallo è compreso tra 0 e 1, mentre 0 è il più trasparente. |
| Larghezza | Facoltativo. Imposta la larghezza dei dati in pixel. L&#39;intervallo consigliato è da 1 a 4. |
| Fattore errore | Controlla la precisione con cui vengono disegnati i vettori. Per valori più grandi, i vettori vengono disegnati con minore precisione ma più velocemente. Il valore predefinito è 5. |

La [!DNL Boundaries.layer] file formattato come segue:

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
