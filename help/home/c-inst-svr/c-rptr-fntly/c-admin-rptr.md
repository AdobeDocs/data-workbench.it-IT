---
description: Le attività amministrative per la funzionalità ripetitore sono molto simili a quelle di Insight Server.
title: Amministrazione del Repeater (Ripetitore)
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
exl-id: 5c7a4f95-be4b-4c2c-8dea-19037ba0b5cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 12%

---

# Amministrazione del Repeater (Ripetitore){#administering-repeater}

{{eol}}

Le attività amministrative per la funzionalità ripetitore sono molto simili a quelle di Insight Server.

Si applicano i seguenti compiti amministrativi; le eccezioni o le modifiche che è necessario apportare affinché il [!DNL Insight Server] DPU può essere utilizzato con il server di ripetizione sono annotati dopo ogni passaggio.

* [Nuova convalida del certificato digitale](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [Conferma dell’esecuzione del servizio](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) Nell’elenco dei servizi nel pannello di controllo Servizi, cercare &quot;Repeater&quot; (Ripetitore).

* [Configurazione del controllo di accesso](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [Monitoraggio dello spazio su disco](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) I tipi di dati applicati al server di ripetizione sono dati evento, sistema operativo e sistema. Se si utilizza il server Repeater per l&#39;archiviazione dei backup e si rende necessario rendere disponibile più spazio di archiviazione dei dati sul computer, è possibile spostare tutti i file di log del giorno, tranne il più recente, in un altro computer o supporto di archiviazione dei dati (unità zip, nastro e così via). Lo spostamento dei dati non richiede l’arresto del servizio Repeater (Ripetitore).

   >[!NOTE]
   >
   >Verificare l&#39;integrità delle copie di backup del [!DNL .vsl] file prima di eliminarli da Repeater.

* [Configurazione degli avvisi amministrativi](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [Monitoraggio degli eventi amministrativi](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [Monitoraggio degli audit di controllo](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [Configurazione delle comunicazioni](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [Riavvio del servizio](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74)  [!DNL Repeater] funzionalità progettata per l&#39;esecuzione continua. Se si riavvia il computer, il ripetitore si riavvia automaticamente. Se è necessario avviare e arrestare manualmente il ripetitore, è possibile farlo utilizzando il pannello di controllo Servizi di Windows.
