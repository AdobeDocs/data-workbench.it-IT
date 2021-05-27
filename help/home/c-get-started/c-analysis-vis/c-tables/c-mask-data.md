---
description: La mascheratura si riferisce alla selezione di un sottoinsieme di dati o di un sottoinsieme di elementi in una dimensione.
title: Dati della maschera
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
exl-id: 3029e08e-827f-40d7-b5a1-45630876a097
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '702'
ht-degree: 1%

---

# Dati della maschera{#mask-data}

La mascheratura si riferisce alla selezione di un sottoinsieme di dati o di un sottoinsieme di elementi in una dimensione.

mascherate o nascondete gli elementi che non desiderate includere nell’analisi.

Data Workbench fornisce due metodi per mascherare gli elementi dimensionali. Il primo metodo utilizza le opzioni disponibili nel menu [!DNL Mask] . Utilizzando le opzioni del menu [!DNL Mask], puoi utilizzare il mouse per selezionare gli elementi da mostrare o mascherare, oppure visualizzare elementi di primo livello quando ordini i dati per metrica. Il secondo metodo per mascherare gli elementi dimensionali utilizza una ricerca.

**Per mascherare i dati**

1. Fai clic con il pulsante destro del mouse su un elemento o sull’etichetta della dimensione desiderata e fai clic su **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. Fai clic su una delle opzioni seguenti:

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]** o  **[!UICONTROL 500]** degli elementi visualizzati ordinati per metrica
   * **[!UICONTROL Show top > All Positive]** per visualizzare solo valori maggiori di zero (0)
   * **[!UICONTROL Display “X more”]** per visualizzare il numero di elementi attualmente mascherati
   * **[!UICONTROL At least one >]***&lt;>>*(disponibile solo quando si lavora con una dimensione standard)**[!UICONTROL countable dimension name]**

      Quando si lavora con una dimensione standard, questa opzione consente di mascherare una dimensione in base a una dimensione conteggiata. Quando è selezionata questa opzione, la tabella mostra solo gli elementi con almeno un elemento della dimensione numerabile selezionata. La tabella visualizza fino a 1.023 elementi.

>[!NOTE]
>
>Poiché l’Adobe [!DNL Platform] elabora i dati in ordine casuale, quando almeno una maschera restituisce più di 1.023 elementi, gli elementi più comuni e più grandi hanno maggiori probabilità di essere inclusi nella tabella.

Quando mascherate per Mostra in alto o Almeno uno, per impostazione predefinita l’ordine nella tabella corrisponde ai valori interessati dalla selezione in quel momento. Se in seguito si modifica la selezione, l’ordine non cambia dall’ordine originale a meno che la tabella non venga ordinata o si attivi Selezione dinamica. Quando fai clic su **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**, la tabella viene ordinata ogni volta che modifichi la selezione.

**Per mascherare i dati utilizzando una ricerca**

* Puoi mascherare i dati utilizzando una delle seguenti opzioni di ricerca:

   * Fai clic con il pulsante destro del mouse su un elemento o sull’etichetta della dimensione desiderata, fai clic su **[!UICONTROL Mask]**, quindi digita nella casella [!DNL Search] la frase da cercare.

      ![](assets/mnu_Table_MaskSearch.png)

   * Fai clic con il pulsante destro del mouse su un elemento o sull’etichetta della dimensione desiderata, fai clic su **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]**, quindi digita la frase da cercare nella casella di ricerca che viene visualizzata nella cella dell’etichetta della dimensione.

      ![](assets/vis_Table_Mask_searchBar.png)

      Quando si digita una frase di ricerca, Data Workbench aggiorna la dimensione in modo che rifletta le corrispondenze.

Per vincolare ulteriormente la maschera durante una ricerca, è possibile utilizzare uno dei seguenti metodi:

* È possibile digitare &quot;re:&quot; nella casella o nella barra [!DNL search] per far sì che la frase di ricerca venga interpretata come espressione regolare. Puoi utilizzare una qualsiasi sintassi associata alle espressioni regolari nella frase di ricerca. Per ulteriori informazioni sulle espressioni regolari, vedi l&#39;appendice Espressione regolare nella *Guida alla configurazione del set di dati*.
* È possibile digitare il simbolo $ come primo carattere nella stringa di ricerca per trovare frasi che iniziano con la stringa immessa oppure come ultimo carattere per trovare frasi che terminano con la stringa immessa.
* È possibile digitare uno spazio come primo carattere nella stringa di ricerca per trovare le parole all&#39;interno di una frase che iniziano con la stringa immessa oppure come ultimo carattere per trovare qualsiasi parola all&#39;interno di una frase che termina con la stringa immessa.

Di seguito sono riportati alcuni esempi di modi diversi per mascherare una tabella utilizzando la stringa &quot;on&quot; in una ricerca:

* Digitando &quot;on&quot; vengono visualizzate tutte le frasi contenenti la stringa &quot;on&quot; in qualsiasi punto della frase: &quot;**su** line banking,&quot; &quot;c **su** tact buyer,&quot; &quot;bulli **su** monete,&quot; &quot;banca **su** linea,&quot; &quot;gold opti **su** s,&quot; e &quot;silver bulli **on&lt;a a11/>.&quot;**
* Digitando &quot;$on&quot; viene visualizzata ogni frase che inizia con la stringa &quot;on&quot;:

   &quot;**on** line banking&quot; e &quot;**on**-line payment.&quot;

* Digitando &quot;on$&quot; viene visualizzata ogni frase che termina con la stringa &quot;on&quot;:

   &quot;silver bulli **on**&quot; e &quot;gold opti **on**.&quot;

* Digitando &quot;on&quot; vengono visualizzate tutte le frasi contenenti una parola che inizia con la stringa &quot;on&quot;:

   &quot;**on** line banking&quot; e &quot;bank **on** line.&quot;

* Digitando &quot;on&quot; vengono visualizzate tutte le frasi contenenti una parola che termina con la stringa &quot;on&quot;:

   &quot;bulli **su** monete&quot; e &quot;silver bulli **su**.&quot;

* Utilizzando &quot;on&quot; viene visualizzata ogni frase contenente la stringa &quot;on&quot; come parola:

   &quot;**on** line banking&quot; e &quot;bank **on** line.&quot;
