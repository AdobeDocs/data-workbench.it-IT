---
description: Normalmente, il server Workbench dati risponde alle domande degli utenti in entrata non appena vengono ricevute e continua a fornire risultati e aggiornamenti in tempo reale fino a quando l'utente non le richiede più.
solution: Analytics
title: Coda query
topic: Data workbench
uuid: 4d64bc89-b664-4532-9f17-be11812d36d4
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Coda query{#query-queue}

Normalmente, il server Workbench dati risponde alle domande degli utenti in entrata non appena vengono ricevute e continua a fornire risultati e aggiornamenti in tempo reale fino a quando l&#39;utente non le richiede più.

A volte, in particolare nei sistemi con molti utenti di Workbench dati, il numero di query attive richiede più risorse di sistema di quelle disponibili dal server. [!DNL Query Queue] consente al server di sospendere temporaneamente alcune query fino a quando non saranno disponibili le risorse necessarie per fornire le risposte. Vengono [!DNL Query Queue] inoltre fornite funzionalità per assegnare priorità alle query in base a una serie di parametri, in modo che in caso di conflitto di risorse, le query con priorità superiore abbiano la precedenza.

Le query provenienti da un singolo client o server di report vengono inserite in un gruppo e pianificate come un&#39;unità. È possibile configurare i monitor delle risorse per limitare la quantità di risorse di sistema utilizzate dalle query. Quando le risorse monitorate consentono la programmazione di un altro gruppo di query, il gruppo con priorità massima è pianificato. Gli utenti le cui query non sono ancora pianificate, a causa di limitazioni delle risorse, non ricevono un errore ma ricevono una notifica che le loro query sono in coda e che l&#39;utente può continuare a lavorare sull&#39;esempio locale.

La configurazione predefinita include una configurazione semplice per l&#39; [!DNL Query Queue], ma la lascia disattivata. Gli amministratori possono attivare o disattivare i [!DNL Query Queue], configurare i monitor delle risorse per determinare la quantità di risorse utilizzate per le query e configurare criteri di priorità complessi per i diversi utenti.

**Per configurare il file Server.cfg per[!DNL Query Queuing]**

1. Apri [!DNL Server.cfg] facendo clic su **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]** > **[!UICONTROL Dataset]**.
1. Fare clic con il pulsante destro del mouse **[!UICONTROL Server.cfg]** e renderlo locale per la modifica.
1. Espandi [!DNL Query Queue].

   ![](assets/queryqueue1.png)

1. Configurate i seguenti parametri:

   * **Gruppi di utenti:** Consente di configurare criteri, utenti e priorità della coda. Consultate Gruppi [di utenti della coda di](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1) query per le definizioni.

   * **Attivo:** (Vettoriale) Abilita o disabilita il [!DNL Query Queue]. I valori validi sono true o false. L&#39;impostazione predefinita è false.

   * **Gruppo utenti predefinito:** (Stringa) Digitate un nome del gruppo di utenti al quale vengono aggiunti gli utenti, se questi non sono elencati in alcun gruppo di utenti.
   * **Monitor risorse:** (Vettoriale) Fate clic con il pulsante destro del mouse per aggiungere un monitor di risorse. È possibile specificare se eseguire il [!DNL Query Queue] monitoraggio della memoria o del numero di query. Fare clic con il pulsante destro del mouse **[!UICONTROL Resource Monitor]** per scegliere Monitor budget memoria o Monitor numero di query. Per ulteriori informazioni, consulta Monitoraggio risorse coda [query](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-res-mon.md#concept-0840967b228c4d5ba3b59b4b2759f325) .

   * **Priorità non toccabile:** (Int) Specifica che i batch con priorità maggiore o uguale a questo valore non vengono mai impediti alla programmazione di batch con priorità maggiore. Utilizzata insieme alla [!DNL Memory Budget Monitor] descritta nella tabella [Parametri del gruppo di](../../../../home/c-get-started/c-admin-intrf/c-query-que/c-query-que-user-grps.md#concept-5555f51402ed49419c067d61738474c1)utenti.

