---
description: Aggiornamento dei componenti server per Data Workbench 6.2 e 6.2.2.
title: Aggiornamento del server DWB da 6.1 a 6.2
uuid: 61ecf2c1-9ced-42d3-a010-4a4fec13b987
exl-id: 094b20f0-bc4a-467a-899e-e1800a624508,20e2cf87-519e-4c27-9201-1275550bb72a
source-git-commit: 050468bf6a9ef9c07719ded79c8ab68753d58647
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 18%

---

# Aggiornamento del server DWB: da 6.1 a 6.2{#dwb-server-upgrade-to}

Aggiornamento dei componenti server per Data Workbench 6.2 e 6.2.2.

## Problemi di aggiornamento per la versione 6.2 {#section-3cc74d08f7454d698b5a6d3f1dcde282}

* Il profilo di attribuzione è configurato per gli utenti che hanno implementato il profilo Adobe SC per utilizzare il feed di dati di Analytics (SC/Insight). Per impostazione predefinita, gli eventi Marketing e Conversione vengono utilizzati come interazioni predefinite valutate nei modelli basati su regole. Per ulteriori informazioni, consulta [Distribuzione del profilo di attribuzione](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en) .
* Per gli utenti dell&#39;aggiornamento del profilo Adobe SC alla Data Workbench 6.2, se non utilizzi le configurazioni predefinite, verifica che il valore [!DNL x-bot_id] nel file [!DNL SC Fields.cfg] sia decodificato correttamente e che il campo [!DNL x-bot_id] sia elencato correttamente nei file [!DNL Decoding Instructions.cfg] e [!DNL Exclude Hit.cfg]. Questo sarà un problema solo se hai modificato il file di configurazione dalla configurazione predefinita.
* Se hai eliminato i campi non utilizzati nel file [!DNL Dataset > Log Processing > SC Fields.cfg] per il profilo Adobe SC, dovrai aggiornarli per disporre dei valori di campo aggiornati utilizzati per il profilo di attribuzione (consulta [Distribuzione del profilo di attribuzione](https://experienceleague.adobe.com/docs/data-workbench/using/client/attribution-reports/c-attrib-profile-deploy.html?lang=en)).

## Problemi di aggiornamento per la versione 6.2.2 {#section-8704a9ac358246cd81233dd0982d534f}

* I file di ricerca **[!UICONTROL Browsers]** e **[!UICONTROL Operating Systems]** non verranno aggiornati all’interno del profilo **[!UICONTROL Traffic]** legacy (ad esempio, [!DNL Lookups\Traffic\Browsers.txt)]. Al contrario, la configurazione del profilo **[!UICONTROL Traffic]** utilizzerà il bundle DeviceAtlas ( [!DNL Lookups\DeviceAtlas\DeviceAtlas.bundle]) per fornire queste informazioni sulla configurazione.
* Workbench dati 6.2.1 sarà l&#39;ultima versione a fornire un download dell&#39;applicazione client a 32 bit. Tutti i futuri download dell&#39;applicazione client saranno a 64 bit e sarà necessario Windows 7 o versioni successive. Le limitazioni di memoria dell&#39;applicazione a 32 bit vengono affrontate con l&#39;introduzione dell&#39;applicazione a 64 bit a partire dalla versione 6.1.

>[!NOTE]
>
>La versione a 32 bit dell’applicazione client Data Workbench può presentare potenziali problemi relativi alle limitazioni di memoria durante l’esecuzione di modelli predittivi utilizzando le funzioni di clustering e punteggio.
