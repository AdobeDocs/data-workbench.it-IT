---
description: L’elaborazione dei file di registro come origini di registro richiede la definizione di un decodificatore all’interno del file di inclusione del set di dati di elaborazione del registro per estrarre i campi di dati dalle voci di registro.
title: Gruppi decodificatore del file di testo
uuid: 3ff9700b-4f34-4098-8827-6856897bdb28
exl-id: e9f6e02e-7150-455f-96f0-f34d98cc31b7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 0%

---

# Gruppi decodificatore del file di testo{#text-file-decoder-groups}

L’elaborazione dei file di registro come origini di registro richiede la definizione di un decodificatore all’interno del file di inclusione del set di dati di elaborazione del registro per estrarre i campi di dati dalle voci di registro.

La definizione dei gruppi di decodificatori dei file di testo per le origini dei file di log richiede la conoscenza della struttura e del contenuto del file di log, dei dati da estrarre e dei campi in cui tali dati vengono memorizzati. Questa sezione fornisce descrizioni di base dei parametri che è possibile specificare per i decoder, ma il modo in cui si utilizza un decoder dipende dal file di registro contenente i dati di origine.

Per informazioni sui requisiti di formato per le origini dei file di registro, vedere [File di registro](../../../../../home/c-dataset-const-proc/c-log-proc-config-file/c-log-sources.md#concept-3d4fb817c057447d90f166b1183b461e). Per assistenza sulla definizione dei decodificatori dei file di testo, contatta l’Adobe .

Un gruppo di decodificatori di file di testo può includere:

* [Decoder con espressione regolare](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-67aca2c1f008404da7f845a64abec97c)
* [Decodificatori delimitati](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-text-file-dec-groups.md#section-7e0a23decdbc4c75ae750a42446997a6)

## Decodificatori con espressione regolare {#section-67aca2c1f008404da7f845a64abec97c}

Un decodificatore di espressioni regolari identifica pattern di stringhe complesse all’interno delle voci di registro in un file di registro ed estrae tali pattern come campi di dati. Per ogni decodificatore, il numero di campi deve corrispondere al numero di sottopattern di acquisizione nell’espressione regolare. La parte della linea che corrisponde all’nth subpattern di acquisizione viene assegnata all’nesimo campo per quella linea.

**Per aggiungere un decodificatore di espressioni regolari a un gruppo di decodificatori di file di testo**

1. Apri il file [!DNL Log Processing Dataset Include] come descritto in [Modifica del set di dati esistente Include Files](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) e aggiungi un gruppo di decodificatori di file di testo. Vedere la voce di tabella [Gruppi decoder](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Decoders]** nel gruppo di decodificatori appena creato, quindi fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Regular Expression]**.

1. Specifica le seguenti informazioni:

   * **Campi:** Elenco dei campi nel file di registro. Se uno dei campi qui definiti deve essere passato alla fase di trasformazione della costruzione del set di dati, tali campi devono essere elencati nel parametro Fields di uno dei file [!DNL Log Processing Dataset Include] per il set di dati. I nomi di campo personalizzati devono iniziare con &quot;x-&quot;.

   * **Nome:** identificatore facoltativo per il decodificatore.
   * **Espressione regolare:** consente di estrarre i campi desiderati da ogni riga del file.

1. Ripetere i passaggi 4 e 5 per tutti gli altri decoder che si desidera aggiungere al gruppo.
1. Per salvare il file [!DNL Log Processing Dataset Include], fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

1. Per rendere effettive le modifiche apportate localmente, fai clic con il pulsante destro del mouse sul segno di spunta relativo al file nella colonna [!DNL User]. [!DNL Profile Manager] Fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, dove il nome del profilo è il nome del profilo del set di dati o il profilo ereditato a cui appartiene il file di set di dati.

Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

>[!NOTE]
>
>Un determinato file di registro può avere più decodificatori di espressioni regolari. L’ordine in cui vengono definiti i decodificatori è importante: il primo decodificatore che corrisponde a una riga nel file di registro è quello utilizzato per decodificare tale riga.

Questo esempio illustra l’utilizzo di un decodificatore di espressioni regolari per estrarre campi di dati da un file di testo delimitato da tabulazioni. Puoi ottenere lo stesso risultato definendo un decodificatore delimitato con un delimitatore di tabulazione.

![](assets/cfg_LogProcessingInclude_RegExpDecoder.png)

Per ulteriori informazioni sui decodificatori di espressioni regolari, compresi la terminologia e la sintassi, consulta [Espressioni regolari](../../../../../home/c-dataset-const-proc/c-reg-exp.md#concept-070077baa419475094ef0469e92c5b9c).

## Decodificatori delimitati {#section-7e0a23decdbc4c75ae750a42446997a6}

Un decodificatore delimitato decodifica un file di registro i cui campi sono delimitati da un singolo carattere. Il numero di campi deve corrispondere al numero di colonne nel file delimitato; tuttavia, non è necessario assegnare un nome a tutti i campi. Se un campo viene lasciato vuoto, la colonna è ancora necessaria nel file di registro, ma il decodificatore lo ignora.

**Aggiunta di un decodificatore delimitato a un gruppo di decodificatori di file di testo**

1. Apri il file [!DNL Log Processing Dataset Include] come descritto in [Modifica del set di dati esistente Include Files](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-work-dataset-inc-files/t-edit-ex-dataset-inc-files.md#task-456c04e38ebc425fb35677a6bb6aa077) e aggiungi un gruppo di decodificatori di file di testo. Vedere la voce di tabella [Gruppi decoder](../../../../../home/c-dataset-const-proc/c-dataset-inc-files/c-types-dataset-inc-files/c-log-proc-dataset-inc-files/c-log-proc-dataset-inc-files.md#concept-999475a22519432e98844622ca95b6ab).

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Decoders]** nel gruppo di decodificatori appena creato, quindi fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Delimited]**.

1. Specifica le seguenti informazioni:

   * **Campi:** Elenco dei campi nel file di registro. Se uno dei campi qui definiti deve essere passato alla fase di trasformazione della costruzione del set di dati, tali campi devono essere elencati nel parametro Fields di uno dei file [!DNL Log Processing Dataset Include] per il set di dati. I nomi di campo personalizzati devono iniziare con &quot;x-&quot;.

   * **Delimitatore:** carattere utilizzato per separare i campi nel file di output.

1. Ripetere i passaggi 4 e 5 per tutti gli altri decoder che si desidera aggiungere al gruppo.
1. Per salvare il file [!DNL Log Processing Dataset Include], fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

1. Per rendere effettive le modifiche apportate localmente, fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*, dove nome profilo è il nome del profilo del set di dati o del profilo ereditato a cui appartiene il file del set di dati include.[!DNL Profile Manager]

>[!NOTE]
>
>Non salvare il file di configurazione modificato in nessuno dei profili interni forniti dall’Adobe, in quanto le modifiche vengono sovrascritte quando installi gli aggiornamenti a tali profili.

Questo esempio illustra l’utilizzo di un decodificatore delimitato per estrarre campi di dati da un file di testo delimitato da virgole contenente dati sui filmati.

![](assets/cfg_LogProcessingInclude_DelimitedDecoder.png)
