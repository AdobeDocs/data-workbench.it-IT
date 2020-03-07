---
description: Elaborazione di file XML come origini di registro per definire decodificatori per l'estrazione di dati dal file XML.
solution: Analytics
title: Gruppi decodificatori XML
topic: Data workbench
uuid: 8fc9ab80-9a71-4fe2-a646-e830ffeb67b9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Gruppi decodificatori XML{#xml-decoder-groups}

Elaborazione di file XML come origini di registro per definire decodificatori per l&#39;estrazione di dati dal file XML.

>[!NOTE]
>
>Per definire i gruppi di decodificatori XML per le origini di registro XML è necessario conoscere la struttura e il contenuto del file XML, i dati da estrarre e i campi in cui tali dati vengono memorizzati. Questa sezione fornisce descrizioni di base dei parametri che è possibile specificare per i decoder. Il modo in cui si utilizza un decodificatore dipende dal file XML che contiene i dati di origine.

Per informazioni sui requisiti di formato per le origini di registro XML, vedere [Origini](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-6714c720fac044cbb9af003bf401b2ea)di registro. Per assistenza nella definizione dei decoder XML, contattate Adobe.

Il livello principale di un decodificatore XML è un gruppo di decodificatori (XMLDecoderGroup), ovvero un insieme di tabelle di decodificatori utilizzate per estrarre i dati da un file XML di un particolare formato. Se disponete di file XML di formati diversi, dovete definire un gruppo di decodificatori per ciascun formato. Ciascun gruppo di decodificatori è costituito da una o più tabelle di decodificatori.

Nella tabella seguente sono descritti il parametro Tables e tutti i sottoparametri che è necessario specificare per definire un gruppo di decodificatori XML.

<table id="table_06C40C5149E94548A1B0C2ED4397624B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parametro </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Tabelle </td> 
   <td colname="col2"> <p>Ogni tabella in un gruppo di decodificatori rappresenta un livello di dati da estrarre dal file XML. Ad esempio, se desideri estrarre dati sui visitatori, creerai una tabella di decodificazione composta dalle informazioni che desideri estrarre per ogni visitatore. È inoltre possibile creare tabelle di decodificazione all'interno delle tabelle di decodificazione (vedere Bambini). </p> <p> <b>Aggiunta di una tabella a un gruppo di decodificatori</b> 
     <ul id="ul_C73CAD77440B4465B9FCE08BF4FA0749"> 
      <li id="li_C4B8CC5A85D942898F1EB76778105818"> Fare clic con il pulsante destro del mouse su <span class="uicontrol"> Tables </span> e scegliere <span class="uicontrol"> Add new </span> &gt; <span class="uicontrol"> XMLDecoderTable </span>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campi </td> 
   <td colname="col2"> <p>Campi estesi (ad esempio x-trackingid, x-email) in cui vengono memorizzati i dati. I dati da memorizzare nel campo sono determinati dai sottomoduli Percorso e/o Operazione. </p> <p> Percorso è il livello del campo all'interno del file XML strutturato. Il percorso di un campo è relativo al percorso della tabella in cui è definito. Alcuni esempi includono <span class="filepath"> tag.tag. </span> o <span class="filepath"> tag.tag.tag.@attribute </span>. I percorsi seguono la distinzione tra maiuscole e minuscole. </p> <p> Un'operazione viene applicata a ogni linea del percorso specificato per produrre un output. Sono disponibili le seguenti operazioni: 
     <ul id="ul_B264A411D7E3446288E7E69D62150B8B"> 
      <li id="li_5936E81C0EEF46AFB780E451A04A88E4"><b>ULTIMO:</b> Il campo prende il valore dell'ultima occorrenza del percorso nel file XML. </li> 
      <li id="li_7BC4F24F2CA84C2EB64B06FE09B4CAF6"><b>RANDOM:</b> Assegna un valore casuale al campo. Questa operazione è utile per generare un ID univoco, ad esempio per il campo x-trackingid. </li> 
      <li id="li_C1D34EA11BFB4859A25A275A9B63FB56"><b>EREDITARIO:</b> Il campo definito eredita il proprio valore dal campo corrispondente della tabella padre. </li> 
      <li id="li_F62FB8CD962E4E1495D9A2D5B7A78E2A"><b>"<i>costante </i>":</b> La costante deve essere racchiusa tra virgolette. È possibile utilizzare un'operazione costante per verificare l'esistenza di un particolare percorso; se il percorso esiste, al campo viene assegnato il valore della costante. </li> 
     </ul> </p> <p> <b>Aggiunta di un campo a una tabella decoder</b> </p> <p> 
     <ul id="ul_91D104D927424DEA9E788E43B2F6FEA9"> 
      <li id="li_5448B01EE82349569BBFC99C9604D7B8"> Fare clic con il pulsante destro del mouse su <span class="uicontrol"> Campi </span>, quindi scegliere <span class="uicontrol"> Aggiungi nuovo </span> &gt; <span class="uicontrol"> XMLDecoderField </span>. Definire Campo, Operazione e Percorso, a seconda delle necessità. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Percorso </td> 
   <td colname="col2"> <p>Il livello all'interno del file XML strutturato per il quale la tabella decoder contiene informazioni. Per una tabella di decodifica XML figlio, il percorso è relativo al percorso della tabella padre. I percorsi seguono la distinzione tra maiuscole e minuscole. </p> <p> Ad esempio, se il file XML contiene la struttura: </p> 

    &amp;lt;visitor&amp;gt;
    
    &amp;nbsp;
    
    ..
    
    &amp;nbsp;
    
    &amp;lt;/visitor&amp;gt;
    
    &amp;lt;/logdata&amp;gt;&amp;nbsp; &lt;/code> &lt;p> il percorso sarà &lt;span class=&quot;filepath&quot;> logdata.visitor &lt;/span>. &lt;/p> &lt;/td>
</tr> 
  <tr> 
   <td colname="col1"> Tabella </td> 
   <td colname="col2"> <p>Il valore di questo parametro deve sempre essere "Log Entry". </p> <p> <p>Nota:  Non modificate questo valore senza consultare Adobe. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bambini </td> 
   <td colname="col2"> <p>Facoltativo. Una o più tabelle decoder incorporate. Ogni elemento secondario include i parametri Campi, Percorso e Tabella descritti in precedenza. </p> <p> <b>Aggiunta di un elemento secondario a una tabella decoder</b> </p> <p> 
     <ul id="ul_902AC6CA5D66457D84CBA3194FF49BBE"> 
      <li id="li_07B4D60E7E2E4630B4878691E575936A"> Fare clic con il pulsante destro del mouse su <span class="uicontrol"> Figli </span> e scegliere <span class="uicontrol"> Aggiungi nuovo </span> &gt; <span class="uicontrol"> XMLDecoderTable </span>. Definire Campo, Operazione e Percorso, a seconda delle necessità. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Per utilizzare un file XML come origine di registro per un set di dati, è necessario definire i gruppi di decodificatori XML e le tabelle per estrarre le informazioni da elaborare nel set di dati. In questo esempio viene illustrato come definire gruppi di decodificatori e tabelle per un&#39;origine di registro XML di esempio per un set di dati Web.

Il seguente file XML contiene informazioni su un visitatore del sito Web, incluso un Experience Cloud ID, un indirizzo e-mail, un indirizzo fisico e informazioni sulle visualizzazioni della pagina del visitatore.

![](assets/xmlFile_LogSource.png)

Poiché disponiamo di un singolo file XML, è necessario un solo gruppo di decodificatori, denominato &quot;Sample XML Format&quot;. Questo gruppo di decodificatori si applica a tutti gli altri file XML dello stesso formato di questo file. Per iniziare a creare tabelle di decodificatore XML all&#39;interno di questo gruppo di decodificatori, è necessario innanzitutto determinare quali informazioni si desidera estrarre e quali campi saranno memorizzati.

In questo esempio, estraiamo informazioni sul visitatore e sulle visualizzazioni di pagina associate a tale visitatore. A questo scopo, creiamo una tabella di decodificatore XML di primo livello (principale) con informazioni sul visitatore e una tabella di decodificatore XML (figlio) incorporata con informazioni sulle visualizzazioni di pagina del visitatore.

**Le informazioni per la tabella padre (visitatore) sono le seguenti**

* Identificatore del tipo di dati per ogni riga di dati nel file XML. Usiamo VISITOR come identificatore per identificare rapidamente le righe di dati relative al visitatore e non alle visualizzazioni della pagina. Questo valore può essere memorizzato nel campo x-rowtype.
* L’ID del visitatore, che viene memorizzato nel campo x-trackingid.
* L&#39;indirizzo e-mail del visitatore (contact.email), memorizzato nel campo x-email.
* Lo stato di registrazione del visitatore. Se il visitatore è un utente registrato, possiamo memorizzare il valore &quot;1&quot; nel campo x-is-registrato.
* Il valore Percorso è [!DNL logdata.visitor]e il valore Tabella è [!DNL Log Entry]. Per informazioni su questi parametri, vedere la tabella XMLDecoderGroup riportata sopra.

**Le informazioni per la tabella figlio (visualizzazioni di pagina) sono le seguenti:**

* Identificatore del tipo di dati per ogni riga di dati nel file XML. Usiamo &quot;PAGEVIEW&quot; come identificatore, in modo da poter identificare rapidamente le righe di dati relative alle visualizzazioni di pagina del visitatore e non solo al visitatore. Questo valore viene memorizzato nel campo x-rowtype.
* L’ID del visitatore. Questo valore viene ereditato dalla tabella padre e memorizzato nel campo x-trackingid.
* La marca temporale di ciascuna visualizzazione di pagina, memorizzata nel campo x-event-time.
* URI di ogni visualizzazione di pagina, memorizzato nel campo cs-uri-stem.
* Il valore Path è pageview e il valore Table è &quot;Log Entry&quot;. Per informazioni su questi parametri, vedere la tabella XMLDecoderGroup riportata sopra.

La seguente acquisizione dello schermo mostra una porzione di [!DNL Log Processing Dataset Include] file con il gruppo di decodificatori XML risultante per il file XML di esempio, in base alla struttura discussa delle tabelle di decoder XML padre e figlio.

![](assets/cft_LogProc_xmldecodergroup_top.png)

![](assets/cfg_LogProcessingInclude_XMLDecoderGroup_bottom.png)

Una tabella che mostra l&#39;output di questo decodificatore per il file XML di esempio ha un aspetto simile a quello riportato di seguito:

| x-rowtype | cs—uri-stem | x-email | x-is-registrato | x-event-time | x-tracking-id |
|---|---|---|---|---|---|
| VISITATORE |  | foo@bar.com | 1 |  | 1 |
| PAGEVIEW | /index.html |  |  | 2006-01-01 08:00:00 | 1 |
| PAGEVIEW | / |  |  | 2006-01-01 08:00:30 | 1 |

È possibile creare una tabella come quella riportata sopra in Workbench dati utilizzando un&#39;interfaccia visualizzatore di campi. Per informazioni sull&#39;interfaccia del visualizzatore di campi, consultate Strumenti [di configurazione](../../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5)DataSet.

## Utilizzo di #value sull&#39;elemento XML per leggere il valore dell&#39;attributo {#section-88758428afb94f0baa5a986604d53bc1}

You can now use the **[!DNL #value]** tag in XML paths to pull the value of an XML element.

Ad esempio, specificando in precedenza un percorso di **`<Hit><Page name="Home Page" index="20">home.html</Page></Hit>`** sinistra non è possibile leggere il valore del `<Page>` tag. Per leggere il valore di un `<Page>` tag e i relativi attributi, potete utilizzare [!DNL Hit.Page.@name] e [!DNL Hit.Page.@index] rispettivamente. È inoltre possibile richiamare il valore del tag utilizzando **`Hit.Page.#value`** espressione.

Ad esempio, potete leggere il valore del tag `<varValue>` aggiungendo il seguente campo nel decoder:

```
7 = XMLDecoderField: 
Field = string: x-varvalue-name-added 
Operation = string: LAST 
Path = string:  
<b>#value</b> 
Path = string: varValue 
Table = string: Log Entry
```

Allo stesso modo, potete leggere il valore del tag `<Rep>` aggiungendo il seguente campo nel decoder:

```
7 = XMLDecoderField: 
Field = string: x-rep-name-added 
Operation = string: LAST 
Path = string: Rep.# 
<b>value</b> 
Path = string: Reps 
Table = string: Log Entry
```

Al contrario, per leggere il valore del tag elemento senza attributo, un `<text>` tag sotto un `<line>` tag e il relativo valore possono essere letti direttamente assegnando &quot; [!DNL text]&quot; in un percorso o utilizzando [!DNL line.text], a seconda di come avete creato il decodificatore.

```
2 = XMLDecoderField: 
Field = string: x-chat-text 
Operation = string: LAST 
Path = string:  
<b>text</b> 
Path = string:  
<b>line</b> 
Table = string: Log Entry
```

