---
description: Potete creare un livello vettoriale che faccia riferimento a uno o più file vettoriali (.vec), contenenti i dati che definiscono i vettori da disegnare nel mondo.
solution: Analytics
title: Definizione di livelli vettoriali con riferimento a file vettoriali
topic: Data workbench
uuid: 162d4ecc-d305-42e3-a5d4-0c1609a40f29
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definizione di livelli vettoriali con riferimento a file vettoriali{#defining-vector-layers-referencing-vector-files}

Potete creare un livello vettoriale che faccia riferimento a uno o più file vettoriali (.vec), contenenti i dati che definiscono i vettori da disegnare nel mondo.

Per definire un livello vettoriale che faccia riferimento a uno o più [!DNL .vec]file, è necessario disporre dei seguenti elementi:

* Uno o più [!DNL .vec]file contenenti i dati utilizzati per disegnare i vettori sul globo.

   >[!NOTE]
   >
   >Per ottenere [!DNL .vec] i file da usare con i livelli vettoriali, contattate Adobe.

* Un file di livello che specifica la posizione dei [!DNL .vec] file. Per ulteriori informazioni sul formato richiesto del file di livello, consultate Formato [file livello](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-def-vctr-files.md#section-530d03f41ede4a339aebbb680e15240a)vettoriale.

   >[!NOTE]
   >
   >Il [!DNL Boundaries.layer] file, fornito con il [!DNL Geography] profilo, è un livello vettoriale che fa riferimento ai file [!DNL mwnation.vec], [!DNL mwstate.vec], [!DNL mwcoast.vec], [!DNL mwlake.vec]e [!DNL mwisland.vec] .

## Formato file livello vettoriale {#section-530d03f41ede4a339aebbb680e15240a}

Ciascun file vettoriale che fa riferimento a [!DNL .vec]file deve essere formattato utilizzando il seguente modello:

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
| File Vec | Percorso o percorsi dei [!DNL .vec] file contenenti i dati vettoriali. |
| Colore | Il vettore del colore RGB, espresso come (rosso, verde, blu). Per ogni colore del vettore, potete immettere un valore compreso tra 0,0 e 1,0. Ad esempio, (1.0, 0.0, 0.0) è rosso chiaro e (0.5, 0.5, 0.5) è grigio. |
| Alfa | Controlla la trasparenza dei vettori mostrati sul globo. L&#39;intervallo è compreso tra 0 e 1, con 0 come il più trasparente. |
| Larghezza | Facoltativo. Imposta la larghezza dei dati in pixel. L&#39;intervallo consigliato è compreso tra 1 e 4. |
| Fattore errore | Controlla la precisione con cui i vettori vengono disegnati. Per valori più grandi, i vettori vengono disegnati meno accuratamente ma più velocemente. Il valore predefinito è 5. |

Il [!DNL Boundaries.layer] file è formattato come segue:

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

