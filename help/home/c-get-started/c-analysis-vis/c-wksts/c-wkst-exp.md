---
description: Informazioni concettuali sulle espressioni del foglio di lavoro e sull'utilizzo dei riferimenti alle celle.
solution: Analytics
title: Espressioni del foglio di lavoro
topic: Data workbench
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Espressioni del foglio di lavoro{#worksheet-expressions}

Informazioni concettuali sulle espressioni del foglio di lavoro e sull&#39;utilizzo dei riferimenti alle celle.

Il seguente foglio di lavoro contiene informazioni dettagliate sui visitatori che visualizzano la pagina Creazione guidata applicazione fornita nel modulo di applicazione online del sito Web di una banca.

![](assets/client-wkst.png)

* La colonna A mostra un elenco delle categorie di visitatori che vengono valutati: visitatori, visitatori di riferimento e visitatori di riferimento da Referente A.
* La colonna B mostra il numero di visitatori in ciascuna categoria che ha visualizzato la pagina Applica ora.
* La colonna C mostra i visitatori che hanno visualizzato sia le pagine Applica ora che le pagine Creazione guidata applicazione.
* La colonna D contiene le percentuali dei visualizzatori Applica ora nelle tre categorie che hanno visualizzato anche la pagina Creazione guidata applicazione.

Il foglio di lavoro mostra che circa il 55% dei visitatori di cui al referente A che ha visualizzato la pagina Applica ora ha visualizzato anche la pagina Creazione guidata applicazione.

La tabella seguente fornisce formule di esempio per il foglio di lavoro dell&#39;esempio precedente:

<table id="table_0F5EFDB58040465AB599E6BE93324822"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cella foglio di lavoro </th> 
   <th colname="col2" class="entry"> Formula </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>B2 </p> <p>Visitatori che hanno visualizzato la pagina Applica ora </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visitatori[Pagina="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B3 </p> <p>Visitatori di riferimento che hanno visualizzato la pagina Applica ora </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =Visitatori di riferimento[Pagina="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>Visitatori di riferimento da Referente A che ha visualizzato la pagina Applica ora </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitatori di riferimento[Pagina="/applynow/default.asp" </span> </p> <p> AND <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>Visitatori che hanno visualizzato la pagina Applica ora e la pagina Applicazione guidata </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitatori[Pagina="/applynow/default.asp" </span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>Visitatori di riferimento che hanno visualizzato la pagina Applica ora e la pagina Creazione guidata applicazione </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitatori di riferimento[Pagina="/applynow/default.asp" </span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>Visitatori di riferimento da Referente A che ha visualizzato la pagina Applica ora e la pagina Applicazione guidata </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitatori di riferimento[Pagina="/applynow/default.asp"</span> </p> <p> AND <span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> AND <span class="filepath"> Referrer="Ref A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D2 </p> <p>Percentuale di visitatori che hanno visualizzato la pagina Applica ora e la pagina Creazione guidata applicazione </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C2/B2*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D3 </p> <p>Percentuale di visitatori di riferimento che hanno visualizzato la pagina Applica ora e la pagina Creazione guidata applicazione </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C3/B3*100</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>D4 </p> <p>Percentuale di visitatori di riferimento da Referente A che ha visualizzato la pagina Applica ora e la pagina Creazione guidata applicazione </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Come per altre visualizzazioni, i fogli di lavoro si aggiornano automaticamente quando si effettua una selezione in un’altra visualizzazione dell’area di lavoro. Per ulteriori informazioni sulla creazione di selezioni, consulta [Effettuare selezioni in Visualizzazioni](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

Nell’esempio di dati Web seguente, diversi giorni di dati delle sessioni sono stati selezionati nella visualizzazione Sessioni per giorno. Il foglio di lavoro mostra che, nel periodo di tempo selezionato, circa il 69% dei visitatori provenienti dal Referente A che ha visualizzato la pagina Applica ora ha visualizzato anche la pagina Creazione guidata applicazione. Senza questa selezione (come illustrato nell&#39;esempio precedente), circa il 55% dei visitatori del referente A ha visualizzato sia la pagina Applica ora che la pagina Creazione guidata applicazione.

![](assets/client-exp.png)

## Utilizzo dei riferimenti di cella {#section-0004e315c9c94d359b1a8a39794ba555}

È possibile sostituire qualsiasi stringa, sia in modo indipendente che all&#39;interno di un&#39;altra espressione del foglio di lavoro, con un riferimento di cella.

* **Riferimento cella semplice:** La cella A2 contiene il testo Visitatori, che viene utilizzato come intestazione. La cella B2 contiene [!DNL eval(A1)], che restituisce [!DNL =Visitors].

* **Riferimento cella filtro:** La cella A5 contiene la data di ieri. La cella B5 contiene [!DNL Visitors[ Day=A5 ]], che corrisponde al numero di Visitatori ieri.

* **Riferimento cella concatenato:** La cella A5 contiene la data odierna e la cella A6 contiene il periodo di un’ora compreso tra 08:00 e 08:59. La cella B6 contiene [!DNL Visitors[ Hour=A5+&quot;&quot;+A6 ]], che valuta il numero di Visitatori oggi compreso tra le 8:00 e le 9:00.

