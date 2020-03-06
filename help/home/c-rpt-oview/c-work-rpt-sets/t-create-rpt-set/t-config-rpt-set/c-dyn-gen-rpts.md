---
description: Potete generare rapporti in modo dinamico per gli elementi dimensione specificati in un file di ricerca o per un numero particolare di elementi dimensione, ad esempio per gli utenti con i 10 conteggi di ordine più alti.
solution: Analytics
title: Generazione dinamica di report
topic: Data workbench
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Generazione dinamica di report{#dynamically-generating-reports}

Potete generare rapporti in modo dinamico per gli elementi dimensione specificati in un file di ricerca o per un numero particolare di elementi dimensione, ad esempio per gli utenti con i 10 conteggi di ordine più alti.

>[!NOTE]
>
>Adobe scoraggia la creazione di set di report dinamici per la generazione quotidiana (o più frequente) di report. La generazione di rapporti dinamici può richiedere molte risorse se configuri rapporti con query grandi o complesse.

* [Report elemento dimensione file di ricerca](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [Report elemento dimensione principale](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## Report elemento dimensione file di ricerca {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

Per configurare un set di rapporti per la generazione e (facoltativamente) dinamica di rapporti per gli elementi di una dimensione specificati in un file di ricerca, specificate i seguenti parametri nel [!DNL Report.cfg] file:

* [!DNL Dimension Name]
* [!DNL Lookup File]

Per una descrizione dettagliata di questi parametri, vedete Parametri [](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.

**Creazione di un set di report dinamico tramite un file di ricerca**

1. Create un file di ricerca a due colonne per una determinata dimensione. Questo file deve contenere due colonne delimitate da tabulazioni, senza una riga di intestazione.

   * La colonna 1 deve contenere un elenco di elementi dimensionali.
   * La colonna 2 deve contenere gli indirizzi e-mail dei destinatari del rapporto. Un rapporto per un dato elemento nella colonna 1 viene inviato agli indirizzi e-mail nella stessa riga nella colonna 2. Potete immettere più indirizzi e-mail separandoli con virgole (senza spazi).

      >[!NOTE]
      >
      >
      >    
      >    
      >    * Se i rapporti non devono essere inviati via e-mail, la colonna 2 può essere vuota ma deve esistere.
      >    * Questo file può contenere righe vuote.




1. Facoltativo. Per abilitare l&#39;invio tramite e-mail di rapporti, nella [!DNL Mail Report] sezione del [!DNL Report.cfg] file devi effettuare le seguenti operazioni:

   * Nel parametro Server SMTP, elencare il server SMTP appropriato da utilizzare per distribuire i report tramite e-mail.
   * Nel parametro Destinatari, elencare almeno un indirizzo e-mail per abilitare la distribuzione dei rapporti tramite e-mail. I rapporti non vengono inviati all&#39;indirizzo indicato; questo parametro viene impostato solo per consentire l&#39;invio tramite e-mail dei rapporti. Può trattarsi di un indirizzo falso, ma deve essere in un formato consentito (ad esempio, [!DNL jsmith@company.com]).

1. Salvate il file di ricerca nella cartella del set di rapporti.
1. Aprite il [!DNL Report.cfg] file per il set di report.
1. Nel parametro Nome dimensione, digitate il nome della dimensione per la quale desiderate generare in modo dinamico un rapporto.
1. Nel parametro File di ricerca, digitare la posizione e il nome del file di ricerca contenente gli elementi dimensionali desiderati nel rapporto e gli indirizzi e-mail del destinatario.
1. Ripetete questi passaggi per altri set di report.

>[!NOTE]
>
>I report dinamici non vengono inviati via e-mail ai destinatari fino al completamento dell&#39;intero set di report.

## Report elemento dimensione principale {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

Per configurare un set di report in modo da generare in modo dinamico report per gli elementi di dimensione principale, contando per la metrica specificata, specificate nel [!DNL Report.cfg] file i seguenti parametri:

* Nome dimensione
* Metrica N superiore
* Valore N superiore
* (Facoltativo) Filtro query di precaricamento

Per una descrizione dettagliata di questi parametri, vedete Parametri [](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff)Report.cfg.

**Creazione di un set di rapporti dinamico per gli elementi principali**

1. Aprite il [!DNL Report.cfg] file del set di rapporti.
1. Nel parametro Nome dimensione, digitate il nome della dimensione per la quale desiderate generare in modo dinamico un set di rapporti.
1. Nel parametro Metrica N superiore, digitate il nome della metrica per la quale desiderate ordinare la dimensione.
1. Nel parametro Top N Value digitare il numero di elementi dimensionali desiderati nel set di report.
1. (Facoltativo) Nel parametro Filtro query di precaricamento, digitate il nome del filtro desiderato.
1. Ripetete questi passaggi per altri set di report.
1. Per informazioni sull’utilizzo di una visualizzazione titolo dinamica con il rapporto, vedere la Guida *utente di Workbench* dati.

