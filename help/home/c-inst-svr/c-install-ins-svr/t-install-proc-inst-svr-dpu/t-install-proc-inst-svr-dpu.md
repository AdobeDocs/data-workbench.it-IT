---
description: Istruzioni dettagliate per l’installazione di un DPU di Insight Server e la configurazione per uso amministrativo.
solution: Insight
title: Procedure di installazione per una DPU di Insight Server
uuid: 4a04d333-3264-4c15-87fd-8fd201eb68fc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Procedure di installazione per una DPU di Insight Server{#installation-procedures-for-an-insight-server-dpu}

Istruzioni dettagliate per l’installazione di un DPU di Insight Server e la configurazione per uso amministrativo.

Per installare e configurare un [!DNL Insight Server] DPU, devi completare le seguenti attività per:

1. Installate i file del [!DNL Insight Server] programma. Consultate [Installazione dei file](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-install-prgm-files.md#task-1e6251fd39714186baa40d38f23d0088)del programma Insight Server.
1. Scaricate e installate il certificato [!DNL Insight Server] digitale. Vedere [Download e installazione dei certificati](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)digitali.
1. Controllare le impostazioni della porta nel [!DNL Communications.cfg] file. Consultate [Controllo delle impostazioni](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)della porta.
1. Modificate il [!DNL Access Control.cfg] file per consentire l&#39;accesso amministrativo a [!DNL Insight Server] da [!DNL Insight]. Vedere [Aggiornamento del file](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)di controllo di accesso.
1. Modificare il [!DNL server.address] file per definire il percorso di rete del server. Vedere [Definizione del percorso](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)di rete del server.
1. (Facoltativo) Modificare il [!DNL Disk Files.cfg] file per specificare la posizione di memorizzazione dei dati elaborati. Consultate [Configurazione della posizione del set di dati (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).
1. Installate i profili e i file di ricerca. Consultate [Installazione di profili e file](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-install-prof-lkup-files.md#concept-1631895d09a14dc99316bf8cf166fdfc)di ricerca.
1. Impostare i parametri di utilizzo della memoria di Microsoft Windows.
1. Registrati [!DNL Insight Server] come servizio Windows. Vedere [Registrazione di Insight Server come servizio](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)Windows.
