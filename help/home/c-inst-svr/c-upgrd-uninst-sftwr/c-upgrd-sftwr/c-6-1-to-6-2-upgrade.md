---
description: Aggiornamento dei componenti server per Data Workbench 6.2 e 6.2.2.
title: Aggiornamento del server DWB da 6.1 a 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
exl-id: 094b20f0-bc4a-467a-899e-e1800a624508,20e2cf87-519e-4c27-9201-1275550bb72a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 18%

---

# Aggiornamento del server DWB: da 6.1 a 6.2{#dwb-server-upgrade-to}

{{eol}}

Aggiornamento dei componenti server per Data Workbench 6.2 e 6.2.2.

## Problemi di aggiornamento per la versione 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* Il profilo di attribuzione è configurato per gli utenti che hanno implementato il profilo Adobe SC per utilizzare il feed di dati di Analytics (SC/Insight). Per impostazione predefinita, gli eventi Marketing e Conversione vengono utilizzati come interazioni predefinite valutate nei modelli basati su regole. Vedi [Distribuzione del profilo di attribuzione](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en) per ulteriori informazioni.
* Per gli utenti dell&#39;aggiornamento del profilo di Adobe SC a Data Workbench 6.2, se non utilizzi le configurazioni predefinite, verifica che il [!DNL x-bot_id] nel [!DNL SC Fields.cfg] il file viene decodificato correttamente e il [!DNL x-bot_id] è elencato correttamente in [!DNL Decoding Instructions.cfg] e [!DNL Exclude Hit.cfg] file. Questo sarà un problema solo se hai modificato il file di configurazione dalla configurazione predefinita.
* Se hai eliminato i campi non utilizzati nel [!DNL Dataset > Log Processing > SC Fields.cfg] per il profilo Adobe SC, dovrai aggiornare per contenere i valori di campo aggiornati utilizzati per il profilo di attribuzione (vedi [Distribuzione del profilo di attribuzione](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)).

## Problemi di aggiornamento per la versione 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* La **[!UICONTROL Browsers]** e **[!UICONTROL Operating Systems]** i file di ricerca non verranno aggiornati all’interno della versione precedente **[!UICONTROL Traffic]** profilo (ad esempio, [!DNL Lookups\Traffic\Browsers.txt)]. Invece, la configurazione del **[!UICONTROL Traffic]** Il profilo utilizzerà il bundle DeviceAtlas ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) per fornire queste informazioni di configurazione.
* Workbench dati 6.2.1 sarà l&#39;ultima versione a fornire un download dell&#39;applicazione client a 32 bit. Tutti i futuri download dell&#39;applicazione client saranno a 64 bit e sarà necessario Windows 7 o versioni successive. Le limitazioni di memoria dell&#39;applicazione a 32 bit vengono affrontate con l&#39;introduzione dell&#39;applicazione a 64 bit a partire dalla versione 6.1.

>[!NOTE]
>
>La versione a 32 bit dell’applicazione client Data Workbench può presentare potenziali problemi relativi alle limitazioni di memoria durante l’esecuzione di modelli predittivi utilizzando le funzioni di clustering e punteggio.
