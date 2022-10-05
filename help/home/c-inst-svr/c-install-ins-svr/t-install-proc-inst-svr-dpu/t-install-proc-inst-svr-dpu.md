---
description: Istruzioni dettagliate per l’installazione di una DPU di Insight Server e la configurazione per uso amministrativo.
title: Procedure di installazione per una DPU di Insight Server
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
exl-id: 0bdfb598-d7eb-4e49-8d9b-4f362c3a62e8
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---

# Procedure di installazione per una DPU di Insight Server{#installation-procedures-for-an-insight-server-dpu}

{{eol}}

Istruzioni dettagliate per l’installazione di una DPU di Insight Server e la configurazione per uso amministrativo.

Per installare e configurare un [!DNL Insight Server] DPU, devi completare le seguenti attività in ordine:

1. Installa il [!DNL Insight Server] file di programma. Vedi [Installazione dei file del programma Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088).
1. Scarica e installa la [!DNL Insight Server] certificato digitale. Vedi [Download e installazione dei certificati digitali](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Controlla le impostazioni della porta nella [!DNL Communications.cfg] file. Vedi [Controllo delle impostazioni della porta](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).
1. Modifica la [!DNL Access Control.cfg] file per consentire l&#39;accesso amministrativo a [!DNL Insight Server] da [!DNL Insight]. Vedi [Aggiornamento del file di controllo di accesso](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modifica la [!DNL server.address] per definire il percorso di rete del server. Vedi [Definizione del percorso di rete del server](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. (Facoltativo) Modifica il [!DNL Disk Files.cfg] file per specificare la posizione di memorizzazione dei dati elaborati. Vedi [Configurazione della posizione del set di dati (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Installa i profili e i file di ricerca. Vedi [Installazione di profili e file di ricerca](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc).
1. Impostare i parametri di utilizzo della memoria di Microsoft Windows.
1. Registro [!DNL Insight Server] come servizio Windows. Vedi [Registrazione di Insight Server come servizio Windows](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
