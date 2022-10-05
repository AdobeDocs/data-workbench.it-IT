---
description: Informazioni concettuali sulle espressioni del foglio di lavoro e sull'utilizzo dei riferimenti alle celle.
title: Espressioni del foglio di lavoro
uuid: be57d6bd-3e13-4c90-9034-8e0f2b8315aa
exl-id: 1ff3ec24-0363-4b6c-8c91-31e49ed0f7c4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 2%

---

# Espressioni del foglio di lavoro{#worksheet-expressions}

{{eol}}

Informazioni concettuali sulle espressioni del foglio di lavoro e sull&#39;utilizzo dei riferimenti alle celle.

Il seguente foglio di lavoro fornisce dettagli sui visitatori che visualizzano la pagina Creazione guidata applicazioni fornita nel modulo di applicazione online di un sito Web di una banca.

![](assets/client-wkst.png)

* La colonna A mostra un elenco delle categorie di visitatori in fase di valutazione: visitatori, visitatori di riferimento e visitatori di provenienza dal referente A.
* La colonna B mostra il numero di visitatori di ogni categoria che hanno visualizzato la pagina Applica ora.
* La colonna C mostra i visitatori che hanno visualizzato sia le pagine Applica ora che la Creazione guidata applicazione.
* La colonna D contiene le percentuali dei visualizzatori Applica ora nelle tre categorie che hanno visualizzato anche la pagina Creazione guidata applicazione .

Il foglio di lavoro mostra che circa il 55% dei visitatori di cui al referente A che ha visualizzato la pagina Applica ora ha visualizzato anche la pagina Creazione guidata applicazione.

La tabella seguente fornisce formule di esempio per il foglio di lavoro nell&#39;esempio precedente:

<table id="table_0F5EFDB58040465AB599E6BE93324822"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cella del foglio di lavoro </th> 
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
   <td colname="col2"> <p><span class="filepath"> =Visitatori_referred[Page="/applynow/default.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>B4 </p> <p>Visitatori di riferimento da referente A che ha visualizzato la pagina Applica ora </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitatori_referred[Page="/applynow/default.asp" </span> </p> <p> E <span class="filepath"> Referrer="Rif A"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C2 </p> <p>Visitatori che hanno visualizzato la pagina Applica ora e la pagina Creazione guidata applicazione </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitatori[Pagina="/applynow/default.asp" </span> </p> <p> E <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C3 </p> <p>Visitatori di riferimento che hanno visualizzato la pagina Applica ora e la pagina Creazione guidata applicazione </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitatori_referred[Page="/applynow/default.asp" </span> </p> <p> E <span class="filepath"> Page="/applynow/appwizard.asp"]</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>C4 </p> <p>Visitatori di riferimento da referente A che ha visualizzato la pagina Applica ora e la pagina Creazione guidata applicazione </p> </td> 
   <td colname="col2"> <p> <span class="filepath"> =Visitatori_referred[Page="/applynow/default.asp"</span> </p> <p> E <span class="filepath"> Page="/applynow/appwizard.asp"</span> </p> <p> E <span class="filepath"> Referrer="Rif A"]</span> </p> </td> 
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
   <td colname="col1"> <p>D4 </p> <p>Percentuale di visitatori di riferimento dal referente A che ha visualizzato la pagina Applica ora e la pagina Creazione guidata applicazione </p> </td> 
   <td colname="col2"> <p><span class="filepath"> =C4/B4*100</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

Come per altre visualizzazioni, i fogli di lavoro vengono aggiornati automaticamente quando effettui una selezione in un’altra visualizzazione nell’area di lavoro. Per ulteriori informazioni sulla selezione, consulta [Effettuare le selezioni nelle visualizzazioni](../../../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746).

Nell’esempio di dati web seguente, diversi giorni di dati di sessione sono stati selezionati nella visualizzazione Sessions by Day (Sessioni per giorno) . Il foglio di lavoro mostra che durante l&#39;intervallo temporale selezionato, circa il 69% dei visitatori dal referente A che ha visualizzato la pagina Applica ora ha visualizzato anche la pagina Creazione guidata applicazione. Senza questa selezione (come mostrato nell&#39;esempio precedente), circa il 55% dei visitatori dal referente A ha visualizzato la pagina Applica ora e la pagina Creazione guidata applicazione.

![](assets/client-exp.png)

## Utilizzo dei riferimenti di cella {#section-0004e315c9c94d359b1a8a39794ba555}

È possibile sostituire qualsiasi stringa, indipendentemente dal fatto che si trovi o all&#39;interno di un&#39;altra espressione nel foglio di lavoro, con un riferimento di cella.

* **Riferimento a cella semplice:** La cella A2 contiene il testo Visitatori, utilizzato come intestazione. La cella B2 contiene [!DNL eval(A1)], che valuta [!DNL =Visitors].

* **Riferimento cella filtro:** La cella A5 contiene la data di ieri. La cella B5 contiene [!DNL Visitors[ Day=A5 ]], che valuta il numero di visitatori ieri.

* **Riferimento a cella concatenata:** La cella A5 contiene la data odierna e la cella A6 contiene il periodo di un’ora dalle 08:00 alle 08:59. La cella B6 contiene [!DNL Visitors[ Hour=A5+” ”+A6 ]], che valuta il numero di visitatori oggi compreso tra le 8:00 e le 9:00.
