---
description: Le correlazioni statistiche misurano relazioni significative per identificare le opportunità attraverso l'estrazione avanzata dei dati.
solution: Analytics
title: Matrice di correlazione
topic: Data workbench
uuid: 7f6bdb65-dc31-4e27-9870-4c9402ee6031
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Matrice di correlazione{#correlation-matrix}

Le correlazioni statistiche misurano relazioni significative per identificare le opportunità attraverso l&#39;estrazione avanzata dei dati.

Utilizzando il coefficiente [di correlazione](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c)Pearsons, la Matrice di Correlazione fornisce informazioni pertinenti per identificare meglio i passi successivi in una campagna di marketing, migliorare la progettazione del sito o continuare un&#39;analisi approfondita dei clienti per ulteriori dipendenze di correlazione.

## Creazione di una matrice di correlazione {#section-87ed12ccc1af4196a1b6534e621c4cbb}

La matrice di correlazione confronta le metriche su una dimensione numerabile o non calcolabile. La matrice può quindi essere modificata per evidenziare le correlazioni all’interno della visualizzazione mediante la selezione del colore o per renderla come mappa di testo, mappa di calore o entrambe.

1. Aprite una matrice di correlazione.

   Right-click [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Correlation Matrix]. Viene aperta la tabella delle dimensioni.

   ![](assets/correlation_matrix_2.png)

   Selezionate una dimensione, ad esempio [!DNL Time] > [!DNL Day of the Week] da questo menu. La tabella di correlazione si aprirà con la dimensione identificata nell&#39;angolo della matrice e la metrica associata inserita nella riga e nella colonna. Per la dimensione Giorno della settimana **[!UICONTROL Visits]** è la metrica associata.

   ![](assets/correlation_matrix_1.png)

   La correlazione è 1.000 perché si confronta una metrica con se stessa (che riflette una correlazione perfetta, ma inutilizzabile).

1. Modificare una delle metriche.

   Fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Change Metric]** per modificare una metrica nella riga o nella colonna. Questo imposta una correlazione tra due metriche del valore.

   Per questo esempio, modificate la **[!UICONTROL Visits]** metrica nella colonna in **[!UICONTROL Internal Searches]**. Fate clic con il pulsante destro del mouse e selezionate [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Internal Searches].

   ![](assets/correlation_matrix_change_metric.png)

1. Aggiungete ulteriori metriche alla matrice di correlazione.

   Fai clic con il pulsante destro del mouse in una colonna o riga di metrica. Ad esempio, dal menu Metrica, aggiungere [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Sign in Error].

   ![](assets/correlation_matrix_11.png)

   La nuova metrica verrà visualizzata in una colonna con un numero di correlazione. Puoi aggiungere altre metriche, ad esempio **[!UICONTROL Email Signups]**, per creare la tabella.

   ![](assets/correlation_matrix_6.png)

   Oppure puoi aggiungere metriche alle righe da confrontare con metriche nelle colonne.

   ![](assets/correlation_matrix_add_metric.png)

1. (facoltativo) Vincola una metrica aggiungendo un elemento dimensione.

   Fare clic con il pulsante destro del mouse nell&#39;area di lavoro e selezionare **[!UICONTROL Table]**. Dalla tabella delle quote aperta, premi Ctrl + Alt e trascina l’elemento su una metrica in una colonna o riga. L’elemento verrà visualizzato accanto alla metrica tra parentesi.

   Ad esempio, per la **[!UICONTROL Visits]** metrica, potete vincolarla selezionando la metrica **[!UICONTROL Country]** come **[!UICONTROL New Zealand]**.

   ![](assets/correlation_matrix_dim_element.png)

   Quando si seleziona un elemento dimensione, la correlazione cambia in tutte le metriche in base all&#39;elemento dimensione selezionato. Solo la metrica Visita sarà vincolata per &quot;Nuova Zelanda&quot; una volta chiusa la finestra della dimensione.

   >[!NOTE]
   >
   >Se si modifica una metrica con un vincolo di dimensione (facendo clic con il pulsante destro del mouse e selezionando **[!UICONTROL Change Metric]**), l’elemento dimensione che vincola la metrica andrà perso. Sarà necessario aggiungere nuovamente l&#39;elemento dimensione.

1. Create un filtro [](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-binary-filter.md#concept-24e1daff43c540f69019f236976da31c) binario per limitare ulteriormente la metrica. Fai clic con il pulsante destro del mouse sulla metrica nella tabella e seleziona Filtro binario dal menu.

## Obiettivi di pianificazione e analisi delle correlazioni {#section-cc322da60b7e417ba29e72b0afeb6f79}

Di seguito sono riportati gli obiettivi generali per la creazione di una matrice di correlazione.

**Identificare la relazione tra due metriche rispetto a una dimensione** specificata. Nell&#39;esempio, la matrice è stata creata intorno alla dimensione di base, Giorno della settimana, con le metriche Visita, Registrazioni e-mail ed Errori di accesso confrontate con le ricerche interne, Accesso ed Eventi delle metriche Visualizzate per sondaggio.

**Sviluppare ipotesi per concentrare l&#39;analisi**. Dopo aver eseguito un&#39;analisi di correlazione, il passaggio successivo consiste nel cercare dipendenze e correlazione delle metriche. Ad esempio, se le ricerche interne hanno un effetto sulle registrazioni alle e-mail, è possibile prevedere tale relazione e modificare le campagne di marketing o la progettazione della navigazione nel sito Web.

**Identificare le metriche per includere algoritmi** di data mining più avanzati. Nella maggior parte dei casi, le metriche chiave vengono identificate in quanto influenzano più correlazioni. Ora puoi prendere queste metriche chiave e applicarle ad ulteriori analisi di data mining per approfondimenti più approfonditi.

## Note sulla funzione Matrice di correlazione {#section-ef3626c665ea468a9ecdad624b4132f5}

**Il filtro e la selezione degli elementi dimensionali all&#39;interno di una tabella vengono confrontati come valori**. Ad esempio, se si utilizza la dimensione Giorno della settimana e si fa clic su un elemento della dimensione principale, ad esempio se si fa clic su un giorno specifico nella tabella Dimensioni giorno della settimana, viene visualizzata una corrispondenza al 100% che non fornisce alcuna correlazione utilizzabile. Poiché la dimensione principale era Giorno della settimana, qualsiasi selezione all&#39;interno della tabella dimensione Giorno della settimana modificherà la matrice in modo che sia una correlazione uno-uno.

![](assets/correlation_matrix_10.png)

Tuttavia, la correlazione da 1 a 1 (quando una singola selezione è fatta di tutti gli elementi) è solo in quel giorno specifico. Se si selezionano più selezioni, non viene necessariamente mantenuta una correlazione tra 1 e 1 e non sempre si ottiene una corrispondenza del 100%, indipendentemente dalla selezione di 1 o 1 o più giorni della settimana.

**Le correlazioni statistiche non sono uguali al Modello** dati correlato, il riferimento storico dei prodotti Adobe Analytics. La correlazione statistica nel workbench dati si basa sul modello [](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c)Pearson Correlation.

**Visualizzare la correlazione in un grafico** a dispersione. Fare clic con il pulsante destro del mouse sul titolo di un grafico a dispersione e scegliere [!DNL Display Correlation] dal [!DNL Visualization] menu. Il valore di correlazione viene visualizzato nella sezione in alto a destra della Dispersione.

>[!NOTE]
>
>La matrice Scatter Plot e Pearsons visualizzeranno &quot;Errore di calcolo&quot; se l&#39;applicazione non è in grado di eseguire il calcolo della correlazione Pearsons. In genere questo è dovuto a dati insufficienti, che possono causare il tentativo dell&#39;equazione di dividere per 0.
