---
description: Dopo la generazione dei rapporti, Report distribuisce i rapporti nel set in base alle impostazioni nel relativo file Report.cfg.
solution: Analytics
title: Distribuzione di report
topic: Data workbench
uuid: 0e993635-1aa8-4314-91aa-b4f8f002fa09
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Distribuzione di report{#distributing-reports}

Dopo la generazione dei rapporti, Report distribuisce i rapporti nel set in base alle impostazioni nel relativo file Report.cfg.

[!DNL Report] consente di distribuire i rapporti in un set utilizzando i seguenti metodi:

* **E-mail:** Per distribuire i rapporti come file Excel [!DNL .png] o miniature tramite e-mail (in linea o come allegati), specificate i parametri Report e-mail nel [!DNL Report.cfg] file del set di rapporti. Tutti i rapporti in quel set vengono inviati tramite e-mail in un messaggio ai destinatari specificati.

* **Directory condivisa:** Per distribuire i rapporti come file, [!DNL .png] file o miniature di Excel in una directory condivisa, specificate la directory nel parametro Output Root nel [!DNL Report.cfg] file del set di rapporti.

* **Portale di reporting:** Un portale di reporting consente di visualizzare i rapporti tramite il browser Web. Adobe [!DNL Report Portal] visualizza i rapporti generati come file Excel o [!DNL .png] ma non come miniature ( [!DNL .jpg]). Per distribuire i rapporti a un portale, specificate la radice del documento del server Web utilizzato per il portale nel parametro Output Root del [!DNL Report.cfg] file del set di rapporti. Per ulteriori informazioni sull&#39;installazione e l&#39;utilizzo [!DNL Report Portal], consultate [Utilizzo del portale](../../home/c-rpt-oview/c-rpt-portal/c-rpt-portal.md#concept-f692210cad494c00865dbf325eb5ed35)dei report.

>[!NOTE]
>
>Per leggere l&#39;output attualmente supportato da [!DNL Report], è necessario disporre di un&#39;applicazione in grado di visualizzare i rapporti nei formati desiderati. Ad esempio, per visualizzare [!DNL .xlsx] i file è necessario disporre di Microsoft Excel 2007 o versione successiva.

È inoltre possibile utilizzare una combinazione di queste opzioni di generazione e distribuzione. Ad esempio, se imposti il [!DNL Report Types] parametro per generare un set di rapporti come Excel e [!DNL .png] file e quindi imposti i parametri [!DNL Mail Report]e [!DNL Output Root] , tutti i rapporti in quel set vengono distribuiti alla directory di output specificata (forse da visualizzare in un portale) e inviati via e-mail ai destinatari tramite e-mail.

Per i passaggi necessari per configurare i set di rapporti, consulta [Utilizzo dei set](../../home/c-rpt-oview/c-work-rpt-sets/c-work-rpt-sets.md#concept-a5f078668e1245e684cb2a778c8803d5)di rapporti. Per ulteriori informazioni sui [!DNL Report.cfg] parametri specifici, vedi Parametri [Report.cfg](../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).
