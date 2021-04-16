---
description: Il marketing del tuo sito web può comportare il posizionamento di annunci pubblicitari sotto forma di immagini o altri file rich media (serviti dal tuo server web) su siti web di terze parti.
title: Misurazione dell’impression pubblicitaria
uuid: ca2bd6bf-4f49-406c-b47a-18d6abfb48a4
exl-id: 77cd816e-63a4-4080-ac65-0661e1de4ec0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 4%

---

# Misurazione dell’impression pubblicitaria{#measuring-advertisement-impression}

Il marketing del tuo sito web può comportare il posizionamento di annunci pubblicitari sotto forma di immagini o altri file rich media (serviti dal tuo server web) su siti web di terze parti.

In questi casi, potrebbe essere utile misurare sia l’impressione dell’annuncio su un browser sia il successivo click-through, se si verifica, dell’URL di destinazione dell’annuncio sul sito web.

Per gli annunci sotto forma di immagini, l&#39;aggiunta di [!DNL Log=1] alla stringa di query determina la richiesta di immagine e quindi l&#39;impression pubblicitaria, catturata da [!DNL Sensor] a scopo di analisi.

```
<!—REFERENCE IMPRESSION TAG-> 
<IMG SRC="http://www.mysite.com/images/zag.gif?Log=1&v_ic=CAMPAIGN 1&v_ica=72890ab&v_icr=http://money.cnn.com/markets/"/>
<!--END REFERENCE IMPRESSION TAG-->
```

| Dati raccolti | Spiegazione | Esempio |
|---|---|---|
| v_ic= | Valore che indica la campagna di impression | v_ic=&quot;CAMPAIGN1&quot; |
| v_ica= | Valore che indica la risorsa della campagna di impression | v_ica=&quot;72890ab&quot; |
| v_icr= | Valore che indica il referente campagna di impression | v_icr=&quot;http://money.cnn.com/markets/ |

Oltre a aggiungere [!DNL Log=1] alla richiesta di immagine, è necessario aggiungere un identificatore all&#39;URL che porta dall&#39;annuncio alla pagina di destinazione all&#39;interno del sito web per tenere traccia dell&#39;annuncio che ha portato al click-through e per monitorare il click-through alla campagna particolare per quell&#39;annuncio.

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
   <td colname="col2"> Valore che indica la campagna di click-through </td> 
   <td colname="col3"> v_c="CAMPAIGN1" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_ca= </td> 
   <td colname="col2"> Valore che indica la risorsa della campagna di click-through </td> 
   <td colname="col3"> v_ca="72890ab" </td> 
  </tr> 
  <tr> 
   <td colname="col1"> v_cr= </td> 
   <td colname="col2"> Valore che indica il referente campagna di click-through </td> 
   <td colname="col3"> <p> <span class="filepath"> v_cr="http://money.cnn.com/</span> </p> <p>mercati/ </p> </td> 
  </tr> 
 </tbody> 
</table>
