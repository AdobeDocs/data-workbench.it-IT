---
description: Per semplificare le statistiche, Workbench dati fornisce tre misure statistiche nella visualizzazione dell'analisi guidata.
solution: Analytics
title: Misure statistiche
topic: Data workbench
uuid: a8782cd2-d657-4c04-9c5d-8e0af2a3b76e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Misure statistiche{#statistical-measures}

Per semplificare le statistiche, Workbench dati fornisce tre misure statistiche nella visualizzazione dell&#39;analisi guidata.

>[!NOTE]
>
>Anche se la matematica può aiutarti a formulare giudizi sulle correlazioni nei dati, anche il contesto che circonda i dati deve essere preso in considerazione.

* **Chi Sq p** è un test di rilevanza statistica che controlla l’aspetto del segno di spunta nella visualizzazione. Matematicamente, è una probabilità che possiamo respingere l&#39;ipotesi null, che afferma che le differenze osservate tra i due gruppi possono essere spiegate da variazioni casuali. Praticamente, se il valore di Chi Sq p è inferiore a quasi 100%, possiamo ignorare la correlazione indipendentemente dalla sua intensità misurata (come descritto nelle seguenti sezioni statistiche U e V).
* **La statistica** U è una misura della forza della correlazione statistica. Matematicamente, proviene da un ramo della matematica chiamato teoria dell&#39;informazione ed è strettamente collegato al concetto di informazione reciproca tra le distribuzioni dei due gruppi. In alternativa, può essere considerata come la compressibilità di un gruppo dato uno schema di codifica ottimale per l&#39;altro gruppo. Praticamente, questa misura funziona molto bene nel caso comune di una dimensione con molti elementi che contengono pochi visitatori. La misura varia da 0 (debole) a 1 (forte).
* **V statistica** è anche una misura della resistenza della correlazione statistica. Dal punto di vista matematico, si tratta della statistica V di Cramer, che differisce solo da un passo di normalizzazione inteso a migliorare la simmetria della misura rispetto all’inversione della selezione. In pratica, questa misura funziona abbastanza bene con molti tipi di dimensioni ed è correlata a una misura statistica comunemente utilizzata. La misura varia da 0 (debole) a 1 (forte).

>[!NOTE]
>
>Le statistiche U e V sono state selezionate per completarsi l&#39;una con l&#39;altra, ciascuna sintonizzata per rilevare tipi di correlazioni alle quali l&#39;altra potrebbe non rispondere così fortemente.

Utilizzando questa visualizzazione come guida, puoi aggiungere altre visualizzazioni all’area di lavoro per fornire ulteriori informazioni sui dati in base alla selezione.

L&#39; [!DNL Site] esempio seguente contiene un grafico a barre che mostra le sessioni per i giorni di gennaio, febbraio, marzo e aprile. Si noti che un giorno in gennaio è selezionato.

![](assets/vis_GuidedAnalysis_withVis.png)

La visualizzazione dell’analisi guidata nell’angolo inferiore sinistro dell’area di lavoro indica che la dimensione Numero sessione fornisce informazioni utili sul giorno selezionato.

Esaminando il grafico a barre Numero sessione nell&#39;angolo inferiore destro dell&#39;area di lavoro, potete vedere che i dati per la sessione numero 2 sono molto inferiori al valore di riferimento. Di conseguenza, possiamo concludere che, come percentuale, il giorno selezionato si sono svolte meno sessioni di seconda rispetto al normale. Per visualizzare un grafico a barre per qualsiasi dimensione elencata nella visualizzazione di analisi guidata, seleziona semplicemente la dimensione facendo clic su di essa con il mouse.
