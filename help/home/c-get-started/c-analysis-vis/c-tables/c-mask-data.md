---
description: Per mascheramento si intende la selezione di un sottoinsieme di dati o di un sottoinsieme di elementi in una dimensione.
solution: Analytics
title: Dati maschera
topic: Data workbench
uuid: 81b5f4e0-826c-4803-9169-66a424a4ea9f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Dati maschera{#mask-data}

Per mascheramento si intende la selezione di un sottoinsieme di dati o di un sottoinsieme di elementi in una dimensione.

Potete mascherare o nascondere gli elementi che non desiderate includere nell’analisi.

Workbench dati offre due metodi per mascherare gli elementi dimensionali. Il primo metodo utilizza le opzioni disponibili nel [!DNL Mask] menu. Utilizzando le opzioni del [!DNL Mask] menu, potete utilizzare il mouse per selezionare gli elementi da mostrare o mascherare, oppure potete mostrare elementi di primo livello quando ordinate i dati per metrica. Il secondo metodo per mascherare gli elementi dimensionali utilizza una ricerca.

**Mascheramento dei dati**

1. Fate clic con il pulsante destro del mouse su un elemento o l’etichetta della dimensione desiderata e fate clic **[!UICONTROL Mask]**.

   ![](assets/mnu_Table_Mask.png)

1. Fai clic su una delle opzioni seguenti:

   * **[!UICONTROL Show all]**
   * **[!UICONTROL Show selected only]**
   * **[!UICONTROL Hide selected]**
   * **[!UICONTROL Show top > 5, 10, 25, 50, 100]** o **[!UICONTROL 500]** degli elementi visualizzati ordinati per metrica
   * **[!UICONTROL Show top > All Positive]** per visualizzare solo valori maggiori di zero (0)
   * **[!UICONTROL Display “X more”]** per visualizzare il numero di elementi attualmente mascherati
   * **[!UICONTROL At least one >]***&lt; **[!UICONTROL countable dimension name]**>*(disponibile solo quando si utilizza una dimensione standard)

      Quando si lavora con una dimensione standard, questa opzione consente di mascherare una dimensione per una dimensione numerabile. Quando è selezionata, la tabella mostra solo gli elementi con almeno un elemento della dimensione numerabile selezionata. La tabella visualizza fino a 1.023 elementi.

>[!NOTE]
>
>Poiché Adobe [!DNL Platform] elabora i dati in ordine casuale, quando almeno una maschera restituisce più di 1.023 elementi, gli elementi più comuni e più grandi hanno maggiori possibilità di essere inclusi nella tabella.

Quando si applica la maschera tramite Mostra superiore o Almeno uno, per impostazione predefinita l&#39;ordine nella tabella corrisponde ai valori interessati dalla selezione in quel momento. Se successivamente si modifica la selezione, l&#39;ordine non cambia dall&#39;ordine originale a meno che la tabella non venga nuovamente ordinata o si attivi la selezione dinamica. Quando si fa clic su **[!UICONTROL Mask]** > **[!UICONTROL Dynamic Selection]**, la tabella viene riordinata ogni volta che si modifica la selezione.

**Mascheramento dei dati con una ricerca**

* È possibile mascherare i dati utilizzando una delle seguenti opzioni di ricerca:

   * Fare clic con il pulsante destro del mouse su un elemento o sull&#39;etichetta della dimensione desiderata, quindi **[!UICONTROL Mask]** digitare nella [!DNL Search] casella la frase per la quale si desidera eseguire la ricerca.

      ![](assets/mnu_Table_MaskSearch.png)

   * Fare clic con il pulsante destro del mouse su un elemento o sull&#39;etichetta della dimensione desiderata, scegliere **[!UICONTROL Mask]** > **[!UICONTROL Display search bar]**, quindi nella casella di ricerca visualizzata nella cella dell&#39;etichetta della dimensione digitare la frase per la quale si desidera eseguire la ricerca.

      ![](assets/vis_Table_Mask_searchBar.png)

      Quando si digita una frase di ricerca, Workbench dati aggiorna la dimensione per riflettere le corrispondenze.

Per limitare ulteriormente la mascheratura durante una ricerca, potete usare uno dei seguenti metodi:

* È possibile digitare &quot;re:&quot; nella [!DNL search] casella o nella barra per far sì che la frase di ricerca venga interpretata come espressione regolare. È possibile utilizzare una qualsiasi sintassi associata alle espressioni regolari nella frase di ricerca. Per ulteriori informazioni sulle espressioni regolari, vedere l&#39;appendice Espressione regolare nella Guida alla configurazione del *set di dati*.
* È possibile digitare il simbolo $ come primo carattere nella stringa di ricerca per trovare frasi che iniziano con la stringa immessa, oppure come ultimo carattere per trovare frasi che terminano con la stringa immessa.
* È possibile digitare uno spazio come primo carattere nella stringa di ricerca per trovare le parole all&#39;interno di una frase che iniziano con la stringa immessa, oppure come ultimo carattere per trovare le parole all&#39;interno di una frase che terminano con la stringa immessa.

Di seguito sono riportati alcuni esempi di modi diversi per mascherare una tabella utilizzando la stringa &quot;on&quot; in una ricerca:

* Digitando &quot;on&quot; vengono visualizzate tutte le frasi che contengono la stringa &quot;on&quot; in qualsiasi punto della frase: &quot;**** online banking&quot;, &quot;**** contattare gli acquirenti,&quot; &quot;**monete da oro** &quot;, &quot;banca **** online&quot;, &quot;**** opzioni d&#39;oro&quot; e &quot;**mongolfiera**&quot;.
* Digitando &quot;$on&quot; vengono visualizzate tutte le frasi che iniziano con la stringa &quot;on&quot;:

   &quot;**** online banking&quot; e &quot;**on**-line payment&quot;.

* Digitando &quot;on$&quot; vengono visualizzate tutte le frasi che terminano con la stringa &quot;on&quot;:

   &quot;**bullone** d&#39;argento&quot; e &quot;**opzione** oro&quot;.

* Digitando &quot;on&quot; vengono visualizzate tutte le frasi contenenti una parola che inizia con la stringa &quot;on&quot;:

   &quot;**** online banking&quot; e &quot;banca **** online&quot;.

* Digitando &quot;on&quot; vengono visualizzate tutte le frasi contenenti una parola che termina con la stringa &quot;on&quot;:

   &quot;**Monete di** oro **&quot; e &quot;** Monete d&#39;argento&quot;.

* L&#39;utilizzo di &quot;on&quot; visualizza ogni frase che contiene la stringa &quot;on&quot; come una parola:

   &quot;**on** line banking&quot; e &quot;bank **on** line&quot;.

