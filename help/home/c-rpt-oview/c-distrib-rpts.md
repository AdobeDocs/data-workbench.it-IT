---
description: Dopo la generazione dei rapporti, Report distribuisce i rapporti nel set in base alle impostazioni nel relativo file Report.cfg.
title: Distribuzione di rapporti
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# Distribuzione di rapporti{#distributing-reports}

{{eol}}

Dopo la generazione dei rapporti, Report distribuisce i rapporti nel set in base alle impostazioni nel relativo file Report.cfg.

[!DNL Report] consente di distribuire i rapporti in un set utilizzando i seguenti metodi:

* **E-mail:** Per distribuire i rapporti come file Excel, [!DNL .png] file o miniature tramite e-mail (in linea o come allegati), specifica i parametri del rapporto e-mail nel set di rapporti [!DNL Report.cfg] file. Tutti i rapporti in quel set vengono inviati tramite e-mail in un messaggio ai destinatari specificati.

* **Directory condivisa:** Per distribuire i rapporti come file Excel, [!DNL .png] file o miniature di una directory condivisa, specifica la directory nel parametro Output Root nel set di rapporti [!DNL Report.cfg] file.

* **Portale di reporting:** Un portale di reporting consente di visualizzare i rapporti tramite il browser Web. dell’Adobe [!DNL Report Portal] visualizza i rapporti generati come Excel o [!DNL .png] , ma non quelli generati come miniature ( [!DNL .jpg]). Per distribuire i rapporti in un portale, specifica la directory principale dei documenti del server Web utilizzato per il portale nel parametro Output Root nel set di rapporti [!DNL Report.cfg] file. Per ulteriori informazioni sull’installazione e l’utilizzo [!DNL Report Portal], vedi [Utilizzo del Report Portal (Portale dei rapporti)](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Per leggere l&#39;output attualmente supportato da [!DNL Report], devi disporre di un’applicazione in grado di visualizzare i rapporti nel formato o nei formati desiderati. Ad esempio, per visualizzare [!DNL .xlsx] file, è necessario disporre di Microsoft Excel 2007 o versione successiva.

È inoltre possibile utilizzare una combinazione di queste opzioni di generazione e distribuzione. Ad esempio, se imposti la [!DNL Report Types] per generare un set di rapporti come Excel e [!DNL .png] e quindi impostare il [!DNL Mail Report]e [!DNL Output Root] , tutti i report in quel set vengono distribuiti nella directory di output specificata (probabilmente da visualizzare in un portale) ed inviati tramite e-mail ai destinatari.

Per i passaggi per configurare i set di rapporti, vedi [Utilizzo dei set di rapporti](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). Per ulteriori informazioni sulle specifiche [!DNL Report.cfg] parametri, vedi [Parametri Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
