---
description: Quando si crea un livello vettoriale che fa riferimento a un file di valori separati da tabulazioni (.tsv), i dati vettoriali vengono ottenuti recuperando le istruzioni di disegno, nonché i dati di longitudine e latitudine dal file .tsv .
title: Livelli vettoriali che fanno riferimento a file di valori separati da tabulazioni
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
exl-id: be16ba73-4a98-472b-98f1-1b32e671b763,7b0b0286-072b-4b31-b6ec-ced322da5236
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 6%

---

# Livelli vettoriali che fanno riferimento a file di valori separati da tabulazioni{#vector-layers-referencing-tab-separated-values-files}

Quando si crea un livello vettoriale che fa riferimento a un file di valori separati da tabulazioni (.tsv), i dati vettoriali vengono ottenuti recuperando le istruzioni di disegno, nonché i dati di longitudine e latitudine dal file .tsv .

Per definire un livello vettoriale che fa riferimento a un file [!DNL .tsv], è necessario disporre dei seguenti elementi:

* **File  [!DNL .tsv]** contenente i dati utilizzati per disegnare i vettori sul globo, inclusi i dati di longitudine e latitudine. Per ulteriori informazioni sul formato richiesto del file [!DNL .tsv], consulta [Formato file Vector TSV](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e).

* **File di livello** che specifica la posizione del  [!DNL .tsv] file. Per ulteriori informazioni sul formato richiesto del file di livello, vedere [Formato del file di livello vettoriale](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf).

## Formato del file Vector TSV {#section-a29012c9ff4444ac8a6d41c68482828e}

Il file [!DNL .tsv] deve contenere le seguenti tre colonne separate da tabulazioni:

* **[!DNL Begin]:** Questa colonna deve indicare se iniziare una nuova riga. I valori in questa colonna possono essere 0 (non iniziare una nuova riga) o 1 (iniziare una nuova riga).
* **[!DNL Longitude]:** Questa colonna deve contenere valori di longitudine.
* **[!DNL Latitude]:** Questa colonna deve contenere valori di latitudine.

>[!NOTE]
>
>Tutte le colonne aggiuntive vengono ignorate.

Di seguito è riportato un file di esempio [!DNL .tsv] contenente dati per un livello vettoriale:

![](assets/tsv_vectorlayer.png)

## Formato del file del livello vettoriale {#section-c430923f341f4c93852e9f24b61e82bf}

Ogni file di livello vettoriale che fa riferimento a file [!DNL .tsv] deve essere formattato utilizzando il seguente modello:

```
Layer = VectorLayer:
  TSV Files = vector: n items
    0 = string: Maps\\File Name.tsv
    1 = string: Maps\\File Name.tsv
    . . .
    n-1 = string: Maps\\File Name.tsv
  Color = v3d: color vector
  Alpha = double: alpha
  Width = double: width
  Error Factor = double: error factor
```

<table id="table_152F73536AB9403AB43854B81D6A9A15"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> File TSV </td> 
   <td colname="col2"> <p>Percorso/i del file <span class="filepath"> .tsv</span> contenente i dati vettoriali. </p> <p>Esempio: <span class="filepath"> Mappe\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colore </td> 
   <td colname="col2"> Il vettore del colore RGB, espresso come (rosso, verde, blu). Per ogni colore del vettore, è possibile immettere un valore compreso tra 0,0 e 1,0. Ad esempio, (1.0, 0.0, 0.0) è rosso chiaro e (0,5, 0,5, 0,5) è grigio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alfa </td> 
   <td colname="col2"> Controlla la trasparenza dei vettori mostrati sul globo. L'intervallo è compreso tra 0 e 1, mentre 0 è il più trasparente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Larghezza </td> 
   <td colname="col2"> Facoltativo. Imposta la larghezza dei dati in pixel. L'intervallo consigliato è da 1 a 4. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fattore errore </td> 
   <td colname="col2"> Controlla la precisione con cui vengono disegnati i vettori. Per valori più grandi, i vettori vengono disegnati con minore precisione ma più velocemente. Il valore predefinito è 5. </td> 
  </tr> 
 </tbody> 
</table>
