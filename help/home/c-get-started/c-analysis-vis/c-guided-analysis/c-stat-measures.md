---
description: Per facilitare l’utilizzo delle statistiche, la Data Workbench fornisce tre misure statistiche nella visualizzazione guidata dell’analisi.
title: Misure statistiche
uuid: a8782cd2-d657-4c04-9c5d-8e0af2a3b76e
exl-id: 166ff98b-d531-4b31-897e-0c7fedbd2f4d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 0%

---

# Misure statistiche{#statistical-measures}

{{eol}}

Per facilitare l’utilizzo delle statistiche, la Data Workbench fornisce tre misure statistiche nella visualizzazione guidata dell’analisi.

>[!NOTE]
>
>Anche se la matematica può aiutarti a formulare giudizi sulle correlazioni nei tuoi dati, anche il contesto che circonda i dati deve essere preso in considerazione.

* **Chi Sq** è un test di rilevanza statistica che controlla l’aspetto del segno di spunta nella visualizzazione. Matematicamente, è una probabilità che possiamo respingere l&#39;ipotesi null, che afferma che le differenze osservate tra i due gruppi possono essere spiegate da variazioni casuali. Praticamente, se il valore di Chi Sq p è inferiore a quasi il 100%, possiamo ignorare la correlazione indipendentemente dalla sua forza misurata (come descritto nelle seguenti sezioni statistiche U e V).
* **Statistiche dell&#39;UE** è una misura dell’intensità della correlazione statistica. Matematicamente, proviene da un ramo della matematica chiamato teoria dell&#39;informazione ed è strettamente legato al concetto di informazione reciproca tra le distribuzioni dei due gruppi. In alternativa, si può pensare come la compressibilità di un gruppo dato uno schema di codifica ottimale per l&#39;altro gruppo. In pratica, questa misura funziona molto bene nel caso comune di una dimensione con molti elementi che contengono pochi visitatori. La misura varia da 0 (debole) a 1 (forte).
* **Statistiche su V** è anche una misura dell’intensità della correlazione statistica. Dal punto di vista matematico, si tratta del risultato statistico V di Cramer, che differisce solo da un passaggio di normalizzazione inteso a migliorare la simmetria della misura rispetto all’inversione della selezione. In pratica, questa misura funziona ragionevolmente bene con molti tipi di dimensioni ed è correlata a una misura statistica comunemente utilizzata. La misura varia da 0 (debole) a 1 (forte).

>[!NOTE]
>
>Le statistiche U e V sono state selezionate per completarsi a vicenda, ognuna sintonizzata per rilevare i tipi di correlazioni a cui l&#39;altra potrebbe non rispondere così fortemente.

Utilizzando questa visualizzazione come guida, puoi aggiungere altre visualizzazioni all’area di lavoro per fornire ulteriori informazioni sui dati in base alla selezione.

I seguenti [!DNL Site] L’esempio contiene un grafico a barre che mostra le sessioni per i giorni di gennaio, febbraio, marzo e aprile. Si noti che è selezionato un giorno in gennaio.

![](assets/vis_GuidedAnalysis_withVis.png)

La visualizzazione dell’analisi guidata nell’angolo in basso a sinistra dell’area di lavoro indica che la dimensione Numero di sessione fornisce informazioni utili sul giorno selezionato.

Esaminando il grafico a barre Numero sessione nell&#39;angolo in basso a destra dell&#39;area di lavoro, puoi vedere che i dati per la Sessione Numero 2 sono molto inferiori al valore di riferimento. Pertanto, possiamo concludere che, in percentuale, nel giorno selezionato si sono verificate meno sessioni al secondo rispetto al solito. Per visualizzare un grafico a barre per una qualsiasi delle dimensioni elencate nella visualizzazione di analisi guidata, seleziona semplicemente la dimensione facendo clic su di essa con il mouse.
