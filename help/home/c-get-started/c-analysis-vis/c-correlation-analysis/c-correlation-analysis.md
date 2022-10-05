---
description: Le correlazioni statistiche misurano relazioni significative per identificare le opportunità attraverso l'estrazione avanzata dei dati.
title: Matrice di correlazione
uuid: 7f6bdb65-dc31-4e27-9870-4c9402ee6031
exl-id: 79c23bb9-2b4b-4fe0-bfdb-52721fbbdf0c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 0%

---

# Matrice di correlazione{#correlation-matrix}

{{eol}}

Le correlazioni statistiche misurano relazioni significative per identificare le opportunità attraverso l&#39;estrazione avanzata dei dati.

Impiego di [Coefficiente di correlazione dei Pearson](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c), la matrice di correlazione fornisce informazioni rilevanti per identificare meglio i passaggi successivi in una campagna di marketing, per migliorare la progettazione del sito o per continuare un’analisi approfondita del cliente per ulteriori dipendenze di correlazione.

## Creazione di una matrice di correlazione {#section-87ed12ccc1af4196a1b6534e621c4cbb}

La matrice di correlazione confronta le metriche su una dimensione conteggiata o non numerabile. La matrice può quindi essere modificata per evidenziare le correlazioni all’interno della visualizzazione tramite la selezione del colore o per renderla come mappa di testo, mappa di calore o entrambe.

1. Apri una matrice di correlazione.

   Fai clic con il pulsante destro del mouse [!DNL Visualization] > [!DNL Predictive Analytics] > [!DNL Correlation Matrix]. Viene aperta la tabella delle dimensioni.

   ![](assets/correlation_matrix_2.png)

   Seleziona una dimensione, ad esempio [!DNL Time] > [!DNL Day of the Week] da questo menu. La tabella di correlazione si aprirà con la dimensione identificata nell’angolo della matrice e la metrica associata posizionata nella riga e nella colonna. Per la dimensione Giorno della settimana, **[!UICONTROL Visits]** è la metrica associata.

   ![](assets/correlation_matrix_1.png)

   La correlazione è di 1.000 perché si confronta una metrica con se stessa (che riflette una correlazione perfetta, ma inutilizzabile).

1. Modificare una delle metriche.

   Fai clic con il pulsante destro del mouse e seleziona **[!UICONTROL Change Metric]** per modificare una metrica nella riga o nella colonna. Questo imposta una correlazione tra due metriche di valore.

   Per questo esempio, modifica la variabile **[!UICONTROL Visits]** nella colonna a **[!UICONTROL Internal Searches]**. Fai clic con il pulsante destro del mouse e seleziona [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Internal Searches].

   ![](assets/correlation_matrix_change_metric.png)

1. Aggiungi più metriche alla matrice di correlazione.

   Fai clic con il pulsante destro del mouse su una colonna o una riga di metrica. Ad esempio, dal menu Metrica , aggiungi [!DNL Metric] > [!DNL Custom Events] > [!DNL Custom Event 1-10] > [!DNL Sign in Error].

   ![](assets/correlation_matrix_11.png)

   La nuova metrica verrà visualizzata in una colonna con un numero di correlazione. Puoi aggiungere altre metriche, come **[!UICONTROL Email Signups]**, per creare la tabella.

   ![](assets/correlation_matrix_6.png)

   Oppure aggiungi metriche alle righe da confrontare con metriche nelle colonne.

   ![](assets/correlation_matrix_add_metric.png)

1. (facoltativo) Vincola una metrica aggiungendo un elemento dimensione.

   Fai clic con il pulsante destro del mouse nell’area di lavoro e seleziona **[!UICONTROL Table]**. Dalla tabella delle dimensioni aperte, premi Ctrl + Alt e trascina l’elemento su una metrica in una colonna o in una riga. L’elemento verrà visualizzato accanto alla metrica tra parentesi.

   Ad esempio, per **[!UICONTROL Visits]** è possibile vincolarla selezionando la **[!UICONTROL Country]** come **[!UICONTROL New Zealand]**.

   ![](assets/correlation_matrix_dim_element.png)

   Quando selezioni un elemento dimensione, la correlazione cambia in tutte le metriche in base all’elemento dimensione selezionato. Solo la metrica Visita sarà vincolata per &quot;Nuova Zelanda&quot; una volta chiusa la finestra della dimensione.

   >[!NOTE]
   >
   >Se modifichi una metrica con un vincolo di dimensione (facendo clic con il pulsante destro del mouse e selezionando **[!UICONTROL Change Metric]**), l’elemento dimensionale che vincola la metrica viene perso. Dovrai aggiungere nuovamente l’elemento dimensionale.

1. Crea un [Filtro binario](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-binary-filter.md#concept-24e1daff43c540f69019f236976da31c) per vincolare ulteriormente la metrica. Fai clic con il pulsante destro del mouse sulla metrica nella tabella e seleziona Filtro binario dal menu .

## Obiettivi di pianificazione e analisi della correlazione {#section-cc322da60b7e417ba29e72b0afeb6f79}

Di seguito sono riportati gli obiettivi generali per la creazione di una matrice di correlazione.

**Identificare la relazione tra due metriche rispetto a una dimensione specificata**. Nell’esempio, la matrice è stata creata intorno alla dimensione di base, Giorno della settimana, con le metriche Visita, Registri e-mail ed Errori di accesso rispetto agli eventi delle metriche Ricerche interne, Accesso e Sondaggio visualizzati.

**Sviluppare ipotesi per concentrare l&#39;analisi**. Dopo aver eseguito un’analisi di correlazione, il passaggio successivo consiste nel cercare le dipendenze e la correlazione delle metriche. Ad esempio, comprendere che le ricerche interne hanno un effetto sulle iscrizioni alle e-mail fornisce un percorso per prevedere tale relazione e modificare le campagne di marketing o il progetto di navigazione del sito web.

**Identificare le metriche per includere algoritmi di data mining più avanzati**. Nella maggior parte dei casi, le metriche chiave vengono identificate in quanto influiscono su più correlazioni. Ora puoi prendere queste metriche chiave e applicarle ad analisi aggiuntive di data mining per ottenere informazioni più approfondite.

## Note sulla funzione della matrice di correlazione {#section-ef3626c665ea468a9ecdad624b4132f5}

**L’applicazione di filtri e la selezione degli elementi dimensionali all’interno di una tabella vengono confrontati come valori**. Ad esempio, utilizzando la dimensione Giorno della settimana e facendo clic su un elemento della dimensione core, ad esempio facendo clic su un giorno specifico nella tabella delle dimensioni Giorno della settimana, viene eseguito il rendering di una corrispondenza al 100% che non fornisce correlazione utilizzabile. Poiché la dimensione principale era Giorno della settimana, qualsiasi selezione all’interno della tabella della dimensione Giorno della settimana modificherà la matrice in modo che sia una correlazione uno-a-uno.

![](assets/correlation_matrix_10.png)

Tuttavia, la correlazione da 1 a 1 (quando una singola selezione è fatta di tutti gli elementi) è solo in quel giorno specifico. Se effettui selezioni multiple, non necessariamente rimane una correlazione da 1 a 1 e non sempre darà una corrispondenza del 100% indipendentemente dalla selezione di 1 o 1+ giorni della settimana.

**Le correlazioni statistiche non sono uguali al Modello dati correlato**, il riferimento storico dei prodotti Adobe Analytics. La correlazione statistica all’interno di Data Workbench è basata su [Modello di correlazione Pearson](../../../../home/c-get-started/c-analysis-vis/c-correlation-analysis/c-correlation-pearsons.md#concept-5996cb8c89fd4df5b47b7318e7a1d29c).

**Visualizza correlazione in un grafico a dispersione**. Fai clic con il pulsante destro del mouse sul titolo di un grafico a dispersione e scegli [!DNL Display Correlation] dal [!DNL Visualization] menu. Il valore Correlazione viene visualizzato nella sezione in alto a destra del grafico a dispersione.

>[!NOTE]
>
>La matrice Scatter Plot e Pearsons visualizza &quot;Errore di calcolo&quot; se l&#39;applicazione non è in grado di eseguire il calcolo della correlazione Pearsons. Questo è solitamente dovuto a dati insufficienti, il che può causare il tentativo di divisione dell&#39;equazione per 0.
