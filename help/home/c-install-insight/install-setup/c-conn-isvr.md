---
description: Dopo aver installato il software Insight e il certificato digitale, è necessario avviare Insight e configurarne la connessione a Insight Server.
title: Configurazione della connessione a Insight Server
uuid: 8ba13da6-8749-49fe-a29e-dac3906f71b8
exl-id: 6a87e972-069a-435c-9bac-23b20f165ebb
source-git-commit: 232117a8cacaecf8e5d7fcaccc5290d6297947e5
workflow-type: tm+mt
source-wordcount: '836'
ht-degree: 1%

---

# Configurazione della connessione a Insight Server{#configuring-the-connection-to-insight-server}

Dopo aver installato il software Insight e il certificato digitale, è necessario avviare Insight e configurarne la connessione a Insight Server.

>[!NOTE]
>
>In alcuni casi, la connessione a Insight Server potrebbe essere stata preconfigurata dai servizi di consulenza Adobe o dall’amministratore di sistema. In tal caso, non è necessario completare questa attività.

Quando si avvia Insight per la prima volta, si connette automaticamente al server licenze Adobe per registrare il certificato digitale. Per completare correttamente il processo di registrazione, è necessario che il computer sia connesso a Internet quando si eseguono i seguenti passaggi.

>[!NOTE]
>
>Se hai già richiesto, scaricato e installato un certificato pre-bloccato come descritto in [Download e installazione del certificato digitale](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#topic-fed3b44e472c4e4ca6dd5852af14cdb9), Insight non tenterà di connettersi al server licenze e non verrà visualizzato un errore.

**Per configurare la connessione a Insight Server**

Quando si lavora in un ambiente cluster, Insight deve essere configurato per accedere al server Insight master per evitare problemi di sincronizzazione. In Insight è possibile visualizzare informazioni sull&#39;elaborazione [!DNL Insight Servers] nel cluster utilizzando la voce di menu [!DNL Related Servers] in [Server Manager](https://experienceleague.adobe.com/docs/data-workbench/using/client/admin-ui/c-svrs-mgr.html).

1. Avvia Insight.
1. In [!DNL Worktop], fai clic su **[!UICONTROL Admin]**, quindi **[!UICONTROL First Steps]**.

1. Fai clic sulla miniatura **[!UICONTROL Configure Connection to Servers]**.

   Vengono visualizzati il file [!DNL Servers Manager], il file [!DNL Insight.cfg] e le istruzioni per la configurazione del file [!DNL Insight.cfg].

1. Nella finestra [!DNL Insight.cfg], fai clic con il pulsante destro del mouse su **[!UICONTROL Servers]** e fai clic su **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddChild.png)

1. Completare o modificare i parametri del server per consentire a Insight di accedere al server Insight principale. Per descrizioni dettagliate dei parametri nel file Insight.cfg, consulta [Parametri di configurazione](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-insght-config-param.html).

   ![](assets/cfg_Workstation_AddServer.png)

1. Ripetere i passaggi 4 e 5 per ogni Insight Server a cui si desidera configurare una connessione.
1. Per salvare le modifiche di configurazione, fai clic con il pulsante destro del mouse su **[!UICONTROL Insight.cfg (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save as Insight.cfg]**.

   Insight tenta di connettersi a [!DNL Insight Server(s)] utilizzando le impostazioni specificate. Se viene stabilita una connessione, nel [!DNL Servers Manager] viene visualizzato un nodo verde, come illustrato nella pagina seguente.

   ![](assets/vis_SysStat_RedGreenDots.png)

   * **Verde:** indica che la connessione a Insight Server è attiva.
   * **Rosso chiaro:** indica un potenziale problema con il server, ad esempio uno scarico sull&#39;elaborazione del server, un uso elevato della memoria o uno spazio su disco insufficiente.
   * **Rosso:** indica che la connessione a Insight Server non è attiva.

   Se Insight non è in grado di connettersi utilizzando le impostazioni specificate, nel [!DNL Servers Manager] viene visualizzato un nodo rosso. In questo caso, consulta [Risoluzione dei problemi di connessione](../../../home/c-install-insight/install-setup/t-conn-trbsh.md#task-034e588c5ce04c4a8f6d0097364d3b2b).

<!--
c_dir_crt_setup.xml
-->

Quando selezioni un profilo da utilizzare, le informazioni di profilo (compresi i dati correlati e eventuali aree di lavoro o visualizzazioni specifiche definite per il profilo) vengono scaricate nel computer. Durante il download di ciascun profilo, Insight crea una cartella all’interno della directory di installazione utilizzando il nome del profilo.

Ad esempio, se selezioni un profilo denominato Vendite, nella directory Insight viene visualizzata una cartella denominata Vendite . Questa cartella contiene le metriche, le dimensioni, le aree di lavoro e le visualizzazioni definite nel profilo Vendite. Dopo il caricamento iniziale del profilo, il profilo può essere utilizzato quando si lavora offline. Vedere [Utilizzo offline e online](https://experienceleague.adobe.com/docs/data-workbench/using/client/c-off-on.html).

Inoltre, quando ci si connette a Insight Server per la prima volta da Insight Server, Insight Server crea le seguenti directory nella directory di installazione di Insight.

* **[!DNL Trace]directory:** All’interno della  [!DNL Trace] directory si trova il file di log Insight (  [!DNL insight.log]). Quando le dimensioni del file [!DNL Insight.log] raggiungono i 100 MB, il file viene rinominato in [!DNL insight-1.log]. Se esiste già un file con il nome [!DNL insight-1.log], [!DNL insight-1.log] viene rinominato come [!DNL insight-2.log] e così via, con un massimo di [!DNL insight-9.log]. Il file [!DNL insight.log] contiene sempre le informazioni di registro più recenti e [!DNL insight-max.log] contiene il file meno recente.

* **[!DNL User]directory:** all’interno della  [!DNL User] directory sono presenti cartelle che corrispondono a ciascun profilo utilizzato fino a oggi e all’interno di ciascuna cartella di profilo sono presenti cartelle denominate  [!DNL Work] e  [!DNL Workspaces]. La directory `User\*profile name*\Workspaces` è la posizione predefinita in cui vengono salvati i file dell’area di lavoro di Insight. `User\*profile name*\Work` è la posizione predefinita in cui vengono salvate le visualizzazioni di Insight e altre operazioni personalizzate eseguite dall’utente di Insight.

Nella tabella seguente sono elencate le posizioni predefinite dei componenti a cui si accede di frequente.

<table id="table_0254A8C25AF5400F89F87A242746D07E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Posizione directory </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Visualizzazioni salvate </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>nome profilo</i>\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Spazi di lavoro salvati <span class="wintitle"></span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>nome profilo</i>\Workspaces\<i>nome scheda</i>\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File salvati<span class="filepath"> .png</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>nome profilo</i>\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cache dati </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\Cache.db </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="filepath"> Insight.</span> logfile </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Trace\ </p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
c_config_file_ent.xml
-->

Per individuare rapidamente una voce, è possibile eseguire una ricerca in base al nome, al tipo di chiave o al valore, per rimuovere la necessità di scorrere file espansi di grandi dimensioni per informazioni nidificate. È possibile individuare nomi di dimensioni, nomi di server e così via. L&#39;esempio seguente mostra le corrispondenze per una ricerca nella mappa delle frasi.

![](assets/cfg_search.PNG)

Digita una frase di ricerca in questo campo per individuare i dati. A seconda del successo di una corrispondenza, cambia il colore del campo. Le corrispondenze vengono evidenziate e le non corrispondenze sono disattivate. In assenza di corrispondenze, lo sfondo del campo di ricerca diventa rosso. Quando si preme Invio, l&#39;albero di configurazione espande ogni punto in cui c&#39;è una corrispondenza e comprime dove non c&#39;è una corrispondenza.

Puoi inoltre utilizzare espressioni regolari nel campo [!DNL Search] . Ad esempio, puoi utilizzare i seguenti: [!DNL *zip.*] per qualsiasi voce contenente la parola &quot;zip&quot;.

Per cancellare una ricerca, premere **[!UICONTROL Escape]**.
