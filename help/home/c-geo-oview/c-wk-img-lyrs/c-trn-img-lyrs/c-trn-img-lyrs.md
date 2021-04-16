---
description: All’interno di Data Workbench, un livello immagine del terreno mostra le immagini del terreno sulla Terra.
title: Utilizzo dei livelli immagine del terreno
uuid: 2f23a2c8-f551-4b84-bd87-5d7053910ab3
exl-id: 22026b41-4e12-4247-b019-461ae223bd07
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1021'
ht-degree: 2%

---

# Utilizzo dei livelli immagine del terreno{#working-with-terrain-image-layers}

All’interno di Data Workbench, un livello immagine del terreno mostra le immagini del terreno sulla Terra.

I livelli immagine del terreno sono memorizzati nel profilo [!DNL Geography], in un formato personalizzato. Questi livelli immagine possono essere generati da Adobe, oppure il server di Data Workbench può trasformare le immagini del terreno fornite dall’utente in livelli del terreno adatti all’utilizzo sulla visualizzazione del globo.

>[!NOTE]
>
>Per lavorare con i livelli immagine del terreno, è necessario installare il file [!DNL Terrain Images.cfg] fornito da Adobe. Per le istruzioni di installazione, vedere [Installazione della geografia di Data Workbench](../../../../home/c-geo-oview/c-inst-geo/c-inst-geo.md).

Per definire un livello immagine del terreno, è necessario disporre dei seguenti elementi:

* **Uno o più** file immagine del terreno contenenti le immagini da visualizzare sul globo.
* **Un file Terrain Images.** cfgfile che specifica i file immagine del terreno da utilizzare per i livelli. Il file [!DNL Terrain Images.cfg] consente di aggiungere una o più sorgenti per creare un livello immagine del terreno. Il formato del file immagine del terreno determina il tipo di origine da aggiungere. La tabella seguente fornisce una descrizione delle origini del livello immagine del terreno disponibili, inclusi i formati di file immagine del terreno supportati:

<table id="table_BF8D5933BFBE45039BD164C258D3B450"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> bitmap non proiettata </td> 
   <td colname="col2"> <p>Crea livelli immagine del terreno da file RGB headerless a 24 bit allineati a latitudine-longitudine (non proiettati), dove nord è la parte superiore dell'immagine e est è la destra. </p> <p>Formati immagine supportati: RAZZA </p> <p> <p>Nota: Questa sorgente richiede informazioni di proiezione. Per informazioni sui formati di proiezione, vedere <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Specifica delle informazioni di proiezione per le immagini del terreno</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Immagine generale, non proiettata </td> 
   <td colname="col2"> <p>Crea livelli immagine del terreno da formati immagine allineati a latitudine e longitudine (non proiettati) a 24 bit, dove nord è la parte superiore dell'immagine e est è la destra. </p> <p>Formati immagine supportati: BMP, JPG, PNG, TIFF </p> <p> <p>Nota: Questa sorgente richiede informazioni di proiezione. Per informazioni sui formati di proiezione, vedere <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Specifica delle informazioni di proiezione per le immagini del terreno</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Immagine con proiezione incorporata </td> 
   <td colname="col2"> <p>Crea livelli immagine del terreno da formati immagine che incorporano dati geodetici nel file immagine. Le informazioni di proiezione vengono estratte dall'immagine. </p> <p>Formati immagine supportati: Erdas (IMG), GeoTIFF </p> <p> <p>Nota: Questa fonte di solito non richiede informazioni di proiezione, ma supporta l'aggiunta di tali informazioni, se necessario. Per informazioni sui formati di proiezione, vedere <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Specifica delle informazioni di proiezione per le immagini del terreno</a>. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Per definire un livello immagine del terreno**

1. All’interno di Data Workbench, nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fai clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l’area di lavoro [!DNL Servers Manager].

1. Nella finestra [!DNL Servers Manager], fai clic con il pulsante destro del mouse sull’icona del server di Data Workbench desiderato e fai clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Components]** per visualizzarne il contenuto. Il file [!DNL Terrain Images.cfg] si trova all&#39;interno di questa directory.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome del server per [!DNL Terrain Images.cfg], quindi fai clic su **[!UICONTROL Make Local]**. Un segno di spunta compare nella colonna [!DNL Temp] per [!DNL Terrain Images.cfg.]

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata la finestra [!DNL Terrain Images.cfg].

1. Nella finestra [!DNL Terrain Images] fare clic su **[!UICONTROL component]** per visualizzarne il contenuto.

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Sources]** > **[!UICONTROL Add new]** e scegli uno dei seguenti tipi di origine:

   * **[!UICONTROL Raw unprojected bitmap]**. (Una volta aggiunto, questo tipo di origine è etichettato RawTerrainSource nella finestra [!DNL Terrain Images] .)

   * **[!UICONTROL General image, unprojected]**. (Una volta aggiunto, questo tipo di origine viene etichettato GDALTerrainSource nella finestra [!DNL Terrain Images].)

   * **[!UICONTROL Image with embedded projection]**. (Una volta aggiunto, questo tipo di origine viene etichettato GDALTerrainSource nella finestra [!DNL Terrain Images].)

1. Modifica i parametri della sorgente in base alle necessità utilizzando il file di esempio seguente e la tabella dei parametri come guide.

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
   <td colname="col2"> Facoltativo per tutte le sorgenti. Specifica la correzione del gamma da applicare all'immagine sorgente. Ciò può essere auspicabile in quanto Data Workbench funziona normalmente con un’impostazione gamma elevata. Il valore predefinito è 1. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Altezza </td> 
   <td colname="col2"> Richiesto per immagini bitmap non proiettate. Altezza dell'immagine sorgente in pixel. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Informazioni sulla proiezione </td> 
   <td colname="col2"> <p>Richiesto per immagini bitmap non proiettate e immagini generali, non proiettate, ma supportato per immagini con proiezione incorporata. Data Workbench<span class="wintitle"> Geografia</span> supporta le proiezioni di latitudine e longitudine e le proiezioni di Mercatore trasversale (TM) per i livelli immagine del terreno. Il formato di proiezione predefinito è la proiezione latitudine-longitudine (LatLonProjection). </p> <p>Per informazioni sui formati di proiezione, vedere <a href="../../../../home/c-geo-oview/c-wk-img-lyrs/c-trn-img-lyrs/c-proj-info-trn-imgs/c-proj-info-trn-imgs.md#concept-69b0c668038f4de9bf430a3a468a2abd"> Specifica delle informazioni di proiezione per le immagini del terreno</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Immagine sorgente </td> 
   <td colname="col2">Obbligatorio per tutte le sorgenti. Nome del file immagine di origine. Può trattarsi di un nome file o di un pattern con caratteri jolly. L’utilizzo di un pattern può essere utile se, ad esempio, vengono caricate immagini per la stessa area in date diverse, senza alcuna modifica nei metadati associati. Pertanto, un pattern come "<span class="filepath"> Tysons Corner *.raw</span>" creerebbe livelli da <span class="filepath"> Tysons Corner 050211.raw</span>, <span class="filepath"> Tysons Corner 050218.raw</span> e così via, quando vengono aggiunte nuove immagini, senza configurazioni aggiuntive necessarie se i parametri in caso contrario, i file sono identici. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Qualità della compressione delle porzioni </td> 
   <td colname="col2"> <p>Facoltativo per tutte le sorgenti. Per la compressione JPEG, un numero intero compreso tra 0 e 100 che specifica come bilanciare la dimensione e la qualità dell'immagine. Il valore predefinito è zero. Un numero più elevato garantisce una migliore qualità delle immagini, ma genera immagini più grandi e tempi di download più lunghi per gli utenti di Data Workbench. </p> <p>La compressione delle immagini al di sotto di 70 può causare la degradazione dell'immagine. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Compressore a piastrelle </td> 
   <td colname="col2"> Facoltativo per tutte le sorgenti. Specifica il metodo di compressione utilizzato per scrivere i file di output. Gli unici metodi attualmente supportati sono RAWRGB (il valore predefinito, senza compressione) e JPEG. Utilizza la compressione JPEG per ridurre le dimensioni dei livelli trasmessi durante la sincronizzazione del profilo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Larghezza </td> 
   <td colname="col2"> Richiesto per immagini bitmap non proiettate. Larghezza dell'immagine sorgente in pixel. </td> 
  </tr> 
 </tbody> 
</table>

1. Modifica i parametri Posizione immagine sorgente, Archiviazione immagini temporanea e Scrivi livelli in utilizzando la seguente tabella come guida. Questi parametri si applicano a tutte le sorgenti immagine del terreno definite nella sezione Origini di questo file.

   | Parametro | Descrizione |
   |---|---|
   | Posizione immagine sorgente | Obbligatorio. Directory analizzata per le immagini da tradurre in livelli del terreno. Se non si tratta di un percorso assoluto, viene interpretato rispetto alla directory di installazione del server di Data Workbench. |
   | Archiviazione immagine temporanea | Facoltativo. Il nome di una directory utilizzata per l&#39;archiviazione dei file temporanei utilizzati nella traduzione delle immagini sorgente in livelli del terreno. Se non si tratta di un percorso assoluto, viene interpretato rispetto alla directory di installazione del server di Data Workbench. Il percorso predefinito è la directory Temp. |
   | Scrivi livelli in | Obbligatorio. La directory in cui vengono emessi i livelli del terreno. In genere, si tratta della sottodirectory Maps di una directory di profilo, in modo che la visualizzazione [!DNL Globe] possa individuare i livelli. |

1. Salva il file facendo clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e facendo clic su **[!UICONTROL Save]**.

1. Per salvare il file aggiornato nel computer server di Data Workbench, fai clic con il pulsante destro del mouse sul segno di spunta [!DNL Terrain Images.cfg] nella colonna [!DNL Temp], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]***.[!DNL Server Files Manager]
