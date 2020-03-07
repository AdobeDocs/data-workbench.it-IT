---
description: Quando si crea un livello vettoriale che fa riferimento a un file con valori separati da tabulazioni (.tsv), i dati vettoriali vengono ottenuti recuperando le istruzioni di disegno, nonché i dati relativi a longitudine e latitudine dal file .tsv.
solution: Analytics
title: Livelli vettoriali che fanno riferimento a file di valori separati da tabulazioni
topic: Data workbench
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Livelli vettoriali che fanno riferimento a file di valori separati da tabulazioni{#vector-layers-referencing-tab-separated-values-files}

Quando si crea un livello vettoriale che fa riferimento a un file con valori separati da tabulazioni (.tsv), i dati vettoriali vengono ottenuti recuperando le istruzioni di disegno, nonché i dati relativi a longitudine e latitudine dal file .tsv.

Per definire un livello vettoriale che faccia riferimento a un [!DNL .tsv] file, dovete disporre dei seguenti elementi:

* **Un[!DNL .tsv]file** che contiene i dati utilizzati per disegnare i vettori sul globo, inclusi i dati di longitudine e latitudine. Per ulteriori informazioni sul formato richiesto del [!DNL .tsv] file, vedere [Formato](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e)file Vector TSV.

* **Un file** di livello che specifica la posizione del [!DNL .tsv] file. Per ulteriori informazioni sul formato richiesto del file di livello, consultate Formato [file livello](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf)vettoriale.

## Formato file Vector TSV {#section-a29012c9ff4444ac8a6d41c68482828e}

Il [!DNL .tsv] file deve contenere le seguenti tre colonne separate da tabulazioni:

* **[!DNL Begin]:**Questa colonna deve indicare se iniziare una nuova riga. I valori in questa colonna possono essere 0 (non iniziare una nuova riga) o 1 (iniziare una nuova riga).
* **[!DNL Longitude]:**Questa colonna deve contenere valori di longitudine.
* **[!DNL Latitude]:**Questa colonna deve contenere valori di latitudine.

>[!NOTE]
>
>Eventuali colonne aggiuntive vengono ignorate.

Segue un file di esempio [!DNL .tsv] che contiene i dati per un livello vettoriale:

![](assets/tsv_vectorlayer.png)

## Formato file vettoriale {#section-c430923f341f4c93852e9f24b61e82bf}

Ciascun file vettoriale che fa riferimento a [!DNL .tsv] file deve essere formattato utilizzando il seguente modello:

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
   <td colname="col2"> <p>Percorso dei file <span class="filepath"> .tsv</span> contenenti i dati vettoriali. </p> <p>Esempio: <span class="filepath"> Mappe\\USVectorData.tsv</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Colore </td> 
   <td colname="col2"> Il vettore del colore RGB, espresso come (rosso, verde, blu). Per ogni colore del vettore, potete immettere un valore compreso tra 0,0 e 1,0. Ad esempio, (1.0, 0.0, 0.0) è rosso chiaro e (0.5, 0.5, 0.5) è grigio. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Alfa </td> 
   <td colname="col2"> Controlla la trasparenza dei vettori mostrati sul globo. L'intervallo è compreso tra 0 e 1, con 0 come il più trasparente. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Larghezza </td> 
   <td colname="col2"> Facoltativo. Imposta la larghezza dei dati in pixel. L'intervallo consigliato è compreso tra 1 e 4. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Fattore errore </td> 
   <td colname="col2"> Controlla la precisione con cui i vettori vengono disegnati. Per valori più grandi, i vettori vengono disegnati meno accuratamente ma più velocemente. Il valore predefinito è 5. </td> 
  </tr> 
 </tbody> 
</table>

