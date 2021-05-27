---
description: Puoi modificare la directory principale di un browser del percorso designando un elemento visualizzato come principale o aggiungendo un nuovo elemento alla visualizzazione.
title: Modifica della directory principale del browser del percorso
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
exl-id: 09842b93-af26-42b9-9395-a02b86978b21
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# Modifica della directory principale del browser del percorso{#change-the-path-browser-s-root}

Puoi modificare la directory principale di un browser del percorso designando un elemento visualizzato come principale o aggiungendo un nuovo elemento alla visualizzazione.

>[!NOTE]
>
>Non è possibile impostare un nodo iniziale o finale come radice di un browser percorsi.

**Impostazione della radice di un browser del percorso**

* Fai clic con il pulsante destro del mouse sull’elemento desiderato e fai clic su **[!UICONTROL Set as root]**.

**Per aggiungere un nuovo elemento al browser percorsi**

1. Apri un grafico o una tabella che mostra la dimensione di cui desideri visualizzare gli elementi nel browser percorsi.

   Ad esempio, se lavori con i dati del sito web, apri un grafico o una tabella di pagina e identifica la pagina da impostare come principale.

1. Premi Ctrl+Alt e trascina l’elemento desiderato nella posizione principale sul browser percorsi.

   >[!NOTE]
   >
   >Puoi modificare la dimensione di base associata a un browser percorsi trascinando un elemento della dimensione desiderata nel browser percorsi. Questo elemento diventa la nuova radice del browser percorsi e l&#39;etichetta nell&#39;angolo in alto a sinistra del browser percorsi cambia per riflettere la dimensione di questo elemento.

   Ad esempio, supponiamo di creare un browser del percorso della pagina che mostri la Sequenza di pagine per ogni sessione. Se devi trascinare un elemento della dimensione Termine di ricerca nel browser percorsi, l’elemento del termine di ricerca diventerebbe la nuova radice e l’etichetta mostrerebbe ora la Sequenza dei Termini di ricerca per ogni sessione.

   >[!NOTE]
   >
   >Trascinando un elemento in un browser percorsi, è possibile modificare la dimensione di base associata al browser percorsi, ma non la dimensione di livello, la dimensione di gruppo o la metrica. Pertanto, devi prestare attenzione nella scelta di una dimensione di base che abbia senso quando viene utilizzata con la dimensione di livello, la dimensione di gruppo e la metrica del browser del percorso. Per modificare la dimensione del livello, la dimensione del gruppo o la metrica, è necessario modificare il file [!DNL *.vw] del browser del percorso in un editor di testo come Blocco note. Consulta [Configurazione dei browser del percorso](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3).
