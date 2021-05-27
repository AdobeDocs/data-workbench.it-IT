---
description: Dopo la generazione dei rapporti, Report distribuisce i rapporti nel set in base alle impostazioni nel relativo file Report.cfg.
title: Distribuzione di rapporti
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
exl-id: ead1d8ef-7319-4307-9155-0101a9c1959d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 1%

---

# Distribuzione di rapporti{#distributing-reports}

Dopo la generazione dei rapporti, Report distribuisce i rapporti nel set in base alle impostazioni nel relativo file Report.cfg.

[!DNL Report] consente di distribuire i rapporti in un set utilizzando i seguenti metodi:

* **E-mail:** per distribuire i rapporti come file Excel,  [!DNL .png] file o miniature tramite e-mail (in linea o come allegati), specifica i parametri del rapporto e-mail nel  [!DNL Report.cfg] file del set di rapporti. Tutti i rapporti in quel set vengono inviati tramite e-mail in un messaggio ai destinatari specificati.

* **Directory condivisa:** per distribuire i rapporti come file Excel,  [!DNL .png] file o miniature in una directory condivisa, specifica la directory nel parametro Directory principale di output nel  [!DNL Report.cfg] file del set di rapporti.

* **Portale dei rapporti:** un portale dei rapporti consente di visualizzare i rapporti tramite il browser web. I rapporti di Adobe [!DNL Report Portal] vengono visualizzati come file Excel o [!DNL .png], ma non come miniature ( [!DNL .jpg]). Per distribuire i rapporti in un portale, specifica la directory principale dei documenti del server Web utilizzato per il portale nel parametro Output Root nel file [!DNL Report.cfg] del set di rapporti. Per ulteriori informazioni sull&#39;installazione e l&#39;utilizzo di [!DNL Report Portal], vedere [Utilizzo del Report Portal (Portale dei rapporti)](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35).

>[!NOTE]
>
>Per leggere l&#39;output attualmente supportato da [!DNL Report], è necessario disporre di un&#39;applicazione in grado di visualizzare i report nel formato desiderato. Ad esempio, per visualizzare i file [!DNL .xlsx], è necessario disporre di Microsoft Excel 2007 o versione successiva.

È inoltre possibile utilizzare una combinazione di queste opzioni di generazione e distribuzione. Ad esempio, se imposti il parametro [!DNL Report Types] per generare un set di rapporti come file Excel e [!DNL .png] e quindi imposti i parametri [!DNL Mail Report]e [!DNL Output Root], tutti i rapporti in quel set vengono distribuiti nella directory di output specificata (probabilmente da visualizzare in un portale) ed inviati tramite e-mail ai destinatari in un unico messaggio.

Per i passaggi per configurare i set di rapporti, consulta [Utilizzo dei set di rapporti](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5). Per ulteriori informazioni sui parametri [!DNL Report.cfg] specifici, consulta [Parametri Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
