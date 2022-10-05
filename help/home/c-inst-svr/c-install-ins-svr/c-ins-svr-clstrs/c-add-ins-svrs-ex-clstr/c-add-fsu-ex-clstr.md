---
description: È possibile aggiungere una FSU di Insight Server a un cluster esistente se si desidera memorizzare i dati di origine in un file server aggiuntivo o se si desidera impostare un backup per Insight Server master.
title: Aggiunta di una FSU di Insight Server a un cluster esistente
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
exl-id: b3b08016-42ad-4972-a8b7-ee714493fa52
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '699'
ht-degree: 2%

---

# Aggiunta di una FSU di Insight Server a un cluster esistente{#adding-an-insight-server-fsu-to-an-existing-cluster}

{{eol}}

È possibile aggiungere una FSU di Insight Server a un cluster esistente se si desidera memorizzare i dati di origine in un file server aggiuntivo o se si desidera impostare un backup per Insight Server master.

Per aggiungere un [!DNL Insight Server] FSU a un cluster esistente, è necessario eseguire le seguenti procedure:

1. [Aggiornamento dei file di configurazione sul server master](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [Installazione della nuova FSU di Insight Server](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [Configurazione della nuova FSU di Insight Server](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## Aggiornamento dei file di configurazione sul server master {#section-b5f21f2edb35493da4475de2cdeefca1}

In [!DNL Insight], aprire [!DNL Server Files Manager] per il tuo master [!DNL Insight Server] (di solito [!DNL Insight Server] FSU) ed effettuare le seguenti operazioni per ogni FSU che si desidera aggiungere al cluster:

1. Modificare il file dell&#39;indirizzo sul master [!DNL Insight Server] per includere il nome e l&#39;indirizzo della nuova FSU come descritto in [Aggiunta dell’elaborazione di Insight Server al file degli indirizzi](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d). Aggiungi il nome e l&#39;indirizzo della nuova FSU al gruppo in cui il cluster è corrente [!DNL Insight Servers] sono elencati.

1. Modificare il file di controllo di accesso sul master [!DNL Insight Server] per includere l&#39;indirizzo IP della nuova FSU come descritto in [Aggiornamento del file di controllo di accesso per un cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Installazione della nuova FSU di Insight Server {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. Sulla FSU corrente, creare un file zip del [!DNL Insight Server] directory di installazione e copia il file nella nuova FSU.
1. Decomprimi il file nella posizione in cui desideri inserire il [!DNL Insight Server] software.
1. Scarica e installa il certificato digitale per la nuova FSU come descritto in [Download e installazione dei certificati digitali](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17).
1. Impostare i parametri di utilizzo della memoria di Windows sulla nuova FSU.
1. Modificare il nome della [!DNL .address] per riflettere il nome della FSU come descritto in [Definizione del percorso di rete del server](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649).

1. Se la struttura dell&#39;unità della nuova FSU è diversa da quella della FSU primaria, è necessario modificare il [!DNL Disk Files.cfg] file.

   1. Apri [!DNL Disk Files.cfg] sul nuovo FSU.
   1. Aggiornare le impostazioni in modo che corrispondano alle unità della FSU primaria come descritto in [Monitoraggio dello spazio dei dati del set di dati](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03).
   1. Salva il file localmente e sul server.

1. Registro [!DNL Insight Server] come servizio Windows sul nuovo computer FSU come descritto in [Registrazione di Insight Server come servizio Windows](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540).

1. Ripetere i passaggi da 1 a 6 per ogni FSU aggiuntiva che si sta aggiungendo al cluster.

## Configurazione della nuova FSU di Insight Server {#section-c39334c5bd754d5b98d41ad094333108}

Le procedure seguenti forniscono istruzioni per specifiche attività di configurazione. Seguire le istruzioni appropriate per l&#39;implementazione della nuova FSU.

**Per configurare la FSU per l&#39;archiviazione dei dati di origine**

Se la nuova FSU memorizza dati di origine aggiuntivi per il set di dati in esecuzione sul cluster, è necessario completare il processo di configurazione del file server come descritto in Configurazione di un [!DNL Insight Server] Unità file server nel capitolo File di configurazione dell&#39;elaborazione del registro *Guida alla configurazione del set di dati*.

**Per fare al nuovo FSU il backup per il master [!DNL Insight Server] FSU**

Se si desidera rendere la nuova FSU il backup per il master [!DNL Insight Server] (che funge da FSU per il cluster), è necessario modificare il file di sincronizzazione sulla nuova FSU (backup) in modo che si sincronizzi con la FSU principale.

1. Sul backup [!DNL Insight Server] FSU, utilizzare [!DNL Server Files Manager] per copiare [!DNL Synchronize.cfg] nel [!DNL Components for Processing Servers] nella cartella [!DNL Components] cartella.

1. Apri [!DNL Synchronize.cfg] (nel [!DNL Components] in [!DNL Insight].

1. Trova la proprietà SynchronizeDir che specifica la posizione della directory Components. Possono essere presenti diverse directory di sincronizzazione elencate in Directory, quindi potrebbe essere necessario visualizzare il contenuto per molte di esse (facendo clic sul numero del server) per trovare il server desiderato).
1. Modificate la voce SynchronizeDir e aggiungete una seconda voce SynchronizeDir come mostrato nell&#39;esempio seguente.

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. Salvare il file modificato con un nuovo nome, ad esempio [!DNL FSU_Synchronize.cfg] in modo da non confonderlo con il [!DNL Synchronize.cfg] file sulle DPU nel cluster.

1. Utilizza la [!DNL Server Files Manager] per salvare sul server la copia locale del file rinominato. La FSU di backup scarica i file nelle directory identificate dal master [!DNL Insight Server] FSU e recupera dinamicamente le copie aggiornate di questi file dal master [!DNL Insight Server] FSU quando cambiano.
