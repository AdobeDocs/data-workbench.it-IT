---
description: Il marketing del sito Web può comportare il posizionamento di annunci pubblicitari sotto forma di immagini o altri file multimediali (serviti dal server Web) su siti Web di terze parti.
solution: Analytics
title: Misurazione dell'impatto pubblicitario
topic: Data workbench
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Misurazione dell&#39;impatto pubblicitario{#measuring-advertisement-impression}

Il marketing del sito Web può comportare il posizionamento di annunci pubblicitari sotto forma di immagini o altri file multimediali (serviti dal server Web) su siti Web di terze parti.

In questi casi, potete misurare sia l’impressione dell’annuncio pubblicitario su un browser, sia il successivo click-through, se si verifica, dell’URL di destinazione dell’annuncio sul vostro sito Web.

Per gli annunci pubblicitari sotto forma di immagini, l&#39;aggiunta [!DNL Log=1] alla stringa di query determina la richiesta di immagine, e quindi l&#39;impressione di annuncio, catturata da [!DNL Sensor] per fini di analisi.

```
<!—REFERENCE IMPRESSION TAG-> 
<IMG SRC="http://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=http://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_ic= | Valore che indica la campagna Impression | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | Valore che indica la risorsa campagna di impressione | v_ica=&quot;72890ab&quot; |
| v_icr= | Valore che indica il referente della campagna Impression | v_icr=&quot;http://money.cnn.com/markets/ |

Oltre ad aggiungere [!DNL Log=1] alla richiesta dell’immagine, è necessario aggiungere un identificatore all’URL che conduce dall’annuncio alla pagina di destinazione all’interno del sito Web, per tenere traccia dell’annuncio che ha portato al click-through e per monitorare il click-through alla campagna particolare per quell’annuncio.

```
<a href=”www.mysite.com/path/to/landingpage?Log=1&v_c=CAMPAIGN&v_ca=72890ab&v_cr=http://money.cnn.com/markets/”>
Click Here
</a>
```

<table id="table_B87134C522EF4AC9BD2AFA6F4A0CF574"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Dati raccolti </th> 
   <th colname="col2" class="entry"> Spiegazione </th> 
   <th colname="col3" class="entry"> Esempio </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> v_c= </td> 
   <td colname="col2"> Valore che indica la campagna Click-through </td> 
   <td colname="col3"> v_c="CAMPAIGN1" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_ca= </td> 
   <td colname="col2"> Valore che indica la risorsa campagna Click-through </td> 
   <td colname="col3"> v_ca="72890ab" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_cr= </td> 
   <td colname="col2"> Valore che indica il referente campagna Click-through </td> 
   <td colname="col3"> <p> <span class="filepath"> v_cr="http://money.cnn.com/</span> </p> <p>markets/ </p> </td> 
  </tr> 
 </tbody> 
</table>

