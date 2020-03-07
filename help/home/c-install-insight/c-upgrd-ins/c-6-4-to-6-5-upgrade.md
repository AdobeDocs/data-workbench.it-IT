---
description: Effettuare l'aggiornamento a Workbench dati v6.5.
title: Aggiornamento da 6.4 a 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Upgrading 6.4 to 6.5{#upgrading-to}

Effettuare l&#39;aggiornamento a Workbench dati v6.5.

## Requisiti e raccomandazioni per l&#39;aggiornamento {#section-8704a9ac358246cd81233dd0982d534f}

Per effettuare l&#39;aggiornamento a Workbench dati 6.5, attenersi ai seguenti requisiti e consigli.

* Le modifiche nel **[!DNL Components for Processing Servers\Communications.cfg]** file richiedono l’aggiornamento di questo file per la release DWB 6.5. Le voci *SourceListServer*, *SegmentExportServer* e *NormalizeServer* sono state rimosse. (DPU non deve eseguire server *sourcelist*, di esportazione *di* segmenti o di *normalizzazione*. )

* Le visualizzazioni Correlazione, Matrice di correlazione, Accordo di associazione, Matrice di associazione, Punteggio tendenza e Attribuzione adattamento ottimale sono ora visualizzazioni a più passaggi.

   Se in un’area di lavoro sono presenti più visualizzazioni passate multiple, per impostazione predefinita il server di report non genera i report con l’errore:

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   Evitate questo errore aggiornando il [!DNL ReportServer.cfg] file o aggiungendo questa riga al file esistente nella sezione *Reporting* .

   ```
   Max Multipass Per Slice = int: n
   ```

   dove n è il numero massimo di visualizzazioni con più passaggi supportate dal server di report in un&#39;area di lavoro.

