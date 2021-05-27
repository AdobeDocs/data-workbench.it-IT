---
description: Istruzioni dettagliate per l’installazione di una DPU di Insight Server e la configurazione per uso amministrativo.
title: Procedure di installazione per una DPU di Insight Server
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
exl-id: 0bdfb598-d7eb-4e49-8d9b-4f362c3a62e8
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 8%

---

# Procedure di installazione per una DPU di Insight Server{#installation-procedures-for-an-insight-server-dpu}

Istruzioni dettagliate per l’installazione di una DPU di Insight Server e la configurazione per uso amministrativo.

Per installare e configurare una DPU [!DNL Insight Server], devi completare le seguenti attività nell&#39;ordine seguente:

1. Installa i file di programma [!DNL Insight Server]. Consulta [Installazione dei file del programma Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088).
1. Scarica e installa il certificato digitale [!DNL Insight Server]. Consulta [Download e installazione dei certificati digitali](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Controlla le impostazioni della porta nel file [!DNL Communications.cfg]. Vedere [Controllo delle impostazioni della porta](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).
1. Modifica il file [!DNL Access Control.cfg] per consentire l&#39;accesso amministrativo a [!DNL Insight Server] da [!DNL Insight]. Vedere [Aggiornamento del file di controllo di accesso](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modifica il file [!DNL server.address] per definire il percorso di rete del server. Vedere [Definizione del percorso di rete del server](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. (Facoltativo) Modifica il file [!DNL Disk Files.cfg] per specificare la posizione in cui vengono archiviati i dati elaborati. Consulta [Configurazione della posizione del set di dati (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Installa i profili e i file di ricerca. Consulta [Installazione di profili e file di ricerca](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc).
1. Impostare i parametri di utilizzo della memoria di Microsoft Windows.
1. Registra [!DNL Insight Server] come servizio Windows. Vedere [Registrazione di Insight Server come servizio Windows](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
