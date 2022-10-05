---
description: Puoi creare un browser percorsi da un grafico, una tabella o una mappa del processo.
title: Creazione di browser del percorso
uuid: 84a5e587-fb02-461b-aec8-1b6ad473ebc3
exl-id: 9fa11b84-da73-447a-8b10-7eab381e3f66
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '380'
ht-degree: 2%

---

# Creazione di browser del percorso{#creating-path-browsers}

{{eol}}

Puoi creare un browser percorsi da un grafico, una tabella o una mappa del processo.

**Creazione di un browser del percorso da un grafico o una tabella**

1. Aggiungi un browser del percorso all&#39;area di lavoro. La visualizzazione è vuota tranne che per l’etichetta (Sequenza di...) nell’angolo in alto a sinistra.
1. Apri un grafico o una tabella che mostra la dimensione di cui desideri visualizzare gli elementi nel browser percorsi. Ad esempio, se lavori con i dati del sito web, apri un grafico di pagina o una tabella e identifica la pagina da impostare come principale.
1. Premi Ctrl+Alt e trascina l’elemento desiderato nel browser del percorso. L’etichetta nell’angolo in alto a sinistra del browser percorsi cambia per riflettere la dimensione di base di cui trascini l’elemento nel browser percorsi.

>[!NOTE]
>
>Trascinando un elemento in un browser percorsi, è possibile modificare la dimensione di base associata al browser percorsi, ma non la dimensione di livello, la dimensione di gruppo o la metrica. Pertanto, devi prestare attenzione nella scelta di una dimensione di base che abbia senso quando viene utilizzata con la dimensione di livello, la dimensione di gruppo e la metrica del browser del percorso. Per modificare la dimensione del livello, la dimensione del gruppo o la metrica, devi modificare la proprietà del browser del percorso [!DNL *.vw] in un editor di testo come Blocco note. Vedi [Configurazione dei browser dei percorsi](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).

**Per creare un browser del percorso da una mappa del processo**

>[!NOTE]
>
>Un browser percorsi creato da una mappa del processo visualizza solo gli elementi visualizzati nella mappa del processo. Altri elementi della dimensione di base non vengono visualizzati.

1. Creare una mappa del processo. Vedi [Creazione di mappe del processo](../../../../home/c-get-started/c-analysis-vis/c-proc-maps/c-create-proc-maps.md#concept-daf5b14dae7a442191611b1b9c1122bf).
1. Trascina l’elemento desiderato dalla mappa del processo al browser percorsi. L’elemento diventa la radice del browser percorsi.

>[!NOTE]
>
>Quando crei un browser percorsi da una mappa del processo, il browser percorsi ignora gli elementi della dimensione del livello senza elementi della dimensione di base associati. Quando trascini un nodo da una mappa del processo in un browser del percorso, la dimensione di base del browser del percorso (denominata Mappa) viene definita dalla mappa del processo e i relativi elementi sono limitati agli elementi della mappa del processo. Di conseguenza, alcuni elementi della dimensione a livello del browser del percorso non hanno elementi di dimensione di base associati e non sono rappresentati nel browser percorsi.
