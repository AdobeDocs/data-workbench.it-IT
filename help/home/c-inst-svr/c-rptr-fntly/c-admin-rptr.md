---
description: Le attività amministrative per la funzionalità di ripetizione sono molto simili a quelle per Insight Server.
solution: Insight
title: Amministrazione Ripetitore
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Amministrazione Ripetitore{#administering-repeater}

Le attività amministrative per la funzionalità di ripetizione sono molto simili a quelle per Insight Server.

Si applicano i seguenti compiti amministrativi; le eccezioni o le modifiche necessarie affinché il [!DNL Insight Server] DPU possa essere utilizzato con il server di ripetizione siano annotate dopo ogni passaggio.

* [Nuova convalida del certificato digitale](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [Per confermare che il servizio è in esecuzione](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) Nell&#39;elenco dei servizi nel pannello di controllo Servizi, cercare &quot;Ripetitore&quot;.

* [Configurazione del controllo di accesso](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [Monitoraggio dello spazio](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) su disco I tipi di dati che si applicano al server ripetitore sono i dati evento, del sistema operativo e del sistema. Se si utilizza il server ripetitore per l&#39;archiviazione di backup e si rende necessario liberare più spazio di archiviazione dati sul computer, è possibile spostare tutti i file di registro tranne il giorno più recente su un altro computer o supporto di memorizzazione dati (unità zip, nastro e così via). Lo spostamento dei dati non richiede l&#39;arresto del servizio di ripetizione.

   >[!NOTE]
   >
   >È necessario verificare l&#39;integrità delle copie di backup dei [!DNL .vsl] file prima di eliminarli dal Ripetitore.

* [Configurazione degli avvisi amministrativi](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [Monitoraggio degli eventi amministrativi](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [Monitoraggio dei registri di controllo](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [Configurazione delle comunicazioni](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [Il riavvio della funzionalità Servizio](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74) [!DNL Repeater] è progettato per essere eseguito in modo continuo. Se si riavvia il computer, il ripetitore si riavvia automaticamente. Se è necessario avviare e arrestare il ripetitore manualmente, è possibile farlo utilizzando il pannello di controllo Servizi in Windows.

