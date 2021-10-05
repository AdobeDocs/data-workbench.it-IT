---
description: Affinché alcune funzioni di Report Server funzionino, è necessario fornire e configurare hardware o software prima di eseguire l'installazione.
title: Prima di iniziare
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---

# Prima di iniziare{#before-you-begin}

Affinché alcune funzioni di Report Server funzionino, è necessario fornire e configurare hardware o software prima di eseguire l&#39;installazione.

## Requisiti di base del server di rapporto {#section-e891eaee79fe4fa98e658426dc3b2777}

I rapporti che vengono generati possono essere sotto forma di immagini .PNG o fogli di calcolo .XLS inseriti in un file system o come e-mail. I requisiti hardware sono identici al [client di Data Workbench](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements).

Per il server di rapporto esistono i seguenti requisiti:

* Accesso al file system per l&#39;output dei dati (condivisione di rete o unità locale).
* Accesso al server SMTP configurato.
* Microsoft Excel 2010 a 64 bit o superiore installato sul server [!DNL Report]. Per ulteriori informazioni, vedere [Considerazioni sull&#39;automazione lato server di Office](https://support.microsoft.com/kb/257757).

## Requisiti aggiuntivi {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Installare una scheda grafica appropriata.** Per eseguire correttamente il rendering dei rapporti, nel computer in cui si installa  [!DNL Report] Server deve essere installato un adattatore grafico appropriato.

* **Installa Microsoft Excel per generare rapporti come file Excel.** Per generare e distribuire i rapporti come file Microsoft Excel (  [!DNL .xls] o  [!DNL .xlsx]), nel computer in cui si installa Report Server deve essere installata e registrata la versione appropriata di Microsoft Excel a 64 bit. Se Excel non è stato registrato e il server di rapporto tenta di accedervi per la prima volta, verrà visualizzata una finestra di dialogo di registrazione. Se non si è sicuri che la copia sia registrata, avviare Excel manualmente e se viene visualizzata una finestra di dialogo di registrazione, completare il processo di registrazione.

   >[!NOTE]
   >
   >Quando si generano rapporti come file Excel, si apre una nuova istanza di Excel. Per ulteriori informazioni su questo processo, consulta [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).

* **Fornire l’accesso a un server SMTP per distribuire i rapporti tramite e-mail.** Se si desidera distribuire i rapporti tramite e-mail, il server di rapporto deve essere in grado di connettersi a un server SMTP e le porte appropriate al servizio di inoltro e-mail devono essere aperte.
