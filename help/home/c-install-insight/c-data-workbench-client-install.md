---
description: Di seguito sono riportati i requisiti e le raccomandazioni per l'installazione della workstation (client) in Workbench dati.
solution: Analytics
title: Requisiti della workstation
topic: Data workbench
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
translation-type: tm+mt
source-git-commit: 2930bd3ae06e700e75144221fc993efdd6bd1e85
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 1%

---


# Requisiti della workstation{#workstation-requirements}

Di seguito sono riportati i requisiti e le raccomandazioni per l&#39;installazione della workstation (client) in Workbench dati.

Per ulteriori requisiti di sistema per Workbench dati, consulta Requisiti [di sistema per](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html) server.

>[!IMPORTANT]
>
>I componenti server, server di report e client vengono aggiornati per essere eseguiti sui sistemi operativi Windows a 64 bit.

**Prima di iniziare**

Prima di installare Workbench dati Workstation (Client), assicurarsi che le attività seguenti siano state completate:

* **Aggiungi** processi ****** esclusi per *MS System Center Endpoint Protection nei server* Windows 2012 per i seguenti eseguibili:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**
   In questo modo verranno abilitati i diritti di elenco per questi eseguibili di interfaccia.

* **Installate Microsoft Excel per esportare i dati di analisi.** Per esportare i dati dalle aree di lavoro come file di Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx]), nel computer in cui si installa Workbench dati deve essere installato Excel e registrato. Se Excel non è stato registrato e Workbench dati tenta di accedervi per la prima volta, verrà visualizzata una finestra di dialogo di registrazione. Se non si è certi che la copia sia registrata, avviare Excel manualmente e, se viene visualizzata una finestra di dialogo di registrazione, completare la procedura di registrazione.

   >[!NOTE]
   >
   >Con il rilascio di Workbench dati 6.4, il supporto per Excel 2007 è stato interrotto. Inoltre, poiché Workbench dati viene eseguito solo su Microsoft Windows per l&#39;architettura a 64 bit, è consigliabile installare anche una versione a 64 bit di Microsoft Excel.

* **Installazione di Adobe[!DNL Acrobat]per la stampa di aree di lavoro ridimensionate in PDF.** Per stampare le aree di lavoro ridimensionate in formato Adobe PDF, nel computer in cui è installato Workbench dati deve essere installato Adobe [!DNL Acrobat] .

* **Accesso a una stampante per le aree di lavoro di stampa.** Per stampare le aree di lavoro da Workbench dati, il computer in cui è installato Workbench dati deve disporre dell&#39;accesso a una stampante. Workbench dati è in grado di stampare le aree di lavoro su stampanti a colori o monocromatiche e non richiede l&#39;utilizzo di postscript o di altre funzioni avanzate per la stampante. Per risultati ottimali, Adobe consiglia di stampare a colori le aree di lavoro.
* **Implementare le misure di sicurezza.** Per i computer Workbench dati, attenersi alle normali politiche aziendali di protezione. Per soddisfare i suoi scopi primari, Workbench dati richiede solo la possibilità di connettersi a un server (attraverso le porte 80 e 443) e a qualsiasi server che raccoglie dati. È possibile utilizzare l&#39;hardware Workbench dati per qualsiasi altro scopo, purché si mantenga il software Workbench dati e si allocino almeno 10 GB di spazio di archiviazione per Workbench dati.
* Per eseguire il rendering accurato delle visualizzazioni, nel computer in cui viene installato il workbench deve essere installato un adattatore **** grafico appropriato (vedere i requisiti dell&#39;adattatore grafico di seguito).

**Requisiti del client Workbench dati**

**Sistema operativo**

* Microsoft Windows 7 a 64 bit
* Microsoft Windows 8.1 a 64 bit
* Microsoft Windows 10 a 64 bit

>[!NOTE]
>
>Windows XP non è supportato per Workbench dati 6.1 e versioni successive.

**Risoluzione**

* Obbligatorio: 1024 x 768 (XGA)
* Consigliato: 1920 x 1200 (WUXGA)

**Scheda grafica**

* Obbligatorio: Accelerazione hardware OpenGL per supportare OpenGL 3.2
* Consigliato: Adattatore video dedicato (ad esempio, scheda NVIDIA o ATI)

**Processore**

* Obbligatorio: 1,2 GHz o superiore Intel o AMD
* Consigliato: Classe ICore 2 Duo

**RAM**

* Obbligatorio: 2 GB
* Consigliato: 4 GB

**Connettività**

* Obbligatorio: Collegamento 512 Kbps al DPU
* Consigliato: 2 Mbps o collegamento più veloce al DPU

**File system**

NTFS

**Archiviazione su disco**

Almeno 10 (10) GB di spazio libero su disco rigido

**Stampa**

Accesso alla stampante (stampanti a colori o in scala di grigi) per aree di lavoro e rapporti di stampa

**Altre**

* Mouse dedicato
* Ambiente di lavoro a basso impatto
* Monitor con superficie opaca

