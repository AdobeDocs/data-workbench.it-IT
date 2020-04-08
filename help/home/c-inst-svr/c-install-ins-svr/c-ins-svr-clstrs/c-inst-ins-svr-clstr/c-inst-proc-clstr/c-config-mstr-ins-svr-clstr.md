---
description: Informazioni sulla configurazione del cluster nel server Master Insight, sull'aggiornamento del file di controllo degli accessi per un cluster e altro ancora.
solution: Insight
title: Configurazione del server Master Insight per il clustering
uuid: c3ac38e3-79c5-4863-9156-194589a6bcbd
translation-type: tm+mt
source-git-commit: b5a22e7a050d7c01570286dcb54e368f7ecdbcd8

---


# Configurazione del server Master Insight per il clustering{#configuring-the-master-insight-server-for-clustering}

Informazioni sulla configurazione del cluster nel server Master Insight, sull&#39;aggiornamento del file di controllo degli accessi per un cluster e altro ancora.

Per configurare il cluster, eseguite i seguenti passaggi sul master [!DNL Insight Server]:

* Aggiungete i nomi e gli indirizzi [!DNL Insight Servers’] comuni di elaborazione al file dell&#39;indirizzo.
* Aggiungi tutti i componenti [!DNL Insight Servers] al gruppo Server cluster nel [!DNL Access Control.cfg] file.

* Aggiornare il [!DNL Synchronize.cfg] file nella directory Components for Processing Servers in modo che punti al master [!DNL Insight Server].

* Se necessario, modificate il [!DNL Disk Files.cfg] file nella directory Components for Processing Servers per specificare la posizione del [!DNL temp.db] file nell&#39;elaborazione [!DNL Insight Servers].

Per completare questi passaggi, è necessario conoscere i nomi comuni (come specificato nei certificati digitali per i singoli [!DNL Insight Server]) e gli indirizzi IP di ciascun [!DNL Insight Server] cluster. Se non disponete già di queste informazioni, ottenetele prima di procedere.

>[!NOTE]
>
>Le procedure descritte in questa sezione richiedono [!DNL Insight]. Se non avete installato [!DNL Insight], seguite le istruzioni riportate nella **[!DNL Insight]Guida **utente prima di continuare.

## Aggiunta dei server di elaborazione a Insight al file di indirizzo {#section-2fe5298180164e8dbaa59ea6b6ff682d}

Utilizzare la procedura seguente per aggiungere i nomi comuni di elaborazione e gli indirizzi IP al file dell&#39;indirizzo sul master [!DNL Insight Servers’] [!DNL Insight Server]. (Anche se il file dell&#39;indirizzo viene mantenuto e amministrato sul master [!DNL Insight Server], viene utilizzato da tutti gli utenti del [!DNL Insight Servers] cluster.)

>[!NOTE]
>
>Di seguito si presuppone che il file dell&#39;indirizzo sia già stato configurato per il master [!DNL Insight Server]. Se non avete già aggiunto gli indirizzi [!DNL Insight Server’s] IP principali al file indirizzo, completate la procedura descritta in [Definizione del percorso](../../../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/c-svrs-ntwk-loc/c-svrs-ntwk-loc.md#concept-87dd2aa3448c415ca1285bc445a8c649) di rete del server prima di iniziare.

**Per aggiungere l&#39;elaborazione[!DNL Insight Servers]al file dell&#39;indirizzo**

1. Avviate [!DNL Insight] e caricate il profilo di configurazione (se non è già aperto) facendo clic con il pulsante destro del mouse sulla barra del titolo e scegliendo **[!UICONTROL Switch Profile]** > **[!UICONTROL Configuration]**.

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del master **[!UICONTROL Insight Server]** e fare clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], aprite la directory Indirizzi ed effettuate le seguenti operazioni per aprire il file dell&#39; [!DNL Insight Server’s] indirizzo:

   1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server e quindi scegliere **[!UICONTROL Make Local]**.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Espandere i contenuti della [!DNL Locations] struttura, quindi espandere NetworkLocation 0, Indirizzi e DefinizioneIndirizzo.
1. Per aggiungere AddressDefinition a NetworkLocation 0 per ogni elaborazione [!DNL Insight Server] nel cluster, effettuare le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL AddressDefinition]** e scegliere **[!UICONTROL Add New]** > **[!UICONTROL Address Definition]**.

   1. Nel parametro Name specificate il nome [!DNL Insight Server’s] comune di elaborazione.
   1. Nel parametro Address, specificate l&#39;indirizzo [!DNL Insight Server’s] IP di elaborazione.

      È possibile utilizzare un asterisco come carattere jolly nel campo Indirizzo, ad esempio 10.10.116.*, per semplificare il clustering. Vedere [Informazioni sui livelli](../../../../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-undst-acc-lvls.md#concept-6b292edf79214750a8d0525097b8795a)di accesso.

      L&#39;esempio seguente definisce un cluster contenente due [!DNL Insight Servers]:

      ![](assets/cfg_cluster_AddressDefinition1IP.png)

1. Se i server sono connessi a più reti, ripetere il passaggio 6 per aggiungere l&#39;elaborazione [!DNL Insight Servers] alle NetworkLocations per tali reti.

   L&#39;esempio seguente mostra un cluster di quattro reti [!DNL Insight Servers] collegate a due reti (&quot;Intranet aziendale&quot; e &quot;Internet&quot;).

   ![](assets/cfg_cluster_AddressDefinition2IP.png)

1. Salvate le modifiche al server effettuando le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare [!DNL Server Files Manager]clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL Temp] colonna e selezionare **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Aggiornamento del file di controllo dell&#39;accesso per un cluster {#section-fce1367d92a445168c35e9ca506e7d6b}

Per poter essere utilizzati [!DNL Insight Servers] in un cluster, ciascuno [!DNL Insight Server] del cluster (incluso il master [!DNL Insight Server]) deve appartenere al gruppo di controllo di accesso ai server cluster. Il gruppo Server cluster identifica i server (per indirizzo IP) che possono partecipare al cluster. Anche se questo file viene mantenuto e amministrato sul master [!DNL Insight Server], viene utilizzato da tutti gli utenti del [!DNL Insight Servers] cluster.

**Per modificare il file di controllo di accesso**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del master [!DNL Insight Server] e fare clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], aprire la directory Controllo accesso.
1. Per aprire il [!DNL Access Control.cfg] file, effettuate le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server e quindi scegliere **[!UICONTROL Make Local]**.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Espandete la struttura Gruppi di controllo di accesso, quindi espandete AccessGroup (Server cluster).
1. Per ogni [!DNL Insight Server] componente del cluster (incluso il master [!DNL Insight Server]), effettuate le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL Members]** e scegliere **[!UICONTROL Add New]** > **[!UICONTROL New Member]**.

   1. Specificate l&#39;indirizzo [!DNL Insight Server’s] IP (indirizzo IP numerico, non il nome). Se [!DNL Insight Servers] sono connessi a più reti, il gruppo AccessGroup deve contenere solo gli indirizzi interni utilizzati [!DNL Insight Servers] per le comunicazioni tra server all&#39;interno del cluster.

      Di seguito viene illustrato AccessGroup (Cluster Server) per un cluster di quattro [!DNL Insight Servers].

      ![](assets/cfg_cluster_AccessControlMembers.png)

1. Salvate le modifiche al server effettuando le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare [!DNL Server Files Manager]clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL Temp] colonna e scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configurazione del file di sincronizzazione {#section-d23e751771c84da6bab6a34a8db867bc}

Per configurare la copia centrale del [!DNL Synchronize.cfg] file è possibile utilizzare la procedura seguente. La copia centrale di questo file viene mantenuta sul master [!DNL Insight Server]. L&#39;elaborazione [!DNL Insight Servers] nel cluster avvia la comunicazione con il master [!DNL Insight Server] per recuperare una copia aggiornata del file.

Il [!DNL Synchronize.cfg] file specifica la posizione del master [!DNL Insight Server]. Inoltre, identifica il set di file amministrativi che ogni elaborazione [!DNL Insight Servers] nel cluster recupera dal master [!DNL Insight Server]. L&#39;elaborazione scarica [!DNL Insight Servers] automaticamente questi file dal master [!DNL Insight Server] quando iniziano. Inoltre, recuperano dinamicamente copie aggiornate di questi file dal master [!DNL Insight Server] quando i file cambiano.

>[!NOTE]
>
>Anche se configurate il [!DNL Synchronize.cfg] file sullo schema [!DNL Insight Server], lo schema [!DNL Insight Server] stesso non utilizza questo file. Il file viene aggiornato sullo schema [!DNL Insight Server] in modo che venga configurato correttamente al momento del [!DNL Insight Servers] recupero del file da parte dell&#39;elaborazione.

**Per aggiornare il file Synchronize.cfg sul master[!DNL Insight Server]**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del master [!DNL Insight Server] e fare clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], aprire la directory **[!UICONTROL Components]** per Server di elaborazione.

1. Per aprire [!DNL Synchronize.cfg]:

   1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server e quindi scegliere **[!UICONTROL Make Local]**.

   1. Fare clic con il pulsante destro del mouse sul [!DNL Temp] segno di spunta e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Espande la struttura del componente.
1. Nel parametro Indirizzo server principale cluster, specificate l&#39;indirizzo IP del master (primario) **[!UICONTROL Insight Server]**.

   ![](assets/cfg_cluster_SyncFile_CentralCopy.png)

   Per creare un registro che registra ogni volta che si verifica la sincronizzazione tra il master [!DNL Insight Server] e l&#39;elaborazione [!DNL Insight Servers], accertatevi che il parametro Enable Synchronization Log (Abilita registro sincronizzazione) sia impostato su &quot;true&quot;.

1. Salvate le modifiche al server effettuando le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fare clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL Temp] colonna e scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

## Configurazione della posizione del dataset (temp.db) {#section-5ec257a4b4c64fb58baec1f12119a822}

Eseguire la procedura seguente se si desidera che l&#39;elaborazione [!DNL Insight Servers] mantenga [!DNL temp.db] (il dataset) in una directory o in un&#39;unità diversa dalla posizione predefinita oppure se si desidera distribuire [!DNL temp.db] su più unità.

>[!NOTE]
>
>Poiché [!DNL Insight Servers] tutte le elaborazioni condividono lo stesso [!DNL Disk Files.cfg], devono supportare tutti i percorsi di file specificati in questo file. Ad esempio, se assegnate [!DNL temp.db] alla E: ogni elaborazione [!DNL Insight Server] nel cluster deve avere una E: guidare.

**Per configurare il percorso di temp.db**

1. In [!DNL Insight], nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del master [!DNL Insight Server] e fare clic su **[!UICONTROL Server Files]**.

1. In [!DNL Server Files Manager], aprite la **[!UICONTROL Components for Processing Servers]** directory.

1. Per aprire [!DNL Disk Files.cfg]:

   1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server e quindi scegliere **[!UICONTROL Make Local]**.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta nella [!DNL Temp]colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.

1. Espandere la struttura DiskSpaceManagerComponent, quindi espandere l&#39;elenco Disk Files (File disco).
1. Modificate la voce 0 per cambiare la posizione del [!DNL temp.db] file.
1. Se si desidera distribuire [!DNL temp.db] su più unità, procedere come segue per creare una voce aggiuntiva per ogni unità aggiuntiva.

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL Disk Files]** e scegliere **[!UICONTROL Add New]** > **[!UICONTROL Disk File]**.

   1. Nella nuova voce, specificate il percorso in cui [!DNL temp.db] scrivere.
   Di seguito sono riportati [!DNL temp.db] scritti su quattro unità.

   ![](assets/cfg_diskfiles_exampleNewValues.png)

1. Salvate le modifiche al server effettuando le seguenti operazioni:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. In [!DNL Server Files Manager], fare clic con il pulsante destro del mouse sul segno di spunta del file nella [!DNL Temp] colonna e scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

