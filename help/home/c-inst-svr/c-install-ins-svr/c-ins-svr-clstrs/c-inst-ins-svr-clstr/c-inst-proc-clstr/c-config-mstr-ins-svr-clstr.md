---
description: Informazioni sulla configurazione del cluster su Master Insight Server, sull’aggiornamento del file di controllo degli accessi per un cluster e altro ancora.
title: Configurazione di Master Insight Server per il clustering
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
exl-id: 28126ba4-6d81-4ca4-895c-4e8b1a54a693
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 1%

---

# Configurazione di Master Insight Server per il clustering{#configuring-the-master-insight-server-for-clustering}

{{eol}}

Informazioni sulla configurazione del cluster su Master Insight Server, sull’aggiornamento del file di controllo degli accessi per un cluster e altro ancora.

Per configurare il cluster, esegui i seguenti passaggi sul master [!DNL Insight Server]:

* Aggiungi l’elaborazione [!DNL Insight Servers’] nomi e indirizzi comuni al file degli indirizzi.
* Aggiungi tutti i [!DNL Insight Servers] al gruppo Cluster Server nel [!DNL Access Control.cfg] file.

* Aggiorna [!DNL Synchronize.cfg] nella directory Components for Processing Servers per puntare al master [!DNL Insight Server].

* Se necessario, modifica la [!DNL Disk Files.cfg] nella directory Components for Processing Servers per specificare il percorso [!DNL temp.db] file di elaborazione [!DNL Insight Servers].

Per completare questi passaggi, è necessario conoscere i nomi comuni (come specificato nei certificati digitali per i singoli utenti [!DNL Insight Server]) e gli indirizzi IP di ciascuno [!DNL Insight Server] nel cluster. Se non si dispone già di queste informazioni, ottenerle prima di procedere.

>[!NOTE]
>
>Le procedure descritte in questa sezione richiedono [!DNL Insight]. Se non hai installato [!DNL Insight], segui le istruzioni contenute nella **[!DNL Insight]Guida utente** prima di procedere.

## Aggiunta dell’elaborazione di Insight Server al file degli indirizzi {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Per aggiungere l’elaborazione, attenersi alla procedura descritta di seguito. [!DNL Insight Servers’] nomi comuni e indirizzi IP al file dell&#39;indirizzo sul master [!DNL Insight Server]. (Anche se il file dell&#39;indirizzo viene mantenuto e amministrato sul master [!DNL Insight Server], viene utilizzato da tutte le [!DNL Insight Servers] nel cluster).

>[!NOTE]
>
>Di seguito si presuppone che il file dell&#39;indirizzo sia già stato configurato per il master [!DNL Insight Server]. Se non hai già aggiunto il master [!DNL Insight Server’s] Indirizzi IP al file dell&#39;indirizzo, completare la procedura descritta in [Definizione del percorso di rete del server](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) prima di iniziare.

**Per aggiungere l’elaborazione [!DNL Insight Servers] al file dell&#39;indirizzo**

1. Inizio [!DNL Insight] e carica il profilo di configurazione (se non è già aperto) facendo clic con il pulsante destro del mouse sulla barra del titolo e facendo clic su **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del master **[!UICONTROL Insight Server]** e fai clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], apri la directory Indirizzi e procedi come segue per aprire la [!DNL Insight Server’s] file di indirizzo:

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* e fai clic su **[!UICONTROL Make Local]**.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Espandi i contenuti della [!DNL Locations] quindi espandere NetworkLocation 0, Indirizzi e AddressDefinition.
1. Eseguire le operazioni seguenti per aggiungere un oggetto AddressDefinition a NetworkLocation 0 per ogni elaborazione [!DNL Insight Server] nel cluster:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL AddressDefinition]** e fai clic su **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. Nel parametro Nome , specifica l’elaborazione [!DNL Insight Server’s] nome comune.
   1. Nel parametro Address , specifica l’elaborazione [!DNL Insight Server’s] Indirizzo IP.

      È possibile utilizzare un asterisco come carattere jolly nel campo Indirizzo, ad esempio 10.10.116.&#42;, per semplificare il clustering. Vedi [Informazioni sui livelli di accesso](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a).

      L&#39;esempio seguente definisce un cluster contenente due [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Se i server sono connessi a più reti, ripetere il passaggio 6 per aggiungere l&#39;elaborazione [!DNL Insight Servers] a NetworkLocations per tali reti.

   L&#39;esempio seguente mostra un cluster di quattro [!DNL Insight Servers] collegati a due reti (&quot;Intranet aziendale&quot; e &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL Temp] e seleziona **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Aggiornamento del file di controllo di accesso per un cluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Per utilizzare [!DNL Insight Servers] in un cluster, ciascuno [!DNL Insight Server] nel cluster (compreso il master [!DNL Insight Server]) deve appartenere al gruppo di controllo di accesso Cluster Server. Il gruppo Cluster Server identifica i server (per indirizzo IP) autorizzati a partecipare al cluster. Anche se questo file viene mantenuto e amministrato sul master [!DNL Insight Server], viene utilizzato da tutti i [!DNL Insight Servers] nel cluster.

**Per modificare il file di controllo di accesso**

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del master [!DNL Insight Server] e fai clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], apri la directory Controllo accessi .
1. Per aprire la [!DNL Access Control.cfg] file:

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* e fai clic su **[!UICONTROL Make Local]**.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Espandere la struttura dei gruppi di controllo di accesso, quindi espandere AccessGroup (Cluster Server).
1. Per ogni [!DNL Insight Server] nel cluster (compreso il master [!DNL Insight Server]), procedi come segue:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL Members]** e fai clic su **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Specifica la [!DNL Insight Server’s] Indirizzo IP (indirizzo IP numerico, non nome). Se la [!DNL Insight Servers] sono connessi a più reti, questo AccessGroup deve contenere solo gli indirizzi interni che [!DNL Insight Servers] utilizzo per la comunicazione inter-server all&#39;interno del cluster.

      Di seguito viene illustrato AccessGroup (Cluster Server) per un cluster di quattro [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL Temp] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configurazione del file di sincronizzazione {#section-d23e751771c84da6bab6a34a8db867bc}

Per configurare la copia centrale del [!DNL Synchronize.cfg] file. La copia centrale di questo file viene mantenuta sul master [!DNL Insight Server]. Elaborazione [!DNL Insight Servers] nel cluster avvia la comunicazione con il master [!DNL Insight Server] per recuperare una copia aggiornata del file.

La [!DNL Synchronize.cfg] specifica la posizione del master [!DNL Insight Server]. Identifica inoltre il set di file amministrativi che ogni elaborazione [!DNL Insight Servers] nel cluster recupera dal master [!DNL Insight Server]. Elaborazione [!DNL Insight Servers] scaricare automaticamente questi file dal master [!DNL Insight Server] quando iniziano. Inoltre, recuperano in modo dinamico le copie aggiornate di questi file dal master [!DNL Insight Server] quando i file cambiano.

>[!NOTE]
>
>Anche se si configura il [!DNL Synchronize.cfg] file sul master [!DNL Insight Server], il comandante [!DNL Insight Server] non utilizza questo file. Aggiorna il file sul master [!DNL Insight Server] in modo che sia configurato correttamente durante l&#39;elaborazione [!DNL Insight Servers] recupera il file.

**Per aggiornare il file Synchronize.cfg sul master[!DNL Insight Server]**

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del master [!DNL Insight Server] e fai clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], apri **[!UICONTROL Components]** per la directory Server di elaborazione.

1. Esegui le seguenti operazioni per aprire [!DNL Synchronize.cfg]:

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* e fai clic su **[!UICONTROL Make Local]**.

   1. Fai clic con il pulsante destro del mouse sul pulsante [!DNL Temp] segno di spunta e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Espandi la struttura del componente.
1. Nel parametro Indirizzo server principale cluster specificare l&#39;indirizzo IP del master (primario) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Creazione di un registro che registra ogni volta che si verifica la sincronizzazione tra il master [!DNL Insight Server] e la trasformazione [!DNL Insight Servers], assicurati che il parametro Enable Synchronization Log sia impostato su &quot;true&quot;.

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL Temp] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configurazione della posizione del set di dati (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Eseguire la procedura seguente se si desidera eseguire l&#39;elaborazione [!DNL Insight Servers] mantenere [!DNL temp.db] (il set di dati) in una directory o unità diversa dalla posizione predefinita o se si desidera distribuire [!DNL temp.db] su più unità.

>[!NOTE]
>
>Perché l&#39;elaborazione [!DNL Insight Servers] tutti condividono lo stesso [!DNL Disk Files.cfg], tutti devono supportare i percorsi dei file specificati nel file. Ad esempio, se assegni [!DNL temp.db] all&#39;E: unità, ogni elaborazione [!DNL Insight Server] nel cluster deve essere presente una E: guida.

**Per configurare il percorso di temp.db**

1. In [!DNL Insight], sul [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del master [!DNL Insight Server] e fai clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], apri **[!UICONTROL Components for Processing Servers]** directory.

1. Esegui le seguenti operazioni per aprire [!DNL Disk Files.cfg]:

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* e fai clic su **[!UICONTROL Make Local]**.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta nel [!DNL Temp]e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Espandere la struttura DiskSpaceManagerComponent, quindi espandere l&#39;elenco File disco.
1. Modifica la voce 0 per modificare la posizione del [!DNL temp.db] file.
1. Per la distribuzione [!DNL temp.db] su più unità, utilizza i passaggi seguenti per creare una voce aggiuntiva per ogni unità aggiuntiva.

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL Disk Files]** e fai clic su **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Nella nuova voce, specifica il percorso in cui desideri. [!DNL temp.db] scritto.
   Di seguito sono riportate le immagini [!DNL temp.db] scritto su quattro unità.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Salva le modifiche al server eseguendo le operazioni seguenti:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta per il file nel [!DNL Temp] e fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
