---
description: Passaggi per distribuire il dashboard in IIS.
title: Distribuzione del dashboard
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 5%

---

# Distribuzione del dashboard{#deploying-the-dashboard}

Passaggi per distribuire il dashboard in IIS.

1. Crea una cartella di installazione per installare il dashboard, ad esempio [!DNL c:\inetpub\wwwroot\dashboard].
1. Crea il pool di applicazioni del dashboard in IIS.
1. Apri la console IIS Manager.
1. Vai a **[!UICONTROL Application Pools]**.
1. Seleziona **[!UICONTROL Add Application Pool…]**nel menu **[!UICONTROL Actions]** a destra.
1. Nel modulo **[!UICONTROL Add Application Pool]**, utilizzare il dashboard per il nome e selezionare .NET Framework v.4.0.xxxxxx come versione di .NET Framework.
1. Lascia come valori predefiniti gli altri campi e fai clic su **[!UICONTROL OK]** per creare il pool di applicazioni.
1. Distribuire l&#39;applicazione dashboard.
1. Apri la console IIS Manager.
1. Espandi il **[!UICONTROL Default Web Site]**, dovresti vedere la cartella creata in c:\inetpub\wwwroot\dashboard by default.
1. Fai clic con il pulsante destro del mouse sulla cartella e seleziona **[!UICONTROL Convert to Application]**.
1. Seleziona il **[!UICONTROL Application Pool]**creato nel passaggio 2 (ad esempio, &quot;Dashboard&quot;).
1. In **[!UICONTROL Sites]**, fare clic con il pulsante destro del mouse sul sito Web in cui si desidera distribuire (ad esempio, &quot;Sito Web predefinito&quot;).
1. Select **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Individua e seleziona il file di distribuzione del dashboard fornito da Adobe.
1. Fare clic due volte su **[!UICONTROL Next]** per passare alla schermata Inserisci informazioni applicazione.
1. Da questa schermata è possibile scegliere di personalizzare la distribuzione del dashboard.
1. Per **[!UICONTROL Application Path]**, immetti il nome della cartella selezionata in precedenza.
1. Alla voce **[!UICONTROL Disable Automatic Database Upgrade]**, immetti `False`, poiché si tratta di una nuova installazione.
1. Se necessario, personalizza la stringa di connessione. Ad esempio:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Fai clic su **[!UICONTROL Next]** e IIS inizierà l&#39;installazione dell&#39;applicazione.
1. Una volta completata l&#39;installazione, non dovrebbe essere visualizzato alcun errore nel registro di installazione.
