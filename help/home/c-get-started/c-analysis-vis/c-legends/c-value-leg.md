---
description: Una legenda di valori visualizza gli eventi di valore definiti.
solution: Analytics
title: Leggende di valore
topic: Data workbench
uuid: 7779f442-2f45-4bf8-a62a-585aaceaeb3a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Leggende di valore{#value-legends}

Una legenda di valori visualizza gli eventi di valore definiti.

La legenda del valore è configurata solo in HBX e nelle [!DNL Site] applicazioni, ma può essere configurata per altre applicazioni. Per ulteriori informazioni, contattate i servizi di consulenza Adobe.

In HBX e [!DNL Site], un evento value è definito come una sessione che ha generato valore aziendale. Ad esempio, i record di dati dell&#39;evento associati a particolari visualizzazioni di pagina (ad esempio, una pagina di ringraziamento dell&#39;ordine o una pagina di completamento dell&#39;applicazione) possono rappresentare eventi di valore per un&#39;organizzazione aziendale.

Con gli eventi value, potete misurare e monitorare la quantità di valore generato dal sito Web. Potete valutare il valore commerciale in dollari per ogni evento e rispondere a domande come:

* Qual è il percorso più redditizio attraverso il sito Web?
* Quale referente o campagna ha generato il maggior valore?

Per ogni evento, la legenda visualizza il valore unitario (valore per evento) dell&#39;evento e il valore totale generato dall&#39;evento. È possibile utilizzare la legenda per definire e modificare gli eventi dei valori e per assegnare loro i valori delle unità.

Nella tabella seguente sono elencate le metriche correlate agli eventi dei valori.

| Metrica | Descrizione |
|---|---|
| Conversione | Percentuale di sessioni che hanno generato valore aziendale |
| Valore | Valore totale dell&#39;attività generato, in dollari |
| Media Valore | Valore aziendale medio generato, in dollari, per sessione |

Potete definire facilmente qualsiasi cosa i visitatori facciano nel sito Web come un evento di valore: invio di una richiesta di assistenza clienti, completamento di un’applicazione, visualizzazione di un contenuto o completamento di un acquisto. Ogni evento value corrisponde a un utente che accede a una particolare pagina o set di pagine del sito Web ed è associato a un valore aziendale in dollari. Ad esempio, potreste supporre che ogni utente che accede alla pagina &quot;Grazie per l’acquisto&quot; generi in media un margine di contributo di $20. È possibile definire un evento value per la pagina con un valore di $20.

## Definizione di nuovi eventi valore {#section-2ea4d168336e4d2e98b22b636ed43853}

**Per definire un nuovo evento value in HBX o[!DNL Site]**

Quando create un evento value, trascinate le pagine del sito Web che rappresentano un valore da una visualizzazione a una legenda del valore.

1. Aprite una legenda di valori.

   ![](assets/lgd_ValueLegend.png)

1. Aggiungere alla legenda eventi di valore dalle mappe di processo, dalle tabelle di pagine URI o dalle visualizzazioni gerarchiche di pagina:

   * Da una mappa di processo, trascinare i nodi dalla mappa di processo alla legenda.
   * Da una tabella di pagina URI, premere Ctrl+Alt e trascinare una pagina dalla tabella alla legenda.
   * Nella visualizzazione gerarchica delle pagine, fare clic a sinistra del nodo (cartella, pagina o gruppo) e trascinarlo sulla legenda.
   ![](assets/client-leg.png)

   Il puntatore del mouse visualizza la parola &quot;No&quot; fino a quando il mouse non raggiunge la legenda.

1. Nella legenda Valore, assegnate un valore business a ogni sessione per la quale si verifica l’evento:

   1. Nella [!DNL Value per Event] colonna, fare clic sulla cella che corrisponde alla pagina aggiunta come evento valore.
   1. Digitare l&#39;importo in dollari da assegnare per il valore dell&#39;evento e premere Invio.
   ![](assets/lgd_ValueLegend_Value.png)

   Per impostazione predefinita, l&#39;URL della pagina definita come evento valore viene visualizzato nella legenda del valore. Se necessario, potete fare doppio clic su questo URL nella legenda per passare alla modalità di modifica e rinominare l’evento. Potete inoltre modificare il valore di un particolare evento in qualsiasi momento. Il server Workbench dati ricalcola automaticamente le metriche basate sull&#39;evento relative al valore, ad esempio il valore medio e la conversione.

Dopo aver definito almeno un evento value, la dimensione Segmento valore diventa disponibile per l&#39;uso. Questa dimensione rappresenta il valore totale generato da un visitatore in tutte le sessioni.

## Rimuovi eventi valore {#section-25cd90a859384ca183c0fc0998f888cf}

* Fate clic con il pulsante destro del mouse sull’evento desiderato e fate clic **[!UICONTROL Delete Event]**.

   ![](assets/lgd_ValueLegend_deleteEvent.png)

>[!NOTE]
>
>Il server Workbench dati calcola le metriche per l&#39;intero set di dati accessibili al profilo in uso. Per impostazione predefinita, [!DNL Data Workbench Server] calcola metriche quali Valore, Eventi di valore, Valore medio e Conversione tra tutti i dati del set di dati di analisi, anche se i dati non provengono dalla stessa origine logica.

## Esporta in Microsoft Excel {#section-feaa7a8eb8124fafbc74169bebaed6d8}

Per informazioni sull&#39;esportazione delle finestre, vedere [Esportazione dei dati](../../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349)delle finestre.
