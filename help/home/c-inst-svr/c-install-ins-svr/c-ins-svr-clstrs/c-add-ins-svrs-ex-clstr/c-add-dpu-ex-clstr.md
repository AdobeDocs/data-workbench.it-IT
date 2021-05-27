---
description: In genere, si desidera aggiungere una DPU di Insight Server a un cluster esistente quando la quantità di dati che si desidera elaborare e rendere accessibili agli utenti di Insight e Report supera la capacità della configurazione corrente del cluster.
title: Aggiunta di una DPU di Insight Server a un cluster esistente
uuid: 1977a90e-bd51-4838-9498-f7692891109f
exl-id: 9cac2795-626b-4fe3-8a7c-f36c9f1dc68f
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 4%

---

# Aggiunta di una DPU di Insight Server a un cluster esistente{#adding-an-insight-server-dpu-to-an-existing-cluster}

In genere, si desidera aggiungere una DPU di Insight Server a un cluster esistente quando la quantità di dati che si desidera elaborare e rendere accessibili agli utenti di Insight e Report supera la capacità della configurazione corrente del cluster.

## Aggiornamento dei file di configurazione sul server master {#section-7c9a23754a994d73b722d53f999f0e82}

In [!DNL Insight], apri il [!DNL Server Files Manager] per il tuo master [!DNL Insight Server] (in genere una FSU [!DNL Insight Server]) e procedi come segue per ogni DPU che desideri aggiungere al cluster:

1. Modifica il file dell&#39;indirizzo sul master [!DNL Insight Server] per includere il nome e l&#39;indirizzo della nuova DPU come descritto in [Aggiunta dell&#39;elaborazione di Insight Server al file dell&#39;indirizzo](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Aggiungi il nome e l’indirizzo della nuova DPU al gruppo in cui sono elencati i valori correnti del cluster [!DNL Insight Servers].

1. Modifica il file di controllo di accesso sul master [!DNL Insight Server] per includere l&#39;indirizzo IP della nuova DPU come descritto in [Aggiornamento del file di controllo di accesso per un cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Installazione della nuova DPU di Insight Server {#section-8ce9a5957db24f94b3a3250caaccc7ba}

Questa attività si applica solo a Windows a 32 bit.

1. Copia le seguenti directory da una delle DPU correnti nel cluster nella nuova DPU:

   * [!DNL Insight Server] directory di installazione/bin/
   * [!DNL Insight Server] directory di installazione/Certificati/
   * [!DNL Insight Server] directory di installazione/Componenti/

1. Scarica e installa il certificato digitale per la nuova DPU come descritto in [Download e installazione dei certificati digitali](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Impostare i parametri di utilizzo della memoria di Windows sulla nuova DPU.
1. Registrati [!DNL Insight Server] come servizio Windows sul nuovo computer DPU come descritto in [Registrazione di Insight Server come servizio Windows](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. Controlla i log di traccia per assicurarti che la DPU sia sincronizzata con il master [!DNL Insight Server].
1. Ripetere i passaggi da 1 a 6 per ogni DPU aggiuntiva aggiunta al cluster.

## Aggiunta della nuova DPU di Insight Server ai server di elaborazione del profilo di set di dati {#section-cdc6c3913b9f4010b5e17cc7ec85e849}

Se la nuova DPU elabora lo stesso set di dati delle altre DPU del cluster, aggiungi il nome comune della nuova DPU al file [!DNL profile.cfg] sul file principale [!DNL Insight Server] come descritto in [Specifica dei server di elaborazione in Profile.cfg](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-prof-run-clstr.md#section-99664e072c21462f91fbafb6d893fcf9).
