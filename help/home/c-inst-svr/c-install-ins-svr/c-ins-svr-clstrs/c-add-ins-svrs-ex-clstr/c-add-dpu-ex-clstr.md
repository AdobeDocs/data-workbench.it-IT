---
description: In genere, si desidera aggiungere un'unità di elaborazione dati di Insight Server a un cluster esistente quando la quantità di dati da elaborare e rendere accessibili agli utenti di Insight e Report supera la capacità della configurazione corrente del cluster.
solution: Analytics
title: Aggiunta di una DPU di Insight Server a un cluster esistente
uuid: 1977a90e-bd51-4838-9498-f7692891109f
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---


# Aggiunta di una DPU di Insight Server a un cluster esistente{#adding-an-insight-server-dpu-to-an-existing-cluster}

In genere, si desidera aggiungere un&#39;unità di elaborazione dati di Insight Server a un cluster esistente quando la quantità di dati da elaborare e rendere accessibili agli utenti di Insight e Report supera la capacità della configurazione corrente del cluster.

## Aggiornamento dei file di configurazione sul server master {#section-7c9a23754a994d73b722d53f999f0e82}

In [!DNL Insight], aprite il file [!DNL Server Files Manager] per il master [!DNL Insight Server] (in genere un [!DNL Insight Server] FSU) ed effettuate le seguenti operazioni per ogni unità di elaborazione dati da aggiungere al cluster:

1. Modificate il file dell&#39;indirizzo sul master [!DNL Insight Server] per includere il nome e l&#39;indirizzo del nuovo DPU come descritto in [Aggiunta di server di elaborazione a tale file](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Aggiungete il nome e l’indirizzo del nuovo DPU al gruppo in cui [!DNL Insight Servers] sono elencati gli attuali cluster.

1. Modificate il file di controllo di accesso sul master [!DNL Insight Server] per includere l&#39;indirizzo IP del nuovo DPU come descritto in [Aggiornamento del file di controllo di accesso per un cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Installazione della nuova unità DPU di Insight Server {#section-8ce9a5957db24f94b3a3250caaccc7ba}

Questa attività è valida solo per Windows a 32 bit.

1. Copiate le seguenti directory da uno dei DPU correnti nel cluster al nuovo DPU:

   * [!DNL Insight Server] directory di installazione/bin/
   * [!DNL Insight Server] directory di installazione/Certificati/
   * [!DNL Insight Server] directory di installazione/Components/

1. Scaricate e installate il certificato digitale per la nuova DPU come descritto in [Download e installazione dei certificati](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)digitali.
1. Impostare i parametri di utilizzo della memoria di Windows sul nuovo DPU.
1. Registrati [!DNL Insight Server] come servizio Windows nel nuovo computer DPU come descritto in [Registrazione di Insight Server come servizio](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)Windows.

1. Controllate i registri di traccia per assicurarvi che il DPU sia sincronizzato con il master [!DNL Insight Server].
1. Ripetere i passaggi da 1 a 6 per ogni unità DPU aggiuntiva che si sta aggiungendo al cluster.

## Aggiunta del nuovo DPU Server Insight ai server di elaborazione del profilo di dati {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

Se il nuovo DPU elabora lo stesso dataset degli altri DPU del cluster, aggiungete al [!DNL profile.cfg] file master il nome comune della nuova DPU [!DNL Insight Server] come descritto in [Specifica dei server di elaborazione in Profile.cfg](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9).
