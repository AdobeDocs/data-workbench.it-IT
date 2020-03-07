---
description: Gli esportatori forniscono le istruzioni per l’output dei dati dell’evento.
solution: Analytics
title: Definizione degli esportatori
topic: Data workbench
uuid: 565d4482-6c25-407c-bda7-0d116180902a
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Definizione degli esportatori{#defining-exporters}

Gli esportatori forniscono le istruzioni per l’output dei dati dell’evento.

La funzionalità di trasformazione fornisce tre tipi di esportatori per l&#39;esportazione di [!DNL .vsl] file, file di registro, file XML e dati ODBC come [!DNL .vsl] file, file di testo o file di testo delimitati che possono essere utilizzati dalle routine di caricamento di DataWarehouse, dalle agenzie di controllo o da altri target.

>[!NOTE]
>
>Affinché un esportatore possa funzionare correttamente, l&#39;origine di registro deve soddisfare i requisiti appropriati descritti nella sezione Origini [di](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea) registro del file [di configurazione dell&#39;elaborazione](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-abt-log-proc-config-file.md)log.

**Per definire un esportatore**

1. Aprire [!DNL Transform.cfg] in workbench dati. Vedere [Per modificare il file](../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13)Insight Transform.cfg.
1. Fare clic con il pulsante destro del mouse **[!UICONTROL Exporters]** e quindi scegliere **[!UICONTROL Add New]**.
1. Selezionate una delle seguenti opzioni:

   * **[!UICONTROL ExportTextFile]**
   * **[!UICONTROL ExportDelimitedTextFile]**
   * **[!UICONTROL ExportVSLFile]**
   >[!NOTE]
   >
   >Per l&#39; [!DNL ExportVSLFile] opzione, tutti i campi estesi nel file di input e tutti i campi definiti dall&#39;utente del modulo cs(*header*) sono sempre scritti nel file di output VSL. Se si sovrascrive un campo esteso esistente, il nuovo valore viene scritto nel file di output, anche se il campo è vuoto.

1. Modificate i parametri Exporter nel file di configurazione utilizzando la seguente tabella come guida:

   <table id="table_35C380DB6E4F42448C149D5EC185213C"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Parametro </th> 
      <th colname="col2" class="entry"> Descrizione </th> 
      </tr> 
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> Formato dati </td> 
      <td colname="col2"> <p>Solo per <span class="wintitle"> ExportTextFile</span> . Il formato di ciascuna riga di output, costituito da escape nome campo (espresso come %<i>fieldname</i>%) ed eventuale altro testo fisso desiderato. Il formato deve includere un separatore di riga, in genere [CR] [LF]. </p> <p> Un segno percentuale letterale (%) può essere incorporato nella stringa di formato, escape del carattere come mostrato di seguito: %% </p> <p> Un esempio di voce per il parametro Data Format è <span class="filepath"> %x-timestring% %x-trackingid%[CR][LF]</span>. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Campi </td> 
      <td colname="col2">Solo per <span class="wintitle"> ExportDelimitedTextFile</span> . Nomi dei campi da restituire. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Delimitatore </td> 
      <td colname="col2"> <p>Facoltativo. Solo per <span class="wintitle"> ExportDelimitedTextFile</span> . Carattere utilizzato per separare i campi nel file di output. </p> <p> Il software non può eseguire l'escape dei delimitatori inclusi nei valori dei dati. Di conseguenza, Adobe non consiglia di utilizzare virgole come delimitatori. </p> <p> Se si tiene premuto il tasto Ctrl e si fa clic con il pulsante destro del mouse all'interno del parametro Delimiter, viene visualizzato un menu <span class="wintitle"> Inserisci</span> . Questo menu contiene un elenco di caratteri speciali che vengono spesso utilizzati come delimitatori. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Separatore righe </td> 
      <td colname="col2">Facoltativo. Solo per <span class="wintitle"> ExportDelimitedTextFile</span> . I caratteri utilizzati per separare le righe nei file di output. Il valore predefinito è [CR] [LF]. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Nome </td> 
      <td colname="col2"> <p>Facoltativo. Identificatore per l’esportatore. Questo nome viene visualizzato nell’interfaccia Stato <span class="wintitle"></span> dettagliato. </p> <p> Per informazioni sull'interfaccia Stato <span class="wintitle"></span> dettagliato, vedere la Guida <i>utente di Workbench</i>dati. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Commenti </td> 
      <td colname="col2"> Facoltativo. Note sull'esportatore. </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Percorso di output </td> 
      <td colname="col2"> <p>Percorso di memorizzazione dei file di output. Il percorso è relativo alla cartella di installazione del server workbench dati. </p> <p> <p>Nota: Il server workbench dati che memorizza i dati di output è il server di elaborazione #0 nel file <span class="filepath"> profile.cfg</span> . </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Periodo di rotazione file </td> 
      <td colname="col2"> <p>Facoltativo. Frequenza con cui i dati vengono esportati nel file di output. Ciascun file di output contiene i dati relativi a un periodo di tempo specifico, il periodo di rotazione. Tutti i calcoli temporali sono in GMT: Un giorno inizia a mezzanotte GMT e termina il giorno successivo a mezzanotte GMT, anche se i dati scritti nel file includono un campo che è stato trasformato in ora locale. </p> <p> I valori disponibili sono i seguenti: </p> 
      <ul id="ul_64F56D093E2E4D07ACB7D7921F4E6FA1"> 
       <li id="li_E4985C7F56E443049AFF57B0270032D6"> ANNO. Ciascun file contiene dati per un anno civile. </li> 
       <li id="li_42E59BB7A5704C85A6079ED9715C44BC"> MESE. Ciascun file contiene dati per un mese di calendario. I mesi sono numerati da 1 (gennaio) a 12 (dicembre). </li> 
       <li id="li_91831283616C48DA8C8086776D181751"> SETTIMANA. Ogni file contiene dati per una settimana. Una settimana inizia il lunedì. La settimana che inizia in uno dei primi sette giorni dell'anno è la settimana 1, e la settimana precedente (parziale), se presente, è la settimana 0. </li> 
       <li id="li_BDB7B4D779434B98935261B8B5C0AABB"> GIORNO. Ogni file contiene dati per un giorno di calendario. </li> 
       <li id="li_018F4133E03C42F29073FED1DB082ED5"> ORA. Ogni file contiene dati per un'ora. </li> 
       <li id="li_EE8CF71BA12149F49D4B7F7108262CD0"> NESSUNO. Non viene eseguita alcuna rotazione. Tutti i dati vengono scritti sullo stesso file (o un insieme di file come determinato dalle altre impostazioni dei parametri). Vedere il parametro Formato <span class="wintitle"></span> nome file in questa tabella. </li> 
      </ul> <p>Il periodo di rotazione predefinito del file è DAY. </p> 
      <ul id="ul_0F3BC98275634F759E5022FF2C19715E"> 
       <li id="li_24DC4D144DA94ED0B7B50E8BB39DB8E3"> Impostare la rotazione del file su NONE solo quando si utilizza la modalità <span class="wintitle"></span>Offline. Consultate la descrizione dei parametri della modalità <a href="../../../../../home/c-dataset-const-proc/c-transf-func/c-config-files-transf/t-ins-transf-file/t-ins-transf-file.md#task-857fc535ccdb4c39b763179efa4b0f13"></a> offline. </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Formato nome file </td> 
      <td colname="col2"> <p>Facoltativo. Il formato del nome del file di output. </p> <p> Ogni voce di registro può essere memorizzata in un file il cui nome è derivato dall’ora di inizio del periodo di rotazione e, facoltativamente, dai valori dei campi nelle righe che contiene. I campi da utilizzare nel nome del file sono incorporati come escape del nome del campo (espresso come %<i>fieldname</i>%). </p> <p>I componenti nome file relativi al periodo di rotazione sono incorporati nella stringa di formato utilizzando le seguenti sequenze di escape: 
      <ul id="ul_3C5C8C5DC9104070ABCFDD85F49BE596"> 
       <li id="li_B100AE13FEA84AB6A1138CF58440E29E"> %yyyy% (anno di quattro cifre) </li> 
       <li id="li_0583970798494A1795B03866DC717FB9"> %yy% (anno di due cifre) </li> 
       <li id="li_10AA96200F294364A5CE9DC3F22C789A"> %mm% (mese di due cifre, 01 - 12) </li> 
       <li id="li_E112E367F62147C49751D6894E47607C"> %ww% (settimana di due cifre, 01 - 52) </li> 
       <li id="li_C4B30E38C05942BB8CAA92F3C9B98A3C"> %dd% (giorno di due cifre, 01 - 31) </li> 
       <li id="li_0318CA8C4DC441B48C16B29A615F3293"> %HH% (ora di due cifre, 00 - 23) </li> 
      </ul> </p> <p> Il formato del nome file predefinito è <span class="filepath"> %yyyy%%mm%%dd%-%x-mask%.txt</span> </p> 
      <ul id="ul_07AE3624E7D74632AD5E5F164048196F"> 
       <li id="li_BA5C2BFBA73D4AAD8D729B30FF812759"> Le sequenze di escape sono con distinzione tra maiuscole e minuscole. </li> 
       <li id="li_32CB9C98190D4B17B4DA84732CFB9E2F"> Se il periodo di rotazione del file è impostato su NONE, viene sostituita una stringa vuota per ciascuna delle sequenze di escape, se presenti. </li> 
       <li id="li_C64731961ED6402FB92210A42854BA72"> Viene generato un errore se Formato <span class="wintitle"> nome</span> file non restituisce un nome file univoco per ciascun periodo di rotazione (vedere il parametro Periodo di rotazione file in questa tabella). Ad esempio, quando si utilizza il periodo di rotazione DAY, le sequenze di escape %dd%, %mm% e %yy% o %yyyy% devono essere presenti nel pattern per evitare la perdita di dati. </li> 
       <li id="li_15CDA2ABE450418FA8D9C4BC581C4ADD"> Se si utilizzano sequenze di escape per i nomi dei campi all'interno del pattern e il campo specificato ha molti valori distinti, molti file di output vengono scritti per ciascun periodo di rotazione. Tenete presente che questo scenario potrebbe causare prestazioni scadenti, pertanto utilizzate questa funzione con cautela. </li> 
       <li id="li_D0F75E4FFAFF47C4AA8A8D14A6E1C18A"> Tutti i calcoli orari sono in GMT. </li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Esegui al passaggio del mouse </td> 
      <td colname="col2"> <p>Facoltativo. Quando ciascun file è finalizzato, è possibile eseguire un comando esterno (Windows). La riga di comando viene derivata dal nome del file finale sostituendo le seguenti sequenze di escape in questo parametro: </p> 
      <ul id="ul_5E16832BDBEA4757A2C02DE4B019A122"> 
       <li id="li_6A74D069353E4FE781657BF492675220"> %dir%. Parte della directory del nome del file finale, inclusa la barra rovesciata finale. </li> 
       <li id="li_2CF7232553C348089B1395BBB0BBD6AE"> %file%. Il nome del file (esclusa la directory e l'estensione) del file finale. </li> 
       <li id="li_901BAB90E5EA434F9EE37A60477F4591"> %ext%. L'estensione (compreso l'interlinea ".") del nome del file finale. </li> 
       <li id="li_AD7269A67A0041438A6951FD1898D458"> %path%. Nome percorso completo del file, equivalente a %dir%%file%%ext%. </li> 
      </ul> <p> Per impostazione predefinita, questo parametro è vuoto (non viene eseguito alcun comando). </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Limite memoria </td> 
      <td colname="col2"> <p>Facoltativo. La quantità di memoria in byte utilizzata per la memorizzazione dell'output dell'esportatore. Il valore predefinito è 10.000.000 byte. </p> <p> <p>Nota:  Se si dispone di molti file di output aperti allo stesso tempo, è possibile aumentare questo valore, ma è possibile ridurre la quantità di memoria disponibile per l'utilizzo da parte di altri componenti del sistema. Tuttavia, la riduzione di questo valore potrebbe rallentare il processo di esportazione. Per assistenza, contattate Adobe. </p> </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> Limite Open Files </td> 
      <td colname="col2"> <p>Facoltativo. Il numero massimo di file che possono essere aperti contemporaneamente per l'output dall'esportatore. Se questo numero viene superato, viene registrato un errore nel registro eventi e il server workbench dati si arresta. Il valore predefinito è 1000. </p> </td> 
      </tr> 
    </tbody> 
   </table>

1. Dopo aver definito l&#39;esportatore (e aver apportato modifiche ad altri parametri) nel [!DNL Transform.cfg] file, salvare il file localmente e salvarlo nel profilo appropriato nel computer server workbench dati.
