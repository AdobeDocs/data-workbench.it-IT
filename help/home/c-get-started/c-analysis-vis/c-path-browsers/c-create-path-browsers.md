---
description: Puoi creare un browser di percorsi da un grafico, una tabella o una mappa di processo.
solution: Analytics
title: Creazione di browser di percorsi
topic: Data workbench
uuid: 84a5e587-fb02-461b-aec8-1b6ad473ebc3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creazione di browser di percorsi{#creating-path-browsers}

Puoi creare un browser di percorsi da un grafico, una tabella o una mappa di processo.

**Per creare un browser di percorsi da un grafico o una tabella**

1. Aggiungere un browser di percorsi all&#39;area di lavoro. La visualizzazione è vuota, tranne per l’etichetta (Sequenza di...) nell’angolo in alto a sinistra.
1. Aprite un grafico o una tabella che mostra la dimensione di cui desiderate visualizzare gli elementi nel browser dei percorsi. Ad esempio, se state lavorando con i dati del sito Web, aprite un grafico a pagina o una tabella e identificate la pagina da impostare come principale.
1. Premere Ctrl+Alt e trascinare l&#39;elemento desiderato nel browser dei percorsi. L’etichetta nell’angolo in alto a sinistra del browser Percorsi viene modificata per riflettere la dimensione di base del cui elemento trascinate nel browser Percorsi.

>[!NOTE]
>
>Trascinando un elemento in un browser percorso è possibile che la dimensione di base associata al browser percorsi venga modificata, ma non la dimensione livello, la dimensione gruppo o la metrica. Pertanto, devi prestare attenzione nella scelta di una dimensione di base che abbia senso se utilizzata con la dimensione di livello, la dimensione di gruppo e la metrica del browser del percorso. Per modificare la dimensione del livello, la dimensione del gruppo o la metrica, è necessario modificare il file del browser del percorso in un editor di testo come [!DNL *.vw] Blocco note. Consultate [Configurazione dei browser](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3)di percorsi.

**Per creare un browser di percorsi da una mappa di processo**

>[!NOTE]
>
>Un browser di percorsi creato da una mappa di processo visualizza solo gli elementi visualizzati sulla mappa di processo. Altri elementi della dimensione di base non vengono visualizzati.

1. Create una mappa di processo. Consultate [Creazione di mappe](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept-daf5b14dae7a442191611b1b9c1122bf)di processo.
1. Trascinate l’elemento desiderato dalla mappa di processo al browser Percorsi. L’elemento diventa la radice del browser percorso.

>[!NOTE]
>
>Quando si crea un browser percorsi da una mappa di processo, il browser percorsi ignora gli elementi della dimensione livello senza elementi della dimensione di base associati. Quando trascinate un nodo da una mappa di processo su un browser di percorsi, la dimensione di base del browser di percorsi (denominata Mappa) viene definita dalla mappa di processo e i suoi elementi sono limitati agli elementi della mappa di processo. Di conseguenza, alcuni elementi della dimensione del livello del browser del percorso non hanno elementi della dimensione di base associati e non sono rappresentati nel browser percorso.

