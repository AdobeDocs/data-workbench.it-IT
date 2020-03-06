---
description: Nel workbench data, uno strato immagine del terreno mostra le immagini del terreno della Terra.
solution: Analytics
title: Utilizzo dei livelli immagine terreno
topic: Data workbench
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
translation-type: tm+mt
source-git-commit: 948c6dd04819e939b45745db573a53c8be51ce37

---


# Utilizzo dei livelli immagine terreno{#working-with-terrain-image-layers}

Nel workbench data, uno strato immagine del terreno mostra le immagini del terreno della Terra.

I livelli immagine del terreno sono memorizzati nel [!DNL Geography] profilo, in un formato personalizzato. Questi livelli di immagine possono essere generati da Adobe, oppure il server workbench dati può trasformare le immagini del terreno fornite dall’utente in livelli del terreno adatti per l’utilizzo sulla visualizzazione globale.

>[!NOTE]
>
>Per utilizzare i livelli immagine del terreno, è necessario installare il [!DNL Terrain Images.cfg] file fornito da Adobe. Per le istruzioni di installazione, vedere [Installazione della geografia](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md)del workbench dati.

Per definire un livello di immagine del terreno, dovete disporre dei seguenti elementi:

* **Uno o più file** immagine del terreno contenenti le immagini da visualizzare sul globo.
* **Un file Terrain Images.cfg** che specifica i file immagine del terreno da utilizzare per i livelli. Il [!DNL Terrain Images.cfg] file consente di aggiungere una o più sorgenti per creare un livello immagine del terreno. Il formato del file immagine del terreno determina il tipo di origine da aggiungere. Nella tabella seguente sono descritte le origini disponibili per il livello dell’immagine del terreno, inclusi i formati supportati per i file immagine del terreno:

<table id="table_BF8D5933BFBE45039BD164C258D3B450"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> bitmap non proiettata non proiettata </td> 
   <td colname="col2"> <p>Crea livelli immagine del terreno da file RGB headerless a 24 bit allineati alla longitudine (non proiettati), dove nord è la parte superiore dell’immagine e est è la parte destra. </p> <p>Formati immagine supportati: RAW </p> <p> <p>Nota: Questa origine richiede informazioni sulla proiezione. Per informazioni sui formati di proiezione, vedere <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Specifica delle informazioni di proiezione per le immagini</a>terrestri. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Immagine generale, non proiettata </td> 
   <td colname="col2"> <p>Crea livelli immagine del terreno a partire dai formati immagine allineati (non proiettati) a 24 bit con longitudine e latitudine, dove nord è la parte superiore dell’immagine e est è la parte destra. </p> <p>Formati immagine supportati: BMP, JPG, PNG, TIFF </p> <p> <p>Nota: Questa origine richiede informazioni sulla proiezione. Per informazioni sui formati di proiezione, vedere <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Specifica delle informazioni di proiezione per le immagini</a>terrestri. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Immagine con proiezione incorporata </td> 
   <td colname="col2"> <p>Crea livelli immagine del terreno da formati immagine che incorporano dati geodetici nel file immagine. Le informazioni sulla proiezione vengono estratte dall’immagine. </p> <p>Formati immagine supportati: Erdas (IMG), GeoTIFF </p> <p> <p>Nota: Questa fonte in genere non richiede informazioni di proiezione ma supporta l'aggiunta di tali informazioni, se necessario. Per informazioni sui formati di proiezione, vedere <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Specifica delle informazioni di proiezione per le immagini</a>terrestri. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Per definire un livello immagine del terreno**

1. Nel workbench dati, nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39; [!DNL Servers Manager] area di lavoro.

1. All&#39;interno della [!DNL Servers Manager] finestra, fare clic con il pulsante destro del mouse sull&#39;icona del server workbench dati desiderato e fare clic **[!UICONTROL Server Files]**.

1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Components]** per visualizzarne il contenuto. Il [!DNL Terrain Images.cfg] file si trova all&#39;interno di questa directory.

1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Terrain Images.cfg], quindi scegliere **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Terrain Images.cfg.]

1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata la [!DNL Terrain Images.cfg]finestra.

1. Nella [!DNL Terrain Images] finestra, fate clic **[!UICONTROL component]** per visualizzarne il contenuto.

1. Fate clic con il pulsante destro del mouse **[!UICONTROL Sources]** > **[!UICONTROL Add new]** e scegliete uno dei seguenti tipi di sorgente:

   * **[!UICONTROL Raw unprojected bitmap]** (Progetto > scarica CSV). (Una volta aggiunto, questo tipo di origine è etichettato RawTerrainSource nella [!DNL Terrain Images] finestra.)

   * **[!UICONTROL General image, unprojected]** (Progetto > scarica CSV). Una volta aggiunto, questo tipo di origine è etichettato GDALTerrainSource nella [!DNL Terrain Images] finestra.

   * **[!UICONTROL Image with embedded projection]** (Progetto > scarica CSV). Una volta aggiunto, questo tipo di origine è etichettato GDALTerrainSource nella [!DNL Terrain Images] finestra.

1. Modificate i parametri per l&#39;origine come necessario utilizzando il file di esempio e la tabella di parametri come guide.

   ![](assets/cfg_TerrainImages_ALL.png)

<table id="table_83171CB58F8B4816BCCA9BFFD5ECD92A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Gamma </td> 
   <td colname="col2"> Facoltativo per tutte le origini. Specifica la correzione gamma da applicare all'immagine sorgente. Questo può essere auspicabile perché il workbench dati normalmente funziona con un'impostazione gamma elevata. Il valore predefinito è 1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Altezza </td> 
   <td colname="col2"> Obbligatorio per immagini bitmap non proiettate. L’altezza dell’immagine sorgente in pixel. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni sulla proiezione </td> 
   <td colname="col2"> <p>Richiesto per immagini bitmap non proiettate e immagini generali, non proiettate, ma supportato per immagini con proiezione incorporata. Il workbench<span class="wintitle"> dati Geography</span> supporta proiezioni di latitudine e di Mercatore trasversale (TM) per i livelli di immagine del terreno. Il formato di proiezione predefinito è la proiezione latitudine-longitudine (LatLonProjection). </p> <p>Per informazioni sui formati di proiezione, vedere <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Specifica delle informazioni di proiezione per le immagini</a>terrestri. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Immagine sorgente </td> 
   <td colname="col2">Obbligatorio per tutte le origini. Il nome del file di immagine di origine. Può trattarsi di un nome di file o di un pattern con caratteri jolly. L'utilizzo di un pattern può essere utile se, ad esempio, vengono caricate immagini per la stessa area in date diverse, senza alcuna modifica nei metadati associati. Pertanto, un pattern come "<span class="filepath"> Tysons Corner *.raw</span>" creerebbe livelli da <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span>e così via, quando vengono aggiunte nuove immagini, senza bisogno di ulteriori configurazioni se i parametri per i file sono altrimenti identici. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Qualità compressione sezione </td> 
   <td colname="col2"> <p>Facoltativo per tutte le origini. Per la compressione JPEG, un numero intero compreso tra 0 e 100 che specifica come bilanciare le dimensioni e la qualità dell’immagine. Il valore predefinito è zero. Un numero più elevato garantisce una migliore qualità delle immagini, ma produce immagini più grandi e tempi di download più lunghi per gli utenti del workbench dati. </p> <p>Comprimendo le immagini al di sotto di 70 si potrebbe verificare un degrado delle immagini. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compressore di sezione </td> 
   <td colname="col2"> Facoltativo per tutte le origini. Specifica quale metodo di compressione viene utilizzato per scrivere i file di output. Gli unici metodi attualmente supportati sono RAWRGB (il valore predefinito, che non comporta alcuna compressione) e JPEG. Utilizzate la compressione JPEG per ridurre le dimensioni dei livelli trasmessi durante la sincronizzazione del profilo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Larghezza </td> 
   <td colname="col2"> Obbligatorio per immagini bitmap non proiettate. Larghezza dell’immagine sorgente in pixel. </td> 
  </tr> 
 </tbody> 
</table>

1. Modificate i parametri Posizione immagine sorgente, Memorizzazione immagini temporanea e Scrivi livelli in utilizzando la tabella seguente come guida. Questi parametri si applicano a tutte le origini immagine del terreno definite nella sezione Origini di questo file.

   | Parametro | Descrizione |
   |---|---|
   | Posizione immagine di origine | Obbligatorio. Directory analizzata per le immagini da tradurre in livelli di terreno. Se non si tratta di un percorso assoluto, viene interpretato rispetto alla directory di installazione del server workbench dati. |
   | Archiviazione immagini temporanea | Facoltativo. Nome di una directory utilizzata per l’archiviazione dei file temporanei utilizzati nella traduzione delle immagini sorgente in livelli di terreno. Se non si tratta di un percorso assoluto, viene interpretato rispetto alla directory di installazione del server workbench dati. Il percorso predefinito è la directory Temp. |
   | Scrivi livelli in | Obbligatorio. La directory in cui vengono inviati i livelli del terreno. Di norma, si tratta della sottodirectory Maps di una directory di profilo, in modo che la [!DNL Globe] visualizzazione possa individuare i livelli. |

1. Salvare il file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**.

1. Per salvare il file aggiornato nel computer server workbench dati, fare clic con il pulsante destro del mouse sul segno di spunta [!DNL Server Files Manager]nella [!DNL Terrain Images.cfg] colonna, quindi fare clic [!DNL Temp] > **[!UICONTROL Save to]** &lt; *>**[!UICONTROL server name]***.

