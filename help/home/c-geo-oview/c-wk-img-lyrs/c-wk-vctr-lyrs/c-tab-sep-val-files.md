---
description: Quando si crea un livello vettoriale che fa riferimento a un file di valori separati da tabulazioni (.tsv), i dati vettoriali vengono ottenuti recuperando le istruzioni di disegno, nonché i dati di longitudine e latitudine dal file .tsv .
title: Livelli vettoriali che fanno riferimento a file di valori separati da tabulazioni
uuid: 42607b34-e9f2-420a-ba5a-05562598b480
exl-id: be16ba73-4a98-472b-98f1-1b32e671b763
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 6%

---

# Livelli vettoriali che fanno riferimento a file di valori separati da tabulazioni{#vector-layers-referencing-tab-separated-values-files}

{{eol}}

Quando si crea un livello vettoriale che fa riferimento a un file di valori separati da tabulazioni (.tsv), i dati vettoriali vengono ottenuti recuperando le istruzioni di disegno, nonché i dati di longitudine e latitudine dal file .tsv .

Per definire un livello vettoriale che fa riferimento a un [!DNL .tsv] file, devi disporre dei seguenti elementi:

* **A [!DNL .tsv] file** che contiene i dati utilizzati per disegnare i vettori sul globo, compresi i dati di longitudine e latitudine. Per ulteriori informazioni sul formato richiesto del [!DNL .tsv] file, vedi [Formato file TSV vettoriale](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-a29012c9ff4444ac8a6d41c68482828e).

* **Un file di livello** specifica la posizione della [!DNL .tsv] file. Per ulteriori informazioni sul formato richiesto del file di livello, vedi [Formato file livello vettoriale](../../../../home/c-geo-oview/c-wk-img-lyrs/c-wk-vctr-lyrs/c-tab-sep-val-files.md#section-c430923f341f4c93852e9f24b61e82bf).

## Formato file TSV vettoriale {#section-a29012c9ff4444ac8a6d41c68482828e}

La [!DNL .tsv] il file deve contenere le tre colonne separate da tabulazioni seguenti:

* **[!DNL Begin]:** Questa colonna deve indicare se iniziare una nuova riga. I valori in questa colonna possono essere 0 (non iniziare una nuova riga) o 1 (iniziare una nuova riga).
* **[!DNL Longitude]:** Questa colonna deve contenere valori di longitudine.
* **[!DNL Latitude]:** Questa colonna deve contenere valori di latitudine.

>[!NOTE]
>
>Tutte le colonne aggiuntive vengono ignorate.

Di seguito è riportato un esempio [!DNL .tsv] file che contiene dati per un livello vettoriale:

![](assets/tsv_vectorlayer.png)

## Formato del file del livello vettoriale {#section-c430923f341f4c93852e9f24b61e82bf}

Ciascun file vettoriale che fa riferimento a [!DNL .tsv] i file devono essere formattati utilizzando il seguente modello:

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
   <td colname="col2"> <p>Percorso/i verso il <span class="filepath"> .tsv</span> file contenenti i dati vettoriali. </p> <p>Esempio: <span class="filepath"> Mappe\\USVectorData.tsv</span> </p> </td> 
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
