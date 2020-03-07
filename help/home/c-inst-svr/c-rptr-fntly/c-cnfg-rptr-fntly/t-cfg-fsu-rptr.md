---
description: Istruzioni per l'installazione e la configurazione di un'unità FSU di Insight Server da utilizzare con Ripetitore.
solution: Insight
title: Configurazione di un FSU di Insight Server per il Ripetitore
uuid: c2bae862-37d3-4841-b31b-59593c1e4316
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurazione di un FSU di Insight Server per il Ripetitore{#configuring-an-insight-server-fsu-for-repeater}

Istruzioni per l&#39;installazione e la configurazione di un&#39;unità FSU di Insight Server da utilizzare con Ripetitore.

Completa i seguenti task in ordine. Eventuali eccezioni o modifiche da apportare affinché l&#39; [!DNL Insight Server] FSU possa essere utilizzato come server di ripetizione vengono annotate dopo ogni passaggio.

1. Installate i file del [!DNL Insight Server] programma come descritto in [Installazione di Insight Server](../../../../home/c-inst-svr/c-install-ins-svr/c-install-ins-svr.md#concept-1c796b4ca427474f99ec6ba34d8254cd).

   Poiché il computer in cui installate questi file viene utilizzato per eseguire Ripetitore, è utile assegnare alla directory di installazione un nome descrittivo come [!DNL D:\Adobe\Repeater].

1. Installate il certificato [!DNL Insight Server] digitale come descritto in [Download e installazione dei certificati](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)digitali.

   Dopo aver eseguito l&#39;accesso ad Adobe License Server, ricordare di cercare il nome del certificato che corrisponde al nome comune del server del computer ripetitore designato.

1. Controllate le impostazioni della porta nel [!DNL Communications.cfg] file come descritto in [Controllo delle impostazioni](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-chk-pt-stgs.md#task-a91191b0a19e4437aa535a27c734ae64)della porta.

   Se le porte assegnate (Porta e Porta SSL) sono utilizzate da un altro processo in esecuzione sullo stesso computer, è necessario modificare le assegnazioni delle porte in una coppia non utilizzata.

1. Se necessario, modificare la directory di registro per i [!DNL Sensor] dati da raccogliere e memorizzare in questo computer. Per istruzioni, vedere [Monitoraggio dello spazio](../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-evt-data-spc.md#task-a54d4bd16b96437f943cd09e5d848440)dati evento.
1. Modificare il [!DNL Access Control.cfg] file per consentire l&#39;accesso amministrativo [!DNL Insight Server] da [!DNL Insight] come descritto in [Aggiornamento del file](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-updt-accss-ctrl-file.md#concept-fb9aa0c0e0664c018528f56d01c4808d)di controllo di accesso.
1. Modificate il [!DNL server.address] file per definire il percorso di rete del server, come definito in [Definizione del percorso](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)di rete del server.
1. Impostare i parametri di utilizzo della memoria di Windows.
1. Registrati [!DNL Insight Server] come servizio Windows come descritto nella [registrazione di Insight Server come servizio](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)Windows.
