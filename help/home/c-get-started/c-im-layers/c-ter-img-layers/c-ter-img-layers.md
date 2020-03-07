---
description: Uno strato immagine del terreno mostra le immagini del terreno della Terra.
solution: Analytics
title: Livelli immagine del terreno
topic: Data workbench
uuid: 17968293-1ad2-4040-a174-d33f418af9b7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Livelli immagine del terreno{#terrain-image-layers}

Uno strato immagine del terreno mostra le immagini del terreno della Terra.

[!DNL Terrain image layers] sono memorizzati nel [!DNL Geography] profilo in un formato personalizzato. Questi livelli di immagine possono essere generati da Adobe, oppure il server Workbench dati può trasformare le immagini del terreno fornite dall’utente in livelli del terreno adatti per l’utilizzo sulla visualizzazione a livello globale.

>[!NOTE]
>
>Per lavorare con [!DNL terrain image layers], è necessario installare il [!DNL Terrain Images.cfg] file fornito da Adobe.

Per definire un livello di immagine del terreno, dovete disporre dei seguenti elementi:

* **Uno o più file** immagine del terreno contenenti le immagini da visualizzare sul globo.
* **Un[!DNL Terrain Images.cfg]file** che specifica i file immagine del terreno da usare per i livelli. Il [!DNL Terrain Images.cfg] file consente di aggiungere una o più origini per creare una [!DNL terrain image layer]. Il formato del file immagine del terreno determina il tipo di origine da aggiungere. Nella tabella seguente sono descritte le origini disponibili per il livello dell’immagine del terreno, inclusi i formati supportati per i file immagine del terreno:

<table id="table_CFDF5E61FCCD40B29A9D35FFA42F68D1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>bitmap non proiettata non proiettata </p> </td> 
   <td colname="col2"> <p>Crea livelli <span class="wintitle"> di immagine del</span> terreno da file RGB headerless a 24 bit allineati con latitudine e longitudine (non proiettati), dove nord è la parte superiore dell’immagine e est è la parte destra. </p> <p>Formati immagine supportati: RAW </p> <p> <p>Nota: Questa origine richiede informazioni sulla proiezione. Per informazioni sui formati di proiezione, vedere <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Specifica delle informazioni di proiezione per le immagini</a>terrestri. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Immagine generale, non proiettata </p> </td> 
   <td colname="col2"> <p>Crea livelli <span class="wintitle"> di immagine del</span> terreno a partire dai formati immagine allineati a 24 bit con latitudine e longitudine (non proiettati), dove nord è la parte superiore dell’immagine e est è la parte destra. </p> <p>Formati immagine supportati: BMP, JPG, PNG, TIFF </p> <p> <p>Nota: Questa origine richiede informazioni sulla proiezione. Per informazioni sui formati di proiezione, vedere <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Specifica delle informazioni di proiezione per le immagini</a>terrestri. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Immagine con proiezione incorporata </p> </td> 
   <td colname="col2"> <p>Consente di creare livelli <span class="wintitle"></span> di immagine del terreno dai formati immagine che incorporano dati geodetici nel file immagine. Le informazioni sulla proiezione vengono estratte dall’immagine. </p> <p>Formati immagine supportati: Erdas (IMG), GeoTIFF </p> <p> <p>Nota: Questa fonte in genere non richiede informazioni di proiezione ma supporta l'aggiunta di tali informazioni, se necessario. Per informazioni sui formati di proiezione, vedere <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Specifica delle informazioni di proiezione per le immagini</a>terrestri. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Per definire un livello immagine del terreno**

1. In Workbench dati, nella scheda **[!UICONTROL Admin]** > **[!UICONTROL Dataset and Profile]** , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39; [!DNL Servers Manager] area di lavoro.
1. Nella [!DNL Servers Manager] finestra fare clic con il pulsante destro del mouse sull&#39;icona del server Workbench dati desiderato e fare clic su **[!UICONTROL Server Files]**.
1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Terrain Images.cfg] file si trova all&#39;interno di questa directory.
1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Terrain Images.cfg], quindi scegliere **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Terrain Images.cfg].
1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella **[!UICONTROL Temp]** colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene [!DNL Terrain Images.cfg] visualizzata la finestra.
1. Nella [!DNL Terrain Images] finestra, fate clic **[!UICONTROL component]** per visualizzarne il contenuto.
1. Fate clic con il pulsante destro del mouse **[!UICONTROL Sources]** > **[!UICONTROL Add new]** e scegliete uno dei seguenti tipi di sorgente:

   * **[!UICONTROL Raw unprojected bitmap]** (Progetto > scarica CSV). (Una volta aggiunto, questo tipo di origine è etichettato RawTerrainSource nella [!DNL Terrain Images] finestra.)

   * **[!UICONTROL General image, unprojected]** (Progetto > scarica CSV). (Una volta aggiunto, questo tipo di origine è etichettato [!DNL GDALTerrainSource] nella [!DNL Terrain Images] finestra.)

   * **[!UICONTROL Image with embedded projection]** (Progetto > scarica CSV). (Una volta aggiunto, questo tipo di origine è etichettato [!DNL GDALTerrainSource] nella [!DNL Terrain Images] finestra.)

1. Modificate i parametri per l&#39;origine come necessario utilizzando il file di esempio e la tabella di parametri come guide.

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_345ACB4C48524516AADB731D87FC6792"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gamma </p> </td> 
   <td colname="col2"> <p>Facoltativo per tutte le origini. Specifica la correzione gamma da applicare all'immagine sorgente. Ciò può essere auspicabile in quanto Workbench dati funziona normalmente con un'impostazione gamma elevata. Il valore predefinito è 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Altezza </p> </td> 
   <td colname="col2"> <p>Obbligatorio per immagini bitmap non proiettate. L’altezza dell’immagine sorgente in pixel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Informazioni sulla proiezione </p> </td> 
   <td colname="col2"> <p>Richiesto per immagini bitmap non proiettate e immagini generali, non proiettate, ma supportato per immagini con proiezione incorporata. Workbench dati supporta proiezioni di longitudine latitudine e proiezioni di Mercatore trasversale (TM) per i livelli immagine del terreno. Il formato di proiezione predefinito è la proiezione latitudine-longitudine (LatLonProjection). </p> <p>Per informazioni sui formati di proiezione, vedere <a href="../../../../home/c-get-started/c-im-layers/c-ter-img-layers/c-proj-info-ter-imgs.md#concept-eec35baa01744895b847a02e69dad04e"> Specifica delle informazioni di proiezione per le immagini</a>terrestri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Immagine sorgente </p> </td> 
   <td colname="col2"> <p>Obbligatorio per tutte le origini. Il nome del file di immagine di origine. Può trattarsi di un nome di file o di un pattern con caratteri jolly. L'utilizzo di un pattern può essere utile se, ad esempio, vengono caricate immagini per la stessa area in date diverse, senza alcuna modifica nei metadati associati. Pertanto, un pattern come <span class="filepath"> Tysons Corner *.raw</span> creerebbe livelli da <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>e così via, quando vengono aggiunte nuove immagini, senza alcuna configurazione aggiuntiva necessaria se i parametri per i file sono altrimenti identici. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Qualità compressione sezione </p> </td> 
   <td colname="col2"> <p>Facoltativo per tutte le origini. Per la compressione JPEG, un numero intero compreso tra 0 e 100 che specifica come bilanciare le dimensioni e la qualità dell’immagine. Il valore predefinito è zero. Un numero più elevato garantisce una migliore qualità delle immagini, ma produce immagini più grandi e tempi di download più lunghi per gli utenti di Workbench dati. </p> <p> <p>Nota:  Comprimendo le immagini al di sotto di 70 si potrebbe verificare un degrado delle immagini. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Compressore di sezione </p> </td> 
   <td colname="col2"> <p>Facoltativo per tutte le origini. Specifica quale metodo di compressione viene utilizzato per scrivere i file di output. Gli unici metodi attualmente supportati sono RAWRGB (il valore predefinito, che non comporta alcuna compressione) e JPEG. Utilizzate la compressione JPEG per ridurre le dimensioni dei livelli trasmessi durante la sincronizzazione del profilo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Larghezza </p> </td> 
   <td colname="col2"> <p>Obbligatorio per immagini bitmap non proiettate. Larghezza dell’immagine sorgente in pixel. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Modificate i parametri Posizione immagine sorgente, Memorizzazione immagini temporanea e Scrivi livelli in utilizzando la tabella seguente come guida. Questi parametri si applicano a tutte le origini immagine del terreno definite nella [!DNL Sources] sezione del file.

<table id="table_103F02C54ED94C6C922450F5B2781CAE"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Posizione immagine di origine </p> </td> 
   <td colname="col2"> <p>Obbligatorio. Directory analizzata per le immagini da tradurre in livelli di terreno. Se non si tratta di un percorso assoluto, viene interpretato rispetto alla directory di installazione del server Workbench dati. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Archiviazione immagini temporanea </p> </td> 
   <td colname="col2"> <p>Facoltativo. Nome di una directory utilizzata per l’archiviazione dei file temporanei utilizzati nella traduzione delle immagini sorgente in livelli di terreno. Se non si tratta di un percorso assoluto, viene interpretato rispetto alla directory di installazione del server Workbench dati. Il percorso predefinito è la directory <span class="wintitle"> Temp</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Scrivi livelli in </p> </td> 
   <td colname="col2"> <p>Obbligatorio. La directory in cui vengono inviati i livelli del terreno. Di norma, questa è la sottodirectory Maps di una directory di profilo, in modo che la visualizzazione Globe possa trovare i livelli. </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Salvare il file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**.
1. Per salvare un file aggiornato nel computer del server Workbench dati, fare clic con il pulsante destro del mouse sul segno di spunta [!DNL Server Files Manager]nella [!DNL Terrain Images.cfg] colonna, quindi fare clic [!DNL Temp] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

