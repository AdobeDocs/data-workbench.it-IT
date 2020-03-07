---
description: Dopo aver installato il software Insight e il certificato digitale, è necessario avviare Insight e configurarne la connessione a Insight Server.
title: Configurazione della connessione a Insight Server
uuid: 8ba13da6-8749-49fe-a29e-dac3906f71b8
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Configurazione della connessione a Insight Server{#configuring-the-connection-to-insight-server}

Dopo aver installato il software Insight e il certificato digitale, è necessario avviare Insight e configurarne la connessione a Insight Server.

>[!NOTE]
>
>In alcuni casi, la connessione a Insight Server potrebbe essere stata preconfigurata da Adobe Consulting Services o dall&#39;amministratore di sistema. In tal caso, non è necessario completare l&#39;attività.

Quando Insight viene avviato per la prima volta, si connette automaticamente ad Adobe License Server per registrare il certificato digitale. Per completare correttamente il processo di registrazione, è necessario che il computer sia connesso a Internet quando si eseguono i seguenti passaggi.

>[!NOTE]
>
>Se avete già richiesto, scaricato e installato un certificato pre-bloccato come descritto in [Download e installazione del certificato](../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#topic-fed3b44e472c4e4ca6dd5852af14cdb9)digitale, Insight non tenterà di connettersi al server licenze e non si riceverà un errore.

**Per configurare la connessione a Insight Server**

Quando si lavora in un ambiente cluster, Insight deve essere configurato per accedere al server Master Insight per evitare problemi di sincronizzazione. In Insight è possibile visualizzare informazioni sull&#39;elaborazione [!DNL Insight Servers] nel cluster utilizzando la voce di [!DNL Related Servers] menu in [Server Manager](https://docs.adobe.com/content/help/en/data-workbench/using/client/admin-ui/c-svrs-mgr.html).

1. Launch Insight.
1. Sulla [!DNL Worktop], fare clic **[!UICONTROL Admin]**, quindi **[!UICONTROL First Steps]**.

1. Fate clic sulla **[!UICONTROL Configure Connection to Servers]** miniatura.

   Vengono [!DNL Servers Manager]visualizzati il [!DNL Insight.cfg] file e le istruzioni per la configurazione del [!DNL Insight.cfg]file.

1. Nella [!DNL Insight.cfg] finestra fare clic con il pulsante destro del mouse **[!UICONTROL Servers]** e scegliere **[!UICONTROL Add new child]** > **[!UICONTROL Server]**.

   ![](assets/cfg_Workstation_AddChild.png)

1. Completate o modificate i parametri del server per fornire a Insight l&#39;accesso al server Master Insight. Per una descrizione dettagliata dei parametri nel file Insight.cfg, vedete Parametri [di](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-insght-config-param.html)configurazione.

   ![](assets/cfg_Workstation_AddServer.png)

1. Ripetere i passaggi 4 e 5 per ogni server Insight in cui si desidera configurare una connessione.
1. Per salvare le modifiche alla configurazione, fai clic con il pulsante destro del mouse **[!UICONTROL Insight.cfg (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save as Insight.cfg]**.

   Insight tenta di connettersi al [!DNL Insight Server(s)] utilizzando le impostazioni specificate. Se viene stabilita una connessione, nella pagina [!DNL Servers Manager] seguente viene visualizzato un nodo verde.

   ![](assets/vis_SysStat_RedGreenDots.png)

   * **Verde:** Indica che la connessione a Insight Server è attiva.
   * **Rosso chiaro:** Indica un potenziale problema con il server, ad esempio un problema di svuotamento dell&#39;elaborazione del server, un uso elevato della memoria o uno spazio su disco insufficiente.
   * **Rosso:** Indica che la connessione a Insight Server non è attiva.
   Se Insight non è in grado di connettersi utilizzando le impostazioni specificate, nel pannello viene visualizzato un nodo rosso. [!DNL Servers Manager] In questo caso, consultate Risoluzione dei problemi di [connessione](../../../home/c-install-insight/install-setup/t-conn-trbsh.md#task-034e588c5ce04c4a8f6d0097364d3b2b).

<!--
c_dir_crt_setup.xml
-->

Quando si seleziona un profilo da utilizzare, le informazioni del profilo (compresi i dati correlati e eventuali aree di lavoro o visualizzazioni specifiche definite per il profilo) vengono scaricate nel computer. Quando scaricate ciascun profilo, Insight crea una cartella all’interno della directory di installazione utilizzando il nome del profilo.

Ad esempio, se selezionate un profilo denominato Vendite, nella directory Insight viene visualizzata una cartella denominata Vendite. Questa cartella contiene le metriche, le dimensioni, le aree di lavoro e le visualizzazioni definite nel profilo Vendite. Dopo il caricamento iniziale del profilo, il profilo può essere utilizzato quando si lavora offline. Consultate [Lavorare offline e online](https://docs.adobe.com/content/help/en/data-workbench/using/client/c-off-on.html).

Inoltre, quando vi connettete a Insight Server per la prima volta da Insight Server, Insight Server crea le seguenti directory nella directory di installazione di Insight.

* **[!DNL Trace]directory:**All&#39;interno della[!DNL Trace]directory si trova il file di registro di Insight ([!DNL insight.log]). Quando la dimensione del[!DNL Insight.log]file raggiunge i 100 MB, il file viene rinominato in[!DNL insight-1.log]. Se un file con il nome esiste[!DNL insight-1.log]già,[!DNL insight-1.log]viene rinominato in[!DNL insight-2.log], e così via, con un massimo di[!DNL insight-9.log]. Il file contiene[!DNL insight.log]sempre le informazioni di registro più recenti e[!DNL insight-max.log]quelle meno recenti.

* **[!DNL User]directory:**All&#39;interno della[!DNL User]directory sono presenti cartelle che corrispondono a ciascun profilo utilizzato fino alla data, e all&#39;interno di ciascuna cartella di profilo sono presenti cartelle denominate[!DNL Work]e[!DNL Workspaces]. La directory`User\*profile name*\Workspaces`è il percorso predefinito in cui vengono salvati i file dell&#39;area di lavoro di Insight.`User\*profile name*\Work`è il percorso predefinito in cui vengono salvate le visualizzazioni Insight e altre operazioni personalizzate eseguite dall’utente Insight.

Nella tabella seguente sono elencate le posizioni predefinite dei componenti a cui si accede di frequente.

<table id="table_0254A8C25AF5400F89F87A242746D07E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Componente </th> 
   <th colname="col2" class="entry"> Percorso directory </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Visualizzazioni salvate </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>del nome</i>del profilo\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Aree di <span class="wintitle"> lavoro salvate</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>nome</i>del profilo\Workspaces\<i>nome</i>scheda\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>File .png<span class="filepath"> salvati</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\<i>del nome</i>del profilo\Work\ </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cache dati </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\User\Cache.db </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="filepath"> File Insight.log</span> </p> </td> 
   <td colname="col2"> <p><i>Insight</i>\Trace\ </p> </td> 
  </tr> 
 </tbody> 
</table>

<!--
c_config_file_ent.xml
-->

È possibile eseguire ricerche in base a nome, tipo di chiave o valore per individuare rapidamente una voce, per rimuovere la necessità di scorrere file espansi di grandi dimensioni per ottenere informazioni nidificate. È possibile individuare nomi di dimensioni, nomi di server e così via. L&#39;esempio seguente mostra le corrispondenze per una ricerca nella mappa delle frasi.

![](assets/cfg_search.PNG)

Digitare una frase di ricerca in questo campo per individuare i dati. A seconda dell’esito positivo di una corrispondenza, cambia il colore del campo. Le corrispondenze vengono evidenziate e le non corrispondenze risultano attenuate. In assenza di corrispondenze, lo sfondo del campo di ricerca diventa rosso. Quando si preme Invio, la struttura di configurazione si espande ogni punto in cui esiste una corrispondenza e si comprime laddove non esiste una corrispondenza.

È inoltre possibile utilizzare espressioni regolari nel [!DNL Search] campo. Ad esempio, puoi usare re: [!DNL *zip.*]per qualsiasi voce contenente la parola &quot;zip&quot;.

Per cancellare una ricerca, premere **[!UICONTROL Escape]**.
