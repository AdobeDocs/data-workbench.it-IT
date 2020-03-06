---
description: Per il funzionamento di alcune delle funzionalità di Report Server, è necessario fornire e configurare hardware o software prima di eseguire l'installazione.
solution: Analytics
title: Prima di iniziare
topic: Data workbench
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Prima di iniziare{#before-you-begin}

Per il funzionamento di alcune delle funzionalità di Report Server, è necessario fornire e configurare hardware o software prima di eseguire l&#39;installazione.

## Requisiti di base del server di report {#section-e891eaee79fe4fa98e658426dc3b2777}

I rapporti che vengono generati possono essere sotto forma di immagini .PNG o fogli di calcolo .XLS inseriti in un file system o come e-mail. I requisiti hardware sono identici al client [workbench](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements)dati.

Per il server di report sono presenti i seguenti requisiti:

* Accesso al file system per l&#39;output di dati (condivisione di rete o unità locale).
* Accesso al server SMTP configurato.
* Microsoft Excel 2010 a 64 bit o superiore installato sul [!DNL Report] server. Per ulteriori informazioni, vedere [Considerazioni sull&#39;automazione di Office](http://support.microsoft.com/kb/257757) lato server.

## Requisiti aggiuntivi {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Installare una scheda grafica appropriata.** Per eseguire correttamente il rendering dei report, nel computer in cui si installa [!DNL Report] Server deve essere installato un adattatore grafico appropriato.

* **Installate Microsoft Excel per generare rapporti come file Excel.** Per generare e distribuire i rapporti come file di Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx]), nel computer in cui si installa il server di report deve essere installata e registrata la versione appropriata di Microsoft Excel a 64 bit. Se Excel non è stato registrato e il server di report tenta di accedervi per la prima volta, verrà visualizzata una finestra di dialogo di registrazione. Se non si è certi che la copia sia registrata, avviare Excel manualmente e, se viene visualizzata una finestra di dialogo di registrazione, completare la procedura di registrazione.

   >[!NOTE]
   >
   >Quando generate rapporti come file Excel, state aprendo una nuova istanza di Excel. Per ulteriori informazioni su questo processo, vedere [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).

* **Fornire l&#39;accesso a un server SMTP per distribuire i rapporti per e-mail.** Se desiderate distribuire i rapporti tramite e-mail, il server di report deve essere in grado di connettersi a un server SMTP e devono essere aperte le porte appropriate al servizio di inoltro e-mail.

