---
description: Puoi generare rapporti in modo dinamico per gli elementi dimensionali specificati in un file di ricerca o per un numero particolare di elementi dimensionali, ad esempio per gli utenti con i 10 conteggi d’ordine più elevati.
title: Generazione dinamica di rapporti
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
exl-id: c14d93cd-212d-44a1-aff9-652e5c4fbda0
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 1%

---

# Generazione dinamica di rapporti{#dynamically-generating-reports}

Puoi generare rapporti in modo dinamico per gli elementi dimensionali specificati in un file di ricerca o per un numero particolare di elementi dimensionali, ad esempio per gli utenti con i 10 conteggi d’ordine più elevati.

>[!NOTE]
>
>L’Adobe scoraggia la creazione di set di rapporti dinamici per la generazione di rapporti giornalieri (o più frequenti). La generazione di rapporti dinamici può richiedere molte risorse se configuri rapporti con query di grandi dimensioni o complesse.

* [Rapporti sugli elementi del Dimension di file di ricerca](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [Report principali sugli elementi del Dimension](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## Rapporti sugli elementi dei Dimension di ricerca {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

Per configurare un set di rapporti per la generazione e (facoltativamente) la distribuzione dinamica di rapporti per gli elementi di una dimensione specificata in un file di ricerca, specifica i seguenti parametri nel file [!DNL Report.cfg] :

* [!DNL Dimension Name]
* [!DNL Lookup File]

Per una descrizione dettagliata di questi parametri, consulta [Parametri Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**Per creare un set di rapporti dinamico utilizzando un file di ricerca**

1. Crea un file di ricerca a due colonne per una determinata dimensione. Questo file deve contenere due colonne delimitate da tabulazioni, senza una riga di intestazione.

   * La colonna 1 deve contenere un elenco di elementi dimensionali.
   * La colonna 2 deve contenere gli indirizzi e-mail dei destinatari del rapporto. Un rapporto per un dato elemento nella colonna 1 viene inviato agli indirizzi e-mail nella stessa riga nella colonna 2. Puoi immettere più indirizzi e-mail separandoli con virgole (senza spazi).

      >[!NOTE]
      >
      >
      >    
      >    
      >    * Se i rapporti non devono essere inviati via e-mail, la colonna 2 può essere vuota ma deve esistere.
      >    * Questo file può contenere righe vuote.




1. Facoltativo. Per abilitare l’invio di rapporti per l’e-mail, è necessario effettuare le seguenti operazioni nella sezione [!DNL Mail Report] del file [!DNL Report.cfg] per quel particolare set di rapporti:

   * Nel parametro del server SMTP, elencare il server SMTP appropriato da utilizzare per distribuire i rapporti tramite e-mail.
   * Nel parametro Recipients (Destinatari), elencare almeno un indirizzo e-mail per consentire la distribuzione dei rapporti tramite e-mail. I rapporti non vengono inviati all&#39;indirizzo indicato, è necessario impostare questo parametro solo per consentire l&#39;invio di messaggi e-mail. Può essere un indirizzo falso, ma deve essere in un formato consentito (ad esempio, [!DNL jsmith@company.com]).

1. Salva il file di ricerca nella cartella del set di rapporti.
1. Apri il file [!DNL Report.cfg] del set di rapporti.
1. Nel parametro Nome Dimension digitare il nome della dimensione per la quale si desidera generare in modo dinamico un rapporto.
1. Nel parametro File di ricerca digitare la posizione e il nome del file di ricerca contenente gli elementi dimensionali desiderati nel rapporto e gli indirizzi e-mail dei destinatari.
1. Ripeti questi passaggi per ulteriori set di rapporti.

>[!NOTE]
>
>I rapporti dinamici non vengono inviati via e-mail ai destinatari fino al completamento dell’intero set di rapporti.

## Rapporti principali sugli elementi del Dimension {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

Per configurare un set di rapporti per la generazione dinamica di rapporti per gli elementi dimensionali principali, conteggiando per la metrica specificata, specifica i seguenti parametri nel file [!DNL Report.cfg] :

* Nome dimensione
* Metrica N principale
* Valore N superiore
* (Facoltativo) Filtro query di precaricamento

Per una descrizione dettagliata di questi parametri, consulta [Parametri Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**Creazione di un set di rapporti dinamico per gli elementi principali**

1. Apri il file [!DNL Report.cfg] del set di rapporti.
1. Nel parametro Nome Dimension digitare il nome della dimensione per la quale si desidera generare in modo dinamico un set di rapporti.
1. Nel parametro della metrica Top N , digita il nome della metrica in base alla quale desideri ordinare la dimensione.
1. Nel parametro Top N Value digitare il numero di elementi dimensionali desiderati nel set di rapporti.
1. (Facoltativo) Nel parametro Filtro query di precaricamento, digita il nome del filtro desiderato.
1. Ripeti questi passaggi per ulteriori set di rapporti.
1. Per informazioni sull&#39;utilizzo di una visualizzazione titolo dinamica con il rapporto, vedere la *Guida utente Data Workbench*.
