---
description: I livelli di accesso descrivono gli URI che un gruppo di utenti può leggere o modificare sul computer.
title: Informazioni sui livelli di accesso
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 3%

---

# Informazioni sui livelli di accesso{#understanding-access-levels}

I livelli di accesso descrivono gli URI che un gruppo di utenti può leggere o modificare sul computer.

Segui queste linee guida per definire i livelli di accesso desiderati per gli utenti della tua organizzazione:

* Gli URI specifici senza carattere barra finale limitano l’accesso a tale URI. Ad esempio, [!DNL /Components/Communications.cfg] fornisce l&#39;accesso solo al file [!DNL Communications.cfg].

* Una barra finale (/), che specifica una directory, consente ai membri del gruppo di accedere a qualsiasi URI che inizia con tale stringa. Ad esempio, /Profiles/ fornisce l&#39;accesso all&#39;intera directory Profiles.
* Un simbolo del simbolo del dollaro finale ($) limita l’accesso all’URI esatto, anche se si tratta di una directory. Ad esempio, /Profiles/$ fornisce l&#39;accesso per leggere la directory principale Profiles, ma non per leggere alcun file all&#39;interno di tale directory.

   Per l&#39;accesso a file specifici, non è necessario utilizzare un $ finale.

   Ad esempio, [!DNL /Components/Communications.cfg] e [!DNL /Components/Communications.cfg$] forniscono lo stesso accesso.

* Un simbolo di percentuale (%) può essere utilizzato con CN (Common Name) per consentire l’accesso. Ad esempio, /Users/%CN%/ consente l&#39;accesso alla directory utente corrispondente al nome comune del certificato SSL dell&#39;utente [!DNL Insight]. Questa sintassi può essere utilizzata una sola volta in un URI.

Gli URI nei gruppi di controllo accessi predefiniti sono stati configurati come segue:

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
   <td colname="col4"> <p>Accesso in lettura e scrittura a tutte le directory <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensori </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Accesso in lettura e scrittura ai due file utilizzati da <span class="wintitle"> Sensors</span> per comunicare con <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utenti </p> </td> 
   <td colname="col2"> <p>/Profili/ </p> <p>/Stato/ </p> <p>/Software/ </p> <p>/Indirizzi/ </p> <p>/Utenti/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>Accesso in lettura e scrittura alla directory utente corrispondente al nome comune del certificato SSL dell'utente <span class="keyword"> Insight</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alimentazione </p> </td> 
   <td colname="col2"> <p>/Profili/$ </p> <p>/Stato/ </p> <p>/Software/ </p> <p>/Indirizzi/ </p> <p>/Utenti/$ </p> </td> 
   <td colname="col3"> <p>/Profili/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>Gli utenti di alimentazione possono avere lo stesso accesso degli utenti, con la possibilità di scrivere nella directory Profiles. Questi utenti possono modificare i profili e consentire l’aggiornamento automatico delle modifiche per altri utenti <span class="keyword"> Insight</span>, ad esempio durante la distribuzione di aree di lavoro appena definite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server cluster </p> </td> 
   <td colname="col2"> <p>/Components per l'elaborazione dei server/ </p> <p>/Indirizzi/ </p> <p>/Profili/ </p> <p>/Ricerca/ </p> <p>/Controllo di accesso/ </p> <p>/Bin/ </p> <p>/Registri/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>Accesso in lettura e scrittura alla directory Cluster. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server di rapporto </p> </td> 
   <td colname="col2"> <p>/Profili/$ </p> <p>/Stato/ </p> <p>/Software/ </p> <p>/Indirizzi/ </p> <p>/Utenti/$ </p> </td> 
   <td colname="col3"> <p>/Profili/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>Alle macchine per report è consentito lo stesso accesso di Power Users, con l'aggiunta della possibilità di scrivere nel file <span class="filepath"> ReportStatus.vsp</span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Per configurare il controllo di accesso**

Quando si definiscono i gruppi di controllo degli accessi, è necessario includere tutti gli utenti amministratori di sistema, utenti, server cluster e server di rapporto che richiedono l&#39;accesso a questo [!DNL Insight Server] computer. Puoi concedere l’accesso utilizzando l’indirizzo IP o le informazioni sul certificato SSL, ad esempio il nome comune o l’organizzazione.

>[!NOTE]
>
>Quando il file [!DNL Access Control.cfg] viene modificato in [!DNL Insight Server], tutte le connessioni esistenti vengono interrotte e forzate per riconnettersi. Le connessioni vengono verificate rispetto alle autorizzazioni nel file [!DNL Access Control.cfg] aggiornato. Nell&#39;interfaccia di Server Manager, l&#39;icona [!DNL Insight Server] diventa temporaneamente rossa e quindi di nuovo verde perché la connessione viene terminata e forzata a riconnettersi insieme a tutte le altre.

1. Nella scheda [!DNL Admin] > [!DNL Dataset and Profile] , fai clic sulla miniatura **[!UICONTROL Servers Manager]** per aprire l’area di lavoro Server Manager.

1. Fai clic con il pulsante destro del mouse sull&#39;icona del [!DNL Insight Server] da configurare e fai clic su **[!UICONTROL Files]**.

1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Access Control]** per visualizzarne il contenuto. Il file [!DNL Access Control.cfg] si trova all&#39;interno di questa directory.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nella colonna *nome server* per [!DNL Access Control.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nella colonna [!DNL Temp] per [!DNL Access Control.cfg].

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nella colonna [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. Nella finestra [!DNL Access Control.cfg] fare clic su **[!UICONTROL Access Control Groups]** per visualizzarne il contenuto.

   ![](assets/access_ctrl_cfg.png)

1. Per aggiungere un nuovo gruppo di controllo accessi:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Access Control Groups]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Members]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      I membri per i gruppi predefiniti non sono predefiniti. Per impostazione predefinita, l’accesso dell’amministratore viene concesso a 127.0.0.1 (host locale) e [!DNL Sensor] viene concesso all’IP:*. Devono essere definiti tutti gli altri membri del gruppo di controllo accessi.

   1. Completa i parametri.

1. Per aggiungere nuovi membri a un gruppo di controllo accessi esistente:

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Members]** nel gruppo di controllo accessi appropriato e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Salva il file facendo clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e quindi facendo clic su **[!UICONTROL Save]**.

1. Per salvare le modifiche apportate localmente al computer [!DNL Insight Server], fai clic con il pulsante destro del mouse sul segno di spunta [!DNL Access Control.cfg] nella colonna [!DNL Temp], quindi fai clic su **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]**>*.[!DNL Server Files Manager]
