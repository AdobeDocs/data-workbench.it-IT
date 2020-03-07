---
description: Aggiornamento dei componenti server per Workbench dati 6.2 e 6.2.2.
title: Aggiornamento del server DWB da 6.1 a 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Aggiornamento del server DWB: da 6.1 a 6.2{#dwb-server-upgrade-to}

Aggiornamento dei componenti server per Workbench dati 6.2 e 6.2.2.

## Problemi di aggiornamento per la versione 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* Il profilo Attribuzione è configurato per gli utenti che hanno implementato il profilo Adobe SC per utilizzare il feed di dati di Analytics (SC/Insight). Per impostazione predefinita, gli eventi Marketing e Conversion vengono utilizzati come interazioni predefinite valutate nei modelli basati su regole. Per ulteriori informazioni, consulta [Distribuzione del profilo](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html) di attribuzione.
* Per gli utenti del profilo Adobe SC che eseguono l’aggiornamento a Workbench dati 6.2, se non si utilizzano le configurazioni predefinite, verificare che il [!DNL x-bot_id] valore nel [!DNL SC Fields.cfg] file sia decodificato correttamente e che il [!DNL x-bot_id] campo sia elencato correttamente nei [!DNL Decoding Instructions.cfg] file e nei [!DNL Exclude Hit.cfg] file. Questo problema si verifica solo se il file di configurazione è stato modificato dalla configurazione predefinita.
* Se hai eliminato dei campi inutilizzati nel [!DNL Dataset > Log Processing > SC Fields.cfg] file per il profilo Adobe SC, dovrai aggiornarli per adattarli ai valori dei campi aggiornati utilizzati per il profilo di attribuzione (consulta [Distribuzione del profilo](https://docs.adobe.com/help/en/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html)di attribuzione).

## Problemi di aggiornamento per la versione 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* I file **[!UICONTROL Browsers]** e **[!UICONTROL Operating Systems]** di ricerca non verranno aggiornati all&#39;interno del **[!UICONTROL Traffic]** profilo precedente (ad esempio, [!DNL Lookups\Traffic\Browsers.txt)]. Instead, configuration of the **[!UICONTROL Traffic]** profile will utilize the DeviceAtlas bundle ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) to provide this configuration information.
* Workbench dati 6.2.1 sarà l&#39;ultima versione a fornire un download dell&#39;applicazione client a 32 bit. Tutti i futuri download dell&#39;applicazione client saranno a 64 bit e sarà necessario Windows 7 o versioni successive. Le limitazioni di memoria dell&#39;applicazione a 32 bit vengono affrontate con l&#39;introduzione dell&#39;applicazione a 64 bit a partire dalla versione 6.1.

>[!NOTE]
>
>La versione a 32 bit dell&#39;applicazione client Workbench dati può presentare potenziali problemi relativi alle limitazioni di memoria durante l&#39;esecuzione di modelli predittivi utilizzando le funzioni di clustering e punteggio.

