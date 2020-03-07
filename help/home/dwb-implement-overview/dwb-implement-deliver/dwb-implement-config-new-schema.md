---
description: In questo documento viene illustrato come modificare tutte le configurazioni predefinite di Workbench dati dopo l'implementazione del nuovo schema.
title: Modifiche alla configurazione per il nuovo schema
uuid: 7d59fc28-ce56-49e2-b068-d5e286dcc057
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modifiche alla configurazione per il nuovo schema{#configuration-changes-for-new-schema}

In questo documento viene illustrato come modificare tutte le configurazioni predefinite di Workbench dati dopo l&#39;implementazione del nuovo schema.

## Informazioni sullo schema del set di dati {#section-2ffac5170c894781bc943565af7ad479}

La base dello schema del set di dati è costituita da un set chiave di relazioni che costituiscono la spina dorsale dello schema di analisi Web di Workbench dati. Nell&#39;esempio seguente, lo schema analitico Web tipico fornisce un&#39;idea delle relazioni tra un visitatore, una visita e una visualizzazione di pagina. ![](assets/dwb_impl_schema_change1.png)

* Ogni visitatore può avere una o più visite.
* Ogni visita specifica viene generata da un solo visitatore.
* Una determinata visita può includere una o più visualizzazioni di pagina.
* Ogni visualizzazione pagina specificata appartiene a una sola visita. `<discoiqbr>`

Con l&#39;evoluzione del web e del mondo degli affari, nel corso degli anni sono cambiate anche le esigenze del web e dell&#39;analisi dei dati. I siti Web sono iniziati come luoghi dove guardare il contenuto. Ora potete guardare il contenuto; corrispondenza interattiva attraverso chat, video o invii; prodotti di acquisto; e molto altro. Inoltre, le aziende ora desiderano integrare i propri dati web con altri canali di dati nelle proprie aziende per ottenere una visione migliore dell&#39;insieme delle loro attività. Ad esempio, un&#39;azienda potrebbe voler integrare i dati relativi a Web, call center, e-mail, social, store e clienti. Grazie a questa integrazione di canali offline e online, gli schemi di set di dati si sono evoluti nel corso degli anni in cui non sono identici due schemi di set di dati.

`<discoiqbr>`Quando si integrano i dati online e offline, il termine &quot;visitatore&quot; non sembra sempre appropriato. Di conseguenza, talvolta viene utilizzato il termine &quot;cliente&quot; al posto del visitatore. ![](assets/dwb_impl_schema_change2.png) ![](assets/dwb_impl_schema_change3.png)

Il livello di coinvolgimento viene utilizzato per abilitare una singola visualizzazione del tempo, quando si dispone di dati provenienti da più origini dati. Ad esempio, supponiamo di avere una sola origine dati: i dati e-commerce raccolti dall&#39;attività del visitatore sul sito Web. In tal caso, il livello Visita indica le visite al sito da parte di tali visitatori. Notate che le dimensioni ora - &#39;Giorno&#39;, &#39;Settimana&#39;, &#39;Mese&#39;, ecc. - vengono tipicamente catturati a livello di &quot;Visita&quot;.

Allo stesso modo, il livello &quot;Evento&quot; porta tutti gli eventi (visualizzazione di pagina, chiamata al call center, ecc.) che si sono verificati durante un coinvolgimento. Combina tutti gli eventi online e offline per un cliente durante un coinvolgimento.

## Nuova struttura numerabile in DWB {#section-b77638ec04e4441cb51c56fd3d4abeb6}

La nuova struttura dello schema sostituisce Visitatore per cliente, Visita per coinvolgimento e Hit per evento. ![](assets/dwb_impl_schema_change4.png)

## Modifiche alla configurazione in base al nuovo schema del set di dati {#section-27135515be5c471ba2ee879d1ef4771f}

Per cambiare lo schema del set di dati da visitatore a cliente, è necessario modificare i seguenti file di configurazione:

1. Tutti i file di configurazione nella cartella DataSet in cui sono definite dimensioni contabili ed estese. ![](assets/dwb_impl_schema_change5.png)

1. I file di configurazione nella cartella Dimension, in cui vengono utilizzati come livello &quot;visitatore&quot;, &quot;visita&quot; o &quot;evento&quot;.

   Esempio: Campaign.cfg. Nel profilo Adobe SC, Campaign è definito a livello di visita. ![](assets/dwb_impl_schema_change6.png)

   L&#39;esempio seguente fornisce un&#39;idea della modifica dello schema padre da Visita a Coinvolgimento: ![](assets/dwb_impl_API10.png)

1. Poiché alcune delle metriche sono derivate o create da calcolatori, i file di configurazione nella cartella Metriche devono essere modificati o creati.

   Ad esempio: crea una nuova metrica [!DNL Customers.metric with formula = sum(one,customer)] o come Visualizzazioni pagina.metrica per *definirla* a livello di hit. Modificate la metrica, quindi modificate il livello in Evento anziché Hit.

   Metrica Visualizzazioni di pagina Adobe SC definita a livello di hit: ![](assets/dwb_impl_API8.png)

   `<discoiqbr>` `<discoiqbr>`Di seguito viene illustrata la metrica Visualizzazioni di pagina in base al nuovo schema: ![](assets/dwb_impl_API9.png)

1. Modificate il file *order.txt* nella cartella delle metriche in modo che rifletta le metriche nuove o modificate relative al cliente, al coinvolgimento e all&#39;evento.

   Adobe *SC order.txt* . ![](assets/dwb_impl_API11.png)

   *File Order.txt* con nuove modifiche allo schema: ![](assets/dwb_impl_API12.png)

1. Tutti i file di configurazione (.vw) nella cartella Visualization (Visualizzazione) devono essere modificati per fare riferimento ai nuovi livelli: Cliente, Partecipazione ed Evento. Ad esempio: Mappa del processo 2D, Mappa del processo 3D, ecc.

   Il file URI.vw predefinito di Adobe SC per la mappa del processo 2D è definito a livello di hit e a livello di gruppo di visite come illustrato di seguito: ![](assets/dwb_impl_API14.png)

   Modifiche da apportare in URI.vw per il nuovo schema: ![](assets/dwb_impl_API15.png)

