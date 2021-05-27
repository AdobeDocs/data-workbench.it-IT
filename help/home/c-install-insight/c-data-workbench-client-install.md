---
description: Di seguito sono riportati i requisiti e le raccomandazioni per l’installazione della workstation (client) in Data Workbench.
title: Requisiti della workstation
uuid: 3c4ba2e8-efbc-45fe-8ac1-923d070bc710
exl-id: 35e259e3-3d6d-45c8-a923-2f8de117489d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 2%

---

# Requisiti della workstation{#workstation-requirements}

Di seguito sono riportati i requisiti e le raccomandazioni per l’installazione della workstation (client) in Data Workbench.

Per ulteriori requisiti di Data Workbench, consulta [Requisiti di sistema del server](https://docs.adobe.com/help/en/data-workbench/using/server-admin-install/c-msr-server.html) .

>[!IMPORTANT]
>
>I componenti server, server di report e client vengono aggiornati per l&#39;esecuzione su sistemi operativi Windows a 64 bit.

**Prima di iniziare**

Assicurati di aver completato le seguenti attività prima di installare Data Workbench Workstation (Client):

* **** ***Processi AddExcluded*** per  *MS System Center Endpoint Protection in Windows 2012* Server per i seguenti eseguibili:

   * **[!DNL InsightServer64.exe]**
   * **[!DNL ReportServer.exe]**
   * **[!DNL ExportIntegration.exe]**

   In questo modo verranno abilitati i diritti inserire nell&#39;elenco Consentiti per questi eseguibili di interfaccia.

* **Installa Microsoft Excel per esportare i dati di analisi.** Per esportare i dati dalle aree di lavoro come file di Microsoft Excel (  [!DNL .xls] o  [!DNL .xlsx]), nel computer in cui si installa Data Workbench deve essere installato e registrato Excel. Se Excel non è stato registrato e Data Workbench tenta di accedervi per la prima volta, viene visualizzata una finestra di dialogo di registrazione. Se non si è sicuri che la copia sia registrata, avviare Excel manualmente e se viene visualizzata una finestra di dialogo di registrazione, completare il processo di registrazione.

   >[!NOTE]
   >
   >Con il rilascio della Data Workbench 6.4, il supporto per Excel 2007 è stato interrotto. Inoltre, poiché Data Workbench viene eseguito solo su Microsoft Windows per l&#39;architettura a 64 bit, è consigliabile installare anche una versione a 64 bit di Microsoft Excel.

* **Installazione di Adobe  [!DNL Acrobat] per la stampa delle aree di lavoro ridimensionate in PDF.** Per stampare le aree di lavoro ridimensionate in formato Adobe PDF, è necessario che nel computer in cui è stata installata la Data Workbench sia  [!DNL Acrobat] installato Adobe.

* **Accesso a una stampante per la stampa delle aree di lavoro.** Per stampare le aree di lavoro da Data Workbench, il computer in cui si installa Data Workbench deve avere accesso a una stampante. Data Workbench può stampare le aree di lavoro su stampanti a colori o monocromatiche e non richiede la postscript o altre caratteristiche avanzate della stampante. Per risultati ottimali, Adobe consiglia di stampare le aree di lavoro a colori.
* **Implementa misure di sicurezza.** Per i computer Data Workbench, attenersi ai normali criteri aziendali di sicurezza. Per soddisfare le sue finalità principali, Data Workbench richiede solo la capacità di connettersi a un server (tramite le porte 80 e 443) e a qualsiasi server che raccoglie dati. È possibile utilizzare l&#39;hardware Data Workbench per qualsiasi altro scopo, purché si mantenga il software Data Workbench e si alloci almeno 10 GB di spazio di archiviazione per la Data Workbench.
* Per eseguire il rendering accurato delle visualizzazioni, nel computer in cui si installa il workbench deve essere installato un **adattatore grafico** appropriato (vedere i requisiti dell&#39;adattatore grafico di seguito).

**Data Workbench requisiti client**

**Sistema operativo**

* Microsoft Windows 7 a 64 bit
* Microsoft Windows 8.1 a 64 bit
* Microsoft Windows 10 a 64 bit

>[!NOTE]
>
>Windows XP non è supportato per Data Workbench 6.1 e versioni successive.

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

* Obbligatorio: Collegamento 512 Kbps alla DPU
* Consigliato: 2 Mbps o un collegamento più veloce alla DPU

**File system**

NTFS

**Archiviazione su disco**

Almeno 10 (10) GB di spazio libero su disco rigido

**Stampa**

Accesso alla stampante (stampanti a colori o in scala di grigi) per aree di lavoro e rapporti di stampa

**Altre**

* Mouse dedicato
* Ambiente di lavoro poco trasparente
* Monitor con superficie opaca
