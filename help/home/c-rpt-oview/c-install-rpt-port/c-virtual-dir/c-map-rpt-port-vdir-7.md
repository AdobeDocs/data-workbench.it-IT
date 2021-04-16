---
description: Passaggi per mappare il Report Portal (Portale dei rapporti) in una directory virtuale (IIS 7.0 o versione successiva).
title: Mappatura del Report Portal (Portale dei rapporti) a una directory virtuale (IIS 7.0 o versione successiva)
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
exl-id: 2fa3439a-1fe5-4a20-83db-d233ae8b5263
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 5%

---

# Mappatura del Report Portal (Portale dei rapporti) a una directory virtuale (IIS 7.0 o versione successiva){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

Passaggi per mappare il Report Portal (Portale dei rapporti) in una directory virtuale (IIS 7.0 o versione successiva).

Attualmente, la maggior parte dei client Managed Service dispone di server con il sistema operativo Windows Server 2008 e il server Web IIS 7.0 o superiore.

## Prerequisiti {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Assicurati che i componenti ASP e [!DNL ASP.Net] siano installati per IIS 7.0 o versione successiva.
* Assicurati che l&#39;utente Web IIS abbia [!DNL Modify] accesso al file [!DNL E:\Portal\data\users.mdb]. Per modificare tale impostazione, fai clic con il pulsante destro del mouse sul file **[!UICONTROL users.mdb]** e, in [!DNL Properties], vai alla scheda [!DNL Security] . Se l&#39;utente Web IIS non viene visualizzato o non è in grado di aggiungere l&#39;utente Web IIS all&#39;elenco, è sufficiente assegnare al gruppo [!DNL Users] l&#39;accesso [!DNL Modify].

* Assicurati che qualsiasi account utente venga utilizzato per eseguire le [!DNL Application Pools] abbia anche [!DNL Modify] accesso alle cartelle [!DNL E:\Portal\data\users.mdb] e  [!DNL C:\Windows\Temp\] .

## Passaggi di installazione {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. Sul computer in cui è installato [!DNL Report Portal], avviare il percorso [!DNL IIS Manager]:

   **[!UICONTROL Start]** (Analytics) > **[!UICONTROL Administrative Tools]** (Componenti) > **[!UICONTROL Internet Information Services (IIS) Manager]** (Progetti programmati).

1. Seleziona **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Fai clic con il pulsante destro del mouse su **[!UICONTROL Default Web Site]** e seleziona **[!UICONTROL Add Virtual Directory]**.

1. Per un alias, immetti Portal.
1. Per il percorso fisico, immettere [!DNL E:\Portal\PortalASP].
1. Fai clic su **[!UICONTROL OK]**.

   La directory virtuale creata viene visualizzata sotto il simbolo [!DNL Default Web Site].

1. Aggiungi le seguenti directory virtuali nella directory virtuale appena creata.

   | Crea alias... | Per questa risorsa fisica |
   |---|---|
   | Core | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Immagini | [!DNL E:\Portal\PortalFiles\Images] |
   | Uscita | Posizione fisica della directory in cui [!DNL Report Server] salva l&#39;output per i set di rapporti. La cartella di output può trovarsi ovunque e può essere denominata qualsiasi cosa. Contiene una sottocartella per ciascun set di rapporti. È possibile eliminare [!DNL E:\Portal\PortalFiles\Output], ma spostare [!DNL profiles.xml] nella posizione fisica del file di output. |

1. Al termine, verificare che IIS visualizzi quattro nuove directory virtuali. Assicurati che la struttura della directory abbia una cartella principale (con lo stesso nome del portale) e quattro sottocartelle.
1. Fare clic su **[!UICONTROL Application Pools]**, quindi su **[!UICONTROL DefaultAppPool]** (partendo dal presupposto che sia quello configurato con il portale).

1. Fare clic su **[!UICONTROL Advanced Settings]** e selezionare True per abilitare le applicazioni a 32 bit.
1. Per far funzionare il [!DNL Portal], devi convertirlo in un&#39;applicazione. Dopo aver impostato le directory virtuali, fare clic con il pulsante destro del mouse sulla directory virtuale del portale e selezionare **[!UICONTROL Convert to Application]**.

## Suggerimenti aggiuntivi {#section-ff84ab3f66c94620a6a11f0e60471d44}

* È possibile scaricare il file [!DNL Portal] da Softdocs in **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. È sufficiente scaricare il [!DNL ReportPortal-Release-1-0-0-7.zip].

* Non è più necessario il [!DNL ReportPortalSetup.xml], quindi può essere eliminato.
* Per motivi di standardizzazione, inserisci il contenuto di questo file zip in [!DNL E:\Portal].
* Per determinare il server SMTP Per i client di servizi gestiti, vedere qui.
* Inserisci una richiesta con NetOps per modificare la voce del nome di dominio in IIS per il server di report in modo che sia più semplice, ad esempio [!DNL reports.clientname.insight.omniture.com], in modo che l&#39;URL del portale complessivo sia [!DNL http://reports.clientname.insight.omniture.com/Portal]. Configura il file [!DNL email.asa] una volta implementata questa modifica.
