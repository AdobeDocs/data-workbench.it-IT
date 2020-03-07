---
description: I livelli di accesso descrivono gli URI che un gruppo di utenti può leggere o modificare sul computer.
solution: Insight
title: Informazioni sui livelli di accesso
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni sui livelli di accesso{#understanding-access-levels}

I livelli di accesso descrivono gli URI che un gruppo di utenti può leggere o modificare sul computer.

Per definire i livelli di accesso desiderati per gli utenti dell’organizzazione, effettuate le seguenti operazioni:

* URI specifici senza carattere barra finale limitano l&#39;accesso a tale URI. Ad esempio, [!DNL /Components/Communications.cfg] fornisce l&#39;accesso solo al [!DNL Communications.cfg]file.

* Una barra finale (/), che specifica una directory, consente ai membri del gruppo di accedere a qualsiasi URI che inizia con tale stringa. Ad esempio, /Profiles/ fornisce l&#39;accesso all&#39;intera directory Profili.
* Un simbolo di dollaro finale ($) limita l&#39;accesso all&#39;URI esatto, anche se si tratta di una directory. Ad esempio, /Profiles/$ fornisce l&#39;accesso per leggere la directory principale Profili, ma non per leggere alcun file all&#39;interno di tale directory.

   Per accedere a file specifici, non è necessario utilizzare un $ finale.

   Ad esempio, [!DNL /Components/Communications.cfg] e [!DNL /Components/Communications.cfg$] fornire lo stesso accesso.

* Un simbolo percentuale (%) può essere utilizzato con CN (Common Name) per consentire l&#39;accesso. Ad esempio, /Users/%CN%/ consente l&#39;accesso alla directory Utente che corrisponde al nome comune del certificato SSL dell&#39; [!DNL Insight] utente. Questa sintassi può essere utilizzata solo una volta in un URI.

Gli URI nei gruppi di controllo di accesso predefiniti sono stati configurati come segue:

<table id="table_8E6FDD741BF24E2DAD96A2919FAE6C7F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome gruppo </th> 
   <th colname="col2" class="entry"> Accesso in sola lettura </th> 
   <th colname="col3" class="entry"> Accesso in lettura e scrittura </th> 
   <th colname="col4" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Amministratori </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/ </p> </td> 
   <td colname="col4"> <p>Accesso in lettura e scrittura a tutte le directory di <span class="keyword"> Insight Server</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensori </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Accesso in lettura e scrittura ai due file che i <span class="wintitle"> sensori</span> utilizzano per comunicare con <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utenti </p> </td> 
   <td colname="col2"> <p>/Profili/ </p> <p>/Stato/ </p> <p>/Software/ </p> <p>/Indirizzi/ </p> <p>/Utenti/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>Accesso in lettura e scrittura alla directory Utente che corrisponde al nome comune del certificato SSL dell’utente <span class="keyword"> Insight</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Power Users </p> </td> 
   <td colname="col2"> <p>/Profili/$ </p> <p>/Stato/ </p> <p>/Software/ </p> <p>/Indirizzi/ </p> <p>/Utenti/$ </p> </td> 
   <td colname="col3"> <p>/Profili/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>Gli utenti di alimentazione possono avere lo stesso accesso degli utenti, con la possibilità di scrivere nella directory Profili. Questi utenti possono modificare i profili e consentire l’aggiornamento automatico delle modifiche per altri utenti di <span class="keyword"> Insight</span> , ad esempio per la distribuzione di aree di lavoro di nuova definizione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server cluster </p> </td> 
   <td colname="col2"> <p>/Components for Processing Servers/ </p> <p>/Indirizzi/ </p> <p>/Profili/ </p> <p>/Searchups/ </p> <p>/Access Control/ </p> <p>/Bin/ </p> <p>/Registri/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>Accesso in lettura e scrittura alla directory Cluster. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server di report </p> </td> 
   <td colname="col2"> <p>/Profili/$ </p> <p>/Stato/ </p> <p>/Software/ </p> <p>/Indirizzi/ </p> <p>/Utenti/$ </p> </td> 
   <td colname="col3"> <p>/Profili/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>Ai computer dei report è consentito lo stesso accesso di Power Users, con la possibilità di scrivere nel file <span class="filepath"> ReportStatus.vsp</span> . </p> </td> 
  </tr> 
 </tbody> 
</table>

**Per configurare il controllo di accesso**

Quando si definiscono i gruppi di controllo di accesso, è necessario includere tutti gli amministratori di sistema, gli utenti, i server cluster e gli utenti del server di report che richiedono l&#39;accesso a questo [!DNL Insight Server] computer. Potete concedere l’accesso utilizzando l’indirizzo IP o le informazioni sul certificato SSL, ad esempio il nome comune o l’organizzazione.

>[!NOTE]
>
>Quando il [!DNL Access Control.cfg] file viene modificato su [!DNL Insight Server], tutte le connessioni esistenti vengono interrotte e forzate a riconnettersi. Le connessioni vengono verificate in base alle autorizzazioni nel [!DNL Access Control.cfg] file aggiornato. Nell&#39;interfaccia Server Manager, l&#39; [!DNL Insight Server] icona diventa temporaneamente rossa e quindi nuovamente verde perché la connessione viene terminata e forzata a riconnettersi con tutti gli altri.

1. Nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fare clic sulla **[!UICONTROL Servers Manager]** miniatura per aprire l&#39;area di lavoro Server Manager.

1. Fare clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] file da configurare e fare clic su **[!UICONTROL Files]**.

1. Nella [!DNL Server Files Manager], fate clic **[!UICONTROL Access Control]** per visualizzarne il contenuto. Il [!DNL Access Control.cfg] file si trova all&#39;interno di questa directory.

1. Fare clic con il pulsante destro del mouse sul segno di spunta nella colonna del nome *del* server per [!DNL Access Control.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella [!DNL Temp] colonna per [!DNL Access Control.cfg].

1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato nella [!DNL Temp] colonna e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Nella [!DNL Access Control.cfg] finestra, fate clic **[!UICONTROL Access Control Groups]** per visualizzarne il contenuto.

   ![](assets/access_ctrl_cfg.png)

1. Per aggiungere un nuovo gruppo di controllo di accesso:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL Access Control Groups]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL Members]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      I membri per i gruppi predefiniti non sono predefiniti. Per impostazione predefinita, l&#39;accesso dell&#39;amministratore è concesso a 127.0.0.1 (host locale) e [!DNL Sensor] l&#39;accesso è concesso all&#39;IP:*. Tutti gli altri membri del gruppo di controllo di accesso devono essere definiti.

   1. Completate i parametri.

1. Per aggiungere nuovi membri a un gruppo di controllo di accesso esistente:

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL Members]** nel gruppo di controllo di accesso appropriato e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Salvare il file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e quindi facendo clic **[!UICONTROL Save]**.

1. Per salvare le modifiche apportate localmente al [!DNL Insight Server] computer, fare clic con il [!DNL Server Files Manager]pulsante destro del mouse sul segno di spunta [!DNL Access Control.cfg] nella [!DNL Temp] colonna, quindi fare clic su **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]**>*.

