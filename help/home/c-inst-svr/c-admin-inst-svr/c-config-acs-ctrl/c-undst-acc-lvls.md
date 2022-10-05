---
description: I livelli di accesso descrivono gli URI che un gruppo di utenti può leggere o modificare sul computer.
title: Informazioni sui livelli di accesso
uuid: e9091ae1-9a34-4e00-a928-20d04119ee9e
exl-id: 64e2dc39-1ca1-425b-bec7-acb10a8819c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '665'
ht-degree: 3%

---

# Informazioni sui livelli di accesso{#understanding-access-levels}

{{eol}}

I livelli di accesso descrivono gli URI che un gruppo di utenti può leggere o modificare sul computer.

Segui queste linee guida per definire i livelli di accesso desiderati per gli utenti della tua organizzazione:

* Gli URI specifici senza carattere barra finale limitano l’accesso a tale URI. Ad esempio: [!DNL /Components/Communications.cfg] fornisce accesso al [!DNL Communications.cfg]solo file.

* Una barra finale (/), che specifica una directory, consente ai membri del gruppo di accedere a qualsiasi URI che inizia con tale stringa. Ad esempio, /Profiles/ fornisce l&#39;accesso all&#39;intera directory Profiles.
* Un simbolo del simbolo del dollaro finale ($) limita l’accesso all’URI esatto, anche se si tratta di una directory. Ad esempio, /Profiles/$ fornisce l&#39;accesso per leggere la directory principale Profiles, ma non per leggere alcun file all&#39;interno di tale directory.

   Per l&#39;accesso a file specifici, non è necessario utilizzare un $ finale.

   Ad esempio: [!DNL /Components/Communications.cfg] e [!DNL /Components/Communications.cfg$] fornisci lo stesso accesso.

* Un simbolo di percentuale (%) può essere utilizzato con CN (Common Name) per consentire l’accesso. Ad esempio, /Users/%CN%/ consente l&#39;accesso alla directory utente che corrisponde al nome comune del certificato SSL del [!DNL Insight] utente. Questa sintassi può essere utilizzata una sola volta in un URI.

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
   <td colname="col4"> <p>Accesso in lettura e scrittura a tutti <span class="keyword"> Insight Server</span> directory. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sensori </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p>/SensorInit.vsp </p> <p>/Submit.vsp </p> </td> 
   <td colname="col4"> <p>Accesso in lettura e scrittura ai due file che <span class="wintitle"> Sensori</span> usare per comunicare con <span class="keyword"> Insight Server</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Utenti </p> </td> 
   <td colname="col2"> <p>/Profili/ </p> <p>/Stato/ </p> <p>/Software/ </p> <p>/Indirizzi/ </p> <p>/Utenti/$ </p> </td> 
   <td colname="col3"> /Users/%CN%/ </td> 
   <td colname="col4"> <p>Accesso in lettura e scrittura alla directory utente corrispondente al nome comune del certificato SSL del <span class="keyword"> Insight</span> utente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Alimentazione </p> </td> 
   <td colname="col2"> <p>/Profili/$ </p> <p>/Stato/ </p> <p>/Software/ </p> <p>/Indirizzi/ </p> <p>/Utenti/$ </p> </td> 
   <td colname="col3"> <p>/Profili/ </p> <p>/Users/%CN%/ </p> </td> 
   <td colname="col4"> <p>Gli utenti di alimentazione possono avere lo stesso accesso degli utenti, con la possibilità di scrivere nella directory Profiles. Questi utenti possono modificare i profili e consentire l’aggiornamento automatico delle modifiche per altri utenti <span class="keyword"> Insight</span> , ad esempio quando si distribuiscono aree di lavoro appena definite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server cluster </p> </td> 
   <td colname="col2"> <p>/Components per l'elaborazione dei server/ </p> <p>/Indirizzi/ </p> <p>/Profili/ </p> <p>/Ricerca/ </p> <p>/Controllo degli accessi/ </p> <p>/Bin/ </p> <p>/Registri/ </p> </td> 
   <td colname="col3"> <p>/Cluster/ </p> </td> 
   <td colname="col4"> <p>Accesso in lettura e scrittura alla directory Cluster. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server di rapporto </p> </td> 
   <td colname="col2"> <p>/Profili/$ </p> <p>/Stato/ </p> <p>/Software/ </p> <p>/Indirizzi/ </p> <p>/Utenti/$ </p> </td> 
   <td colname="col3"> <p>/Profili/ </p> <p>/Users/%CN%/ </p> <p>/ReportStatus.vsp </p> </td> 
   <td colname="col4"> <p>Le macchine per report possono avere lo stesso accesso di Power Users, con l'aggiunta della possibilità di scrivere nel <span class="filepath"> ReportStatus.vsp</span> file. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Per configurare il controllo di accesso**

Quando si definiscono i gruppi di controllo degli accessi, è necessario includere tutti gli amministratori di sistema, gli utenti, i server cluster e gli utenti di Report Server che richiedono l&#39;accesso a questo [!DNL Insight Server] computer. Puoi concedere l’accesso utilizzando l’indirizzo IP o le informazioni sul certificato SSL, ad esempio il nome comune o l’organizzazione.

>[!NOTE]
>
>Quando il [!DNL Access Control.cfg] file modificato in [!DNL Insight Server], tutte le connessioni esistenti vengono interrotte e forzate per riconnettersi. Le connessioni vengono verificate in base alle autorizzazioni nell&#39;aggiornamento [!DNL Access Control.cfg] file. Nell&#39;interfaccia Server Manager, la [!DNL Insight Server] l&#39;icona diventa temporaneamente rossa e quindi di nuovo verde perché la connessione viene terminata e forzata a riconnettersi insieme a tutti gli altri.

1. Sulla [!DNL Admin] > [!DNL Dataset and Profile] fai clic sulla scheda **[!UICONTROL Servers Manager]** per aprire l&#39;area di lavoro Server Manager.

1. Fai clic con il pulsante destro del mouse sull’icona [!DNL Insight Server] si desidera configurare e fare clic su **[!UICONTROL Files]**.

1. In [!DNL Server Files Manager], fai clic su **[!UICONTROL Access Control]** per visualizzarne il contenuto. La [!DNL Access Control.cfg] il file si trova all&#39;interno di questa directory.

1. Fai clic con il pulsante destro del mouse sul segno di spunta nel *nome server* colonna per [!DNL Access Control.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta viene visualizzato nel [!DNL Temp] colonna per [!DNL Access Control.cfg].

1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato nel [!DNL Temp] e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Workstation]**.

1. In [!DNL Access Control.cfg] finestra, fai clic su **[!UICONTROL Access Control Groups]** per visualizzarne il contenuto.

   ![](assets/access_ctrl_cfg.png)

1. Per aggiungere un nuovo gruppo di controllo accessi:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL Access Control Groups]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Group]**.

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL Members]** e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

      I membri per i gruppi predefiniti non sono predefiniti. Per impostazione predefinita, l’accesso dell’amministratore viene concesso alla versione 127.0.0.1 (host locale) e [!DNL Sensor] l&#39;accesso è concesso al PI:&#42;. Devono essere definiti tutti gli altri membri del gruppo di controllo accessi.

   1. Completa i parametri.

1. Per aggiungere nuovi membri a un gruppo di controllo accessi esistente:

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL Members]** nel gruppo di controllo accessi appropriato e fai clic su **[!UICONTROL Add new]** > **[!UICONTROL Member]**.

1. Salva il file facendo clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e quindi facendo clic su **[!UICONTROL Save]**.

1. Per salvare le modifiche apportate localmente al [!DNL Insight Server] nella macchina [!DNL Server Files Manager], fai clic con il pulsante destro del mouse sul segno di spunta [!DNL Access Control.cfg] in [!DNL Temp] , quindi fai clic su **[!UICONTROL Save to]** *&lt;**[!UICONTROL server name]**>*.
