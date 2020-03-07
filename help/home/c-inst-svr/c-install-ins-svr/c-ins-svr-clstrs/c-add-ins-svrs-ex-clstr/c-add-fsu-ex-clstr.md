---
description: È possibile aggiungere un FSU di Insight Server a un cluster esistente se si desidera memorizzare i dati di origine in un file server aggiuntivo o se si desidera impostare un backup per il server di Insight principale.
solution: Insight
title: Aggiunta di un FSU per server di Insight a un cluster esistente
uuid: 57d6ef52-eef9-4425-943a-331e4c9c4207
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Aggiunta di un FSU per server di Insight a un cluster esistente{#adding-an-insight-server-fsu-to-an-existing-cluster}

È possibile aggiungere un FSU di Insight Server a un cluster esistente se si desidera memorizzare i dati di origine in un file server aggiuntivo o se si desidera impostare un backup per il server di Insight principale.

Per aggiungere un [!DNL Insight Server] FSU a un cluster esistente, è necessario eseguire le seguenti procedure:

1. [Aggiornamento dei file di configurazione sul server master](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-b5f21f2edb35493da4475de2cdeefca1)
1. [Installazione del nuovo FSU di Insight Server](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-dddad299dd8642aa91cbe19a395ef3f4)
1. [Configurazione del nuovo FSU del server Insight](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-add-ins-svrs-ex-clstr/c-add-fsu-ex-clstr.md#section-c39334c5bd754d5b98d41ad094333108)

## Aggiornamento dei file di configurazione sul server master {#section-b5f21f2edb35493da4475de2cdeefca1}

In [!DNL Insight], aprite il file [!DNL Server Files Manager] per il master [!DNL Insight Server] (in genere un [!DNL Insight Server] FSU) ed effettuate le seguenti operazioni per ogni FSU che desiderate aggiungere al cluster:

1. Modificate il file dell&#39;indirizzo sul master [!DNL Insight Server] per includere il nome e l&#39;indirizzo del nuovo FSU come descritto in [Aggiunta dei server di visualizzazione dell&#39;elaborazione al file](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-2fe5298180164e8dbaa59ea6b6ff682d)dell&#39;indirizzo. Aggiungete il nome e l&#39;indirizzo del nuovo FSU al gruppo in cui [!DNL Insight Servers] sono elencati gli attuali cluster.

1. Modificare il file di controllo di accesso sul master [!DNL Insight Server] per includere l&#39;indirizzo IP del nuovo FSU come descritto in [Aggiornamento del file di controllo di accesso per un cluster](../../../../../home/c-inst-svr/c-install-ins-svr/c-ins-svr-clstrs/c-inst-ins-svr-clstr/c-inst-proc-clstr/c-config-mstr-ins-svr-clstr.md#section-fce1367d92a445168c35e9ca506e7d6b).

## Installazione del nuovo FSU di Insight Server {#section-dddad299dd8642aa91cbe19a395ef3f4}

1. Sul FSU corrente, creare un file zip della directory di [!DNL Insight Server] installazione e copiare il file nella nuova FSU.
1. Decomprimete il file nella posizione in cui desiderate inserire il [!DNL Insight Server] software.
1. Scaricate e installate il certificato digitale per la nuova FSU come descritto in [Download e installazione dei certificati](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-dnld-dgtl-cert/c-dnld-dgtl-cert.md#concept-4f79c240492f4e52b6375b4b3bbefa17)digitali.
1. Impostare i parametri di utilizzo della memoria di Windows sul nuovo FSU.
1. Modificare il nome del [!DNL .address] file in modo che rifletta il nome dell&#39;FSU come descritto in [Definizione del percorso](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649)di rete del server.

1. Se la struttura dell&#39;unità sul nuovo FSU è diversa da quella dell&#39;FSU principale, è necessario modificare il [!DNL Disk Files.cfg] file.

   1. Aprire il [!DNL Disk Files.cfg] file sulla nuova FSU.
   1. Aggiornare le impostazioni in modo che corrispondano alle unità dell&#39;FSU principale come descritto in [Monitoring Dataset Data Space](../../../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/t-mntr-dtst-data-spc.md#task-6223fa2c718845678824a0a96df96a03).
   1. Salvate il file localmente e sul server.

1. Registrarsi [!DNL Insight Server] come servizio Windows sul nuovo computer FSU come descritto in [Registrazione di Insight Server come servizio](../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-reg-wdws-svc.md#concept-f2c7aa891d544a2595aa01d0d796a540)Windows.

1. Ripetere i passaggi da 1 a 6 per ogni ulteriore FSU che si sta aggiungendo al cluster.

## Configurazione del nuovo FSU del server Insight {#section-c39334c5bd754d5b98d41ad094333108}

Le procedure seguenti forniscono istruzioni per specifiche attività di configurazione. Seguire le istruzioni appropriate per l&#39;implementazione della nuova FSU.

**Configurazione dell&#39;FSU per l&#39;archiviazione dei dati di origine**

Se il nuovo FSU memorizza dati di origine aggiuntivi per il set di dati in esecuzione nel cluster, è necessario completare il processo di configurazione del file server come descritto in Configurazione di un&#39;unità del [!DNL Insight Server] file server nel capitolo File di configurazione dell&#39;elaborazione del registro della Guida alla configurazione del *set di dati*.

**Per effettuare al nuovo FSU il backup per il master[!DNL Insight Server]FSU**

Se si desidera rendere il nuovo FSU il backup per il master [!DNL Insight Server] (che funge da FSU per il cluster), è necessario modificare il file di sincronizzazione sul nuovo FSU (backup) in modo che si sincronizzi con il FSU principale.

1. Nella [!DNL Insight Server] FSU di backup, usate [!DNL Server Files Manager] per copiare il [!DNL Synchronize.cfg] file nella [!DNL Components for Processing Servers] cartella alla [!DNL Components] cartella.

1. Aprite il [!DNL Synchronize.cfg] file (nella [!DNL Components] cartella) in [!DNL Insight].

1. Individuate SynchronizeDir che specifica la posizione della directory Components (Componenti). Potrebbero essere presenti diverse directory di sincronizzazione elencate in Directory, pertanto potrebbe essere necessario visualizzare il contenuto per molti di essi (facendo clic sul numero del server) per trovare il server desiderato).
1. Modificate la voce SynchronizeDir e aggiungete una seconda voce SynchronizeDir come illustrato nell’esempio di seguito.

   ![](assets/cfg_cluster_SynchronizeDirEditComponents.png)

1. Salvate il file modificato con un nuovo nome, ad esempio [!DNL FSU_Synchronize.cfg] in modo da non confonderlo con i [!DNL Synchronize.cfg] file DPU del cluster.

1. Utilizzate l&#39;icona [!DNL Server Files Manager] per salvare la copia locale del file rinominato nel server. L&#39;FSU di backup scarica i file nelle directory identificate dall&#39; [!DNL Insight Server] FSU principale e recupera dinamicamente le copie aggiornate di questi file dall&#39; [!DNL Insight Server] FSU principale quando cambiano.

