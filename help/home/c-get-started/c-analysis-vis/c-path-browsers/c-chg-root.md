---
description: Puoi modificare la radice di un browser di percorsi designando un elemento visualizzato come principale oppure aggiungendo un nuovo elemento alla visualizzazione.
solution: Analytics
title: Modifica della directory principale del browser percorso
topic: Data workbench
uuid: 0bb9b004-9736-411b-bd22-cac04f4733a6
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modifica della directory principale del browser percorso{#change-the-path-browser-s-root}

Puoi modificare la radice di un browser di percorsi designando un elemento visualizzato come principale oppure aggiungendo un nuovo elemento alla visualizzazione.

>[!NOTE]
>
>Non è possibile impostare un nodo iniziale o finale come radice di un browser di percorsi.

**Impostazione della radice di un browser percorso**

* Fate clic con il pulsante destro del mouse sull’elemento desiderato e fate clic **[!UICONTROL Set as root]**.

**Per aggiungere un nuovo elemento al browser Percorsi**

1. Aprite un grafico o una tabella che mostra la dimensione di cui desiderate visualizzare gli elementi nel browser dei percorsi.

   Ad esempio, se state lavorando con i dati del sito Web, aprite un grafico a pagina o una tabella e identificate la pagina da impostare come principale.

1. Premere Ctrl+Alt e trascinare l&#39;elemento desiderato nella posizione principale del browser percorso.

   >[!NOTE]
   >
   >Puoi modificare la dimensione di base associata a un browser percorso trascinando un elemento della dimensione desiderata nel browser percorso. Questo elemento diventa la nuova radice del browser percorso e l&#39;etichetta nell&#39;angolo superiore sinistro del browser percorso cambia per riflettere la dimensione per questo elemento.

   Ad esempio, se create un browser con percorso di pagina che mostra la sequenza di pagine per ogni sessione, Se doveste trascinare un elemento della dimensione Termine di ricerca nel browser Percorsi, l&#39;elemento del termine di ricerca diventerebbe la nuova radice, e l&#39;etichetta ora mostrerebbe la sequenza di Termini di ricerca per ogni sessione.

   >[!NOTE]
   >
   >Trascinando un elemento in un browser percorso è possibile che la dimensione di base associata al browser percorsi venga modificata, ma non la dimensione livello, la dimensione gruppo o la metrica. Pertanto, devi prestare attenzione nella scelta di una dimensione di base che abbia senso se utilizzata con la dimensione di livello, la dimensione di gruppo e la metrica del browser del percorso. Per modificare la dimensione del livello, la dimensione del gruppo o la metrica, è necessario modificare il file del browser del percorso in un editor di testo come [!DNL *.vw] Blocco note. Consultate [Configurazione dei browser](../../../../home/c-get-started/c-intf-anlys-ftrs/t-config-path-brwsr.md#task-bbb3ddaa140a414f984b697c2b8202a3)di percorsi.

