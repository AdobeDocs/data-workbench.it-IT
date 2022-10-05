---
description: Istruzioni per installare e configurare una FSU di Insight Server da utilizzare con Repeater (Ripetitore).
title: Configurazione di un FSU di Insight Server per il Repeater (Ripetitore)
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
exl-id: dacbabd5-f6f5-4201-8709-146075eae679
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 5%

---

# Configurazione di un FSU di Insight Server per il Repeater (Ripetitore){#configuring-an-insight-server-fsu-for-repeater}

{{eol}}

Istruzioni per installare e configurare una FSU di Insight Server da utilizzare con Repeater (Ripetitore).

Completa le seguenti attività in ordine. Eventuali eccezioni o modifiche che è necessario apportare affinché il [!DNL Insight Server] FSU può essere utilizzato come server ripetitore sono annotati dopo ogni passaggio.

1. Installa il [!DNL Insight Server] file di programma come descritto in [Installazione di Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   Poiché il computer in cui si installano questi file viene utilizzato per eseguire Repeater, è utile assegnare alla directory di installazione un nome descrittivo come [!DNL D:\Adobe\Repeater].

1. Installa il [!DNL Insight Server] certificato digitale come descritto in [Download e installazione dei certificati digitali](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).

   Dopo aver effettuato l&#39;accesso al server licenze Adobe, ricordare di cercare il nome del certificato che corrisponde al nome comune del server del computer ripetitore designato.

1. Controlla le impostazioni della porta nella [!DNL Communications.cfg] come descritto in [Controllo delle impostazioni della porta](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64).

   Se le porte assegnate (porta e porta SSL) vengono utilizzate da un altro processo in esecuzione sullo stesso computer, è necessario modificare le assegnazioni delle porte in una coppia inutilizzata.

1. Se necessario, modifica la directory di log per [!DNL Sensor] dati da raccogliere e memorizzare su questa macchina. Per istruzioni, consulta [Monitoraggio dello spazio dei dati degli eventi](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440).
1. Modifica la [!DNL Access Control.cfg] file per consentire l&#39;accesso amministrativo a [!DNL Insight Server] da [!DNL Insight] come descritto in [Aggiornamento del file di controllo di accesso](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d).
1. Modifica la [!DNL server.address] per definire il percorso di rete del server come definito in [Definizione del percorso di rete del server](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).
1. Impostare i parametri di utilizzo della memoria di Windows.
1. Registro [!DNL Insight Server] come servizio Windows, come descritto in [Registrazione di Insight Server come servizio Windows](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).
