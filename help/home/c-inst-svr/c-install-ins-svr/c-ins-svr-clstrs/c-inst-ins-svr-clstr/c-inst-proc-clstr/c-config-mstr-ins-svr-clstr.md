---
description: Informazioni sulla configurazione del cluster su Master Insight Server, sull’aggiornamento del file di controllo degli accessi per un cluster e altro ancora.
title: Configurazione di Master Insight Server per il clustering
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# Configurazione di Master Insight Server per il clustering{#configuring-the-master-insight-server-for-clustering}

Informazioni sulla configurazione del cluster su Master Insight Server, sull’aggiornamento del file di controllo degli accessi per un cluster e altro ancora.

Per configurare il cluster, esegui i seguenti passaggi sul master [!DNL Insight Server]:

* Aggiungi i nomi e gli indirizzi comuni di elaborazione [!DNL Insight Servers’] al file degli indirizzi.
* Aggiungi tutti i [!DNL Insight Servers] al gruppo Cluster Server nel file [!DNL Access Control.cfg].

* Aggiorna il file [!DNL Synchronize.cfg] nella directory Components for Processing Servers per puntare al master [!DNL Insight Server].

* Se necessario, modifica il file [!DNL Disk Files.cfg] nella directory Components for Processing Servers per specificare la posizione del file [!DNL temp.db] nell&#39;elaborazione [!DNL Insight Servers].

Per completare questi passaggi, è necessario conoscere i nomi comuni (come specificato nei certificati digitali per il singolo [!DNL Insight Server]) e gli indirizzi IP di ciascun [!DNL Insight Server] nel cluster. Se non si dispone già di queste informazioni, ottenerle prima di procedere.

>[!NOTE]
>
>Le procedure descritte in questa sezione richiedono [!DNL Insight]. Se non hai installato [!DNL Insight], segui le istruzioni contenute nella **[!DNL Insight]Guida utente** prima di procedere.

## Aggiunta dell’elaborazione di Insight Server al file degli indirizzi {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Segui la procedura seguente per aggiungere i nomi comuni e gli indirizzi IP di elaborazione [!DNL Insight Servers’] al file degli indirizzi sul master [!DNL Insight Server]. (Anche se il file dell&#39;indirizzo viene mantenuto e amministrato sul master [!DNL Insight Server], viene utilizzato da tutti i [!DNL Insight Servers] nel cluster.)

>[!NOTE]
>
>Di seguito si presuppone che il file dell&#39;indirizzo sia già stato configurato per il master [!DNL Insight Server]. Se non hai già aggiunto gli indirizzi IP master [!DNL Insight Server’s] al file degli indirizzi, completa la procedura descritta in [Definizione del percorso di rete del server](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) prima di iniziare.

**Per aggiungere l’elaborazione  [!DNL Insight Servers] al file dell’indirizzo**

1. Avvia [!DNL Insight] e carica il profilo di configurazione (se non è già aperto) facendo clic con il pulsante destro del mouse sulla barra del titolo e facendo clic su **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del master **[!UICONTROL Insight Server]** e fare clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], apri la directory Indirizzi e procedi come segue per aprire il file dell&#39;indirizzo [!DNL Insight Server’s]:

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* e fai clic su **[!UICONTROL Make Local]**.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Espandere i contenuti della struttura [!DNL Locations], quindi espandere NetworkLocation 0, Indirizzi e AddressDefinition.
1. Per aggiungere una definizione AddressDefinition a NetworkLocation 0 per ogni elaborazione [!DNL Insight Server] nel cluster, procedere come segue:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL AddressDefinition]** e fai clic su **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. Nel parametro Name, specifica il nome comune di elaborazione [!DNL Insight Server’s].
   1. Nel parametro Address , specifica l’indirizzo IP di elaborazione [!DNL Insight Server’s].

      È possibile utilizzare un asterisco come carattere jolly nel campo Indirizzo, ad esempio 10.10.116.*, per semplificare il clustering. Consultare [Informazioni sui livelli di accesso](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      L&#39;esempio seguente definisce un cluster contenente due [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Se i server sono connessi a più reti, ripetere il passaggio 6 per aggiungere l&#39;elaborazione [!DNL Insight Servers] alle NetworkLocations per tali reti.

   L&#39;esempio seguente mostra un cluster di quattro [!DNL Insight Servers] collegati a due reti (&quot;Intranet aziendale&quot; e &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Aggiornamento del file di controllo di accesso per un cluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Per utilizzare [!DNL Insight Servers] in un cluster, ogni [!DNL Insight Server] nel cluster (incluso il master [!DNL Insight Server]) deve appartenere al gruppo di controllo accessi ai cluster server. Il gruppo Cluster Server identifica i server (per indirizzo IP) autorizzati a partecipare al cluster. Anche se questo file viene mantenuto e amministrato sul master [!DNL Insight Server], viene utilizzato da tutti i [!DNL Insight Servers] nel cluster.

**Per modificare il file di controllo di accesso**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del master [!DNL Insight Server] e fare clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], apri la directory Controllo accessi .
1. Per aprire il file [!DNL Access Control.cfg], procedi come segue:

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* e fai clic su **[!UICONTROL Make Local]**.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Espandere la struttura dei gruppi di controllo di accesso, quindi espandere AccessGroup (Cluster Server).
1. Per ogni [!DNL Insight Server] nel cluster (incluso il master [!DNL Insight Server]), procedi come segue:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Members]** e fai clic su **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Specifica l&#39;indirizzo IP [!DNL Insight Server’s] (il suo indirizzo IP numerico, non il suo nome). Se i [!DNL Insight Servers] sono connessi a più reti, AccessGroup deve contenere solo gli indirizzi interni utilizzati da [!DNL Insight Servers] per la comunicazione tra server all&#39;interno del cluster.

      Di seguito viene illustrato AccessGroup (Cluster Server) per un cluster di quattro [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configurazione del file di sincronizzazione {#section-d23e751771c84da6bab6a34a8db867bc}

Per configurare la copia centrale del file [!DNL Synchronize.cfg] è possibile utilizzare la procedura seguente. La copia centrale di questo file viene mantenuta sul master [!DNL Insight Server]. L&#39;elaborazione [!DNL Insight Servers] nel cluster avvia la comunicazione con il master [!DNL Insight Server] per recuperare una copia aggiornata di questo file.

Il file [!DNL Synchronize.cfg] specifica la posizione del master [!DNL Insight Server]. Inoltre identifica il set di file amministrativi che ogni elaborazione [!DNL Insight Servers] nel cluster recupera dal master [!DNL Insight Server]. L&#39;elaborazione [!DNL Insight Servers] scarica automaticamente questi file dal master [!DNL Insight Server] all&#39;avvio. Inoltre, recuperano in modo dinamico le copie aggiornate di questi file dal master [!DNL Insight Server] quando i file cambiano.

>[!NOTE]
>
>Anche se si configura il file [!DNL Synchronize.cfg] sul master [!DNL Insight Server], il master [!DNL Insight Server] stesso non utilizza questo file. Questo file viene aggiornato sul master [!DNL Insight Server] in modo che sia configurato correttamente quando il file di elaborazione [!DNL Insight Servers] recupera il file.

**Per aggiornare il file Synchronize.cfg sul master[!DNL Insight Server]**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del master [!DNL Insight Server] e fare clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], apri la directory **[!UICONTROL Components]** per Server di elaborazione.

1. Per aprire [!DNL Synchronize.cfg], procedi come segue:

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* e fai clic su **[!UICONTROL Make Local]**.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Espandi la struttura del componente.
1. Nel parametro Indirizzo server principale cluster specificare l&#39;indirizzo IP del master (primario) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Per creare un registro che registra ogni volta che si verifica la sincronizzazione tra il master [!DNL Insight Server] e l&#39;elaborazione [!DNL Insight Servers], assicurati che il parametro Abilita registro sincronizzazione sia impostato su &quot;true&quot;.

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configurazione della posizione del set di dati (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Esegui la seguente procedura se desideri che l&#39;elaborazione [!DNL Insight Servers] mantenga [!DNL temp.db] (il set di dati) in una directory o unità diverse dalla posizione predefinita o se desideri distribuire [!DNL temp.db] su più unità.

>[!NOTE]
>
>Poiché le [!DNL Insight Servers] di elaborazione condividono tutte le stesse [!DNL Disk Files.cfg], devono supportare tutte le posizioni dei file specificate in questo file. Ad esempio, se assegni [!DNL temp.db] all&#39;E: unità, ogni elaborazione [!DNL Insight Server] nel cluster deve avere un E: guida.

**Per configurare il percorso di temp.db**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] fare clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro di Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del master [!DNL Insight Server] e fare clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], apri la directory **[!UICONTROL Components for Processing Servers]** .

1. Per aprire [!DNL Disk Files.cfg], procedi come segue:

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* e fai clic su **[!UICONTROL Make Local]**.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna [!DNL Temp]e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Espandere la struttura DiskSpaceManagerComponent, quindi espandere l&#39;elenco File disco.
1. Modifica la voce 0 per modificare la posizione del file [!DNL temp.db].
1. Se si desidera distribuire [!DNL temp.db] su più unità, utilizzare i passaggi seguenti per creare una voce aggiuntiva per ogni unità aggiuntiva.

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Disk Files]** e fai clic su **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Nella nuova voce, specifica il percorso in cui desideri scrivere [!DNL temp.db].
   Di seguito sono riportati i [!DNL temp.db] scritti su quattro unità.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
