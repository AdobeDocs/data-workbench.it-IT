---
description: Passaggi per distribuire il dashboard in IIS.
title: Distribuzione del dashboard
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
exl-id: d59efcc3-7405-407d-840a-b5202f418d51
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 5%

---

# Distribuzione del dashboard{#deploying-the-dashboard}

{{eol}}

Passaggi per distribuire il dashboard in IIS.

1. Creare una cartella di installazione per installare il dashboard, ad esempio [!DNL c:\inetpub\wwwroot\dashboard].
1. Crea il pool di applicazioni del dashboard in IIS.
1. Apri la console IIS Manager.
1. Vai a **[!UICONTROL Application Pools]**.
1. Seleziona **[!UICONTROL Add Application Pool…]**nel **[!UICONTROL Actions]** a destra.
1. In **[!UICONTROL Add Application Pool]** Utilizzare il dashboard per il nome e selezionare .NET Framework v.4.0.xxxxxx come versione di .NET Framework.
1. Lascia i campi predefiniti e fai clic su **[!UICONTROL OK]** per creare il pool di applicazioni.
1. Distribuire l&#39;applicazione dashboard.
1. Apri la console IIS Manager.
1. Espandi la **[!UICONTROL Default Web Site]**, dovresti visualizzare la cartella creata in c:\inetpub\wwwroot\dashboard by default.
1. Fai clic con il pulsante destro del mouse sulla cartella e seleziona **[!UICONTROL Convert to Application]**.
1. Seleziona il **[!UICONTROL Application Pool]**creato nel passaggio 2 (ad esempio, &quot;Dashboard&quot;).
1. Sotto **[!UICONTROL Sites]**, fare clic con il pulsante destro del mouse sul sito Web in cui si desidera distribuire (ad esempio, &quot;Sito Web predefinito&quot;).
1. Seleziona **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Individua e seleziona il file di distribuzione del dashboard fornito da Adobe.
1. Fai clic su **[!UICONTROL Next]** due volte per passare alla schermata Inserisci informazioni applicazione.
1. Da questa schermata è possibile scegliere di personalizzare la distribuzione del dashboard.
1. Per **[!UICONTROL Application Path]**, immetti il nome della cartella selezionata in precedenza.
1. Sotto **[!UICONTROL Disable Automatic Database Upgrade]**, inserisci `False`, poiché si tratta di una nuova installazione.
1. Se necessario, personalizza la stringa di connessione. Esempio:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Fai clic su **[!UICONTROL Next]** e IIS inizierà l&#39;installazione dell&#39;applicazione.
1. Una volta completata l&#39;installazione, non dovrebbe essere visualizzato alcun errore nel registro di installazione.
