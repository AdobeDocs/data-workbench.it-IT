---
description: Passaggi per distribuire il dashboard in IIS.
solution: Analytics
title: Distribuzione del dashboard
topic: Data workbench
uuid: e9a5d62e-9d59-448a-9728-8087aec0fdec
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Distribuzione del dashboard{#deploying-the-dashboard}

Passaggi per distribuire il dashboard in IIS.

1. Create una cartella di installazione per installare il dashboard, ad esempio [!DNL c:\inetpub\wwwroot\dashboard].
1. Creare il pool di applicazioni del dashboard in IIS.
1. Aprite la console Gestione IIS.
1. Vai a **[!UICONTROL Application Pools]**.
1. Selezionare **[!UICONTROL Add Application Pool…]**nel **[!UICONTROL Actions]** menu a destra.
1. Nel **[!UICONTROL Add Application Pool]** modulo, utilizzare il dashboard per il nome e selezionare .NET Framework v.4.0.xxxxxx come versione di .NET Framework.
1. Lasciate gli altri campi come predefiniti e fate clic **[!UICONTROL OK]** per creare il pool di applicazioni.
1. Implementare l&#39;applicazione dashboard.
1. Aprite la console Gestione IIS.
1. Espandete la cartella **[!UICONTROL Default Web Site]**, per visualizzare la cartella creata in c:\inetpub\wwwroot\dashboard by default.
1. Fate clic con il pulsante destro del mouse sulla cartella e selezionate **[!UICONTROL Convert to Application]**.
1. Selezionare il **[!UICONTROL Application Pool]**creato al punto 2 (ad esempio, &quot;Dashboard&quot;).
1. In **[!UICONTROL Sites]**, fare clic con il pulsante destro del mouse sul sito Web a cui si desidera distribuire (ad esempio, &quot;Sito Web predefinito&quot;).
1. Select **[!UICONTROL Deploy]** > **[!UICONTROL Import Application]**.
1. Individuate e selezionate il file di distribuzione del dashboard fornito da Adobe.
1. Fate **[!UICONTROL Next]** due volte clic per passare alla schermata Inserisci informazioni applicazione.
1. Da questa schermata potete scegliere di personalizzare la distribuzione del dashboard.
1. Ad esempio, **[!UICONTROL Application Path]** immettete il nome della cartella precedentemente selezionato.
1. In **[!UICONTROL Disable Automatic Database Upgrade]**, immettere `False`, poiché si tratta di una nuova installazione.
1. Se necessario, personalizzare la stringa di connessione. Ad esempio:

   ```
   Data Source=.;Initial Catalog=thinclientdb;Integrated Security=SSPI;Connect Timeout=30; 
   Application Name=Insight Dashboard;MultipleActiveResultSets=true;
   ```

1. Fate clic su **[!UICONTROL Next]** e IIS inizierà l&#39;installazione dell&#39;applicazione.
1. Una volta completata l&#39;installazione, nel registro di installazione non dovrebbero essere visualizzati errori.
