---
description: Segui questi passaggi per eseguire l’aggiornamento a Data Workbench v6.5.
title: Aggiornamento da 6.4 a 6.5
uuid: b90b7b0c-7467-405f-a5ca-c40e69975d49
exl-id: bcfd1ab1-2fb8-4bcd-b6c9-329143274ca4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 2%

---

# Aggiornamento da 6.4 a 6.5{#upgrading-to}

{{eol}}

Segui questi passaggi per eseguire l’aggiornamento a Data Workbench v6.5.

## Requisiti di aggiornamento e Recommendations {#section-8704a9ac358246cd81233dd0982d534f}

Segui questi requisiti e consigli durante l’aggiornamento alla Data Workbench 6.5.

* Modifiche nel **[!DNL Components for Processing Servers\Communications.cfg]** è necessario aggiornare questo file per la versione DWB 6.5. La *SourceListServer*, *SegmentExportServer* e *NormalizeServer* le voci sono state rimosse. ( Le DPU non devono essere in esecuzione *secolare*, *esportazione di segmenti* oppure *normalizzazione dei server*. )

* Le visualizzazioni Correlazione Chord (Corda correlazione), Matrice di correlazione, Accordi associazione, Matrice di associazione, Punteggio tendenza e Attribuzione adattamento ottimale sono ora visualizzazioni a più passaggi.

   Se in un’area di lavoro sono presenti più visualizzazioni con più passaggi, per impostazione predefinita il server di rapporto non genera rapporti con l’errore:

   ```
   Too many Multipass visualizations in workspace ....... (has #, 1 allowed).
   ```

   Evita questo errore aggiornando il tuo [!DNL ReportServer.cfg] o aggiungi questa riga al file esistente nel *Reporting* sezione .

   ```
   Max Multipass Per Slice = int: n
   ```

   dove n è il numero massimo di visualizzazioni con più passaggi supportate dal server di rapporto in un’area di lavoro.
