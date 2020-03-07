---
description: Passaggi per mappare il portale dei report su una directory virtuale (IIS 7.0 o versione successiva).
solution: Analytics
title: Mappatura del portale di report a una directory virtuale (IIS 7.0 o versione successiva)
topic: Data workbench
uuid: 9d18fb85-f9d7-48b6-a19b-1e7b68a5adca
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Mappatura del portale di report a una directory virtuale (IIS 7.0 o versione successiva){#mapping-report-portal-to-a-virtual-directory-iis-or-higher}

Passaggi per mappare il portale dei report su una directory virtuale (IIS 7.0 o versione successiva).

Attualmente, la maggior parte dei client di servizi gestiti dispone di server con il sistema operativo Windows Server 2008 e il server Web IIS 7.0 o versione successiva.

## Prerequisiti {#section-7b1cff24fc4f4c8591540b78de686f2f}

* Accertatevi che ASP e [!DNL ASP.Net] componenti siano installati per IIS 7.0 o versione successiva.
* Verificare che l&#39;utente Web IIS abbia [!DNL Modify] accesso al [!DNL E:\Portal\data\users.mdb] file. È possibile modificare tale impostazione facendo clic con il pulsante destro del mouse sul **[!UICONTROL users.mdb]** file e sotto [!DNL Properties], passare alla [!DNL Security] scheda. Se non viene visualizzato l&#39;utente Web IIS elencato o non è in grado di aggiungere l&#39;utente Web IIS all&#39;elenco, è sufficiente assegnare al [!DNL Users] gruppo l&#39; [!DNL Modify] accesso.

* Verificate che qualsiasi account utente venga utilizzato per eseguire l&#39;account [!DNL Application Pools] disponga anche [!DNL Modify] dell&#39;accesso alle cartelle [!DNL E:\Portal\data\users.mdb] e [!DNL C:\Windows\Temp\].

## Passaggi di installazione {#section-2a6476a221fa43dfa91866c0d41f82e5}

1. Nel computer in cui [!DNL Report Portal] è installato, avviare [!DNL IIS Manager]:

   **[!UICONTROL Start]** (Analytics) > **[!UICONTROL Administrative Tools]** (Componenti) > **[!UICONTROL Internet Information Services (IIS) Manager]** (Progetti programmati).

1. Seleziona **[!UICONTROL Local Machine]** > **[!UICONTROL Sites]** > **[!UICONTROL Default Web Site]**.

1. Fare clic con il pulsante destro del mouse **[!UICONTROL Default Web Site]** e selezionare **[!UICONTROL Add Virtual Directory]**.

1. Per un alias, immettete Portal.
1. Per il percorso fisico, immettere [!DNL E:\Portal\PortalASP].
1. Fai clic su **[!UICONTROL OK]** (Fine).

   La directory virtuale creata viene visualizzata sotto il [!DNL Default Web Site].

1. Aggiungete le seguenti directory virtuali nella directory virtuale appena creata.

   | Crea alias... | Per questa risorsa fisica |
   |---|---|
   | Core | [!DNL E:\Portal\PortalFiles\Core] |
   | CSS | [!DNL E:\Portal\PortalFiles\CSS] |
   | Immagini | [!DNL E:\Portal\PortalFiles\Images] |
   | Uscita | Posizione fisica della directory in cui [!DNL Report Server] viene salvato l&#39;output per i set di report. La cartella di output può trovarsi ovunque e può essere denominata qualsiasi cosa. Contiene una sottocartella per ciascun set di rapporti. È possibile eliminare il file [!DNL E:\Portal\PortalFiles\Output], ma spostare [!DNL profiles.xml] il file nella posizione fisica del file Output. |

1. Al termine, verificate che IIS visualizzi quattro nuove directory virtuali. Accertatevi che la struttura di directory contenga una cartella principale (con lo stesso nome del portale) e quattro sottocartelle.
1. Fare clic su **[!UICONTROL Application Pools]**, quindi **[!UICONTROL DefaultAppPool]** (supponendo che sia quello configurato con il portale).

1. Fare clic su **[!UICONTROL Advanced Settings]** e selezionare True per abilitare le applicazioni a 32 bit.
1. Per [!DNL Portal] far funzionare il sistema, è necessario convertirlo in un&#39;applicazione. Dopo aver configurato le directory virtuali, fare clic con il pulsante destro del mouse sulla directory virtuale del portale e selezionare **[!UICONTROL Convert to Application]**.

## Suggerimenti e trucchi aggiuntivi {#section-ff84ab3f66c94620a6a11f0e60471d44}

* Puoi scaricare il contenuto [!DNL Portal] da Softdocs in **[!UICONTROL Softdocs]** > **[!UICONTROL Report Portal]**. Potete semplicemente scaricare il [!DNL ReportPortal-Release-1-0-0-7.zip].

* Non è più necessario [!DNL ReportPortalSetup.xml], quindi può essere eliminato.
* Per motivi di standardizzazione, inserite il contenuto di questo file ZIP in [!DNL E:\Portal].
* Per determinare il server SMTP Per i client di servizi gestiti, è possibile consultare questo documento.
* Inserire una richiesta con NetOps per modificare la voce del nome di dominio in IIS per il server di report in modo più semplice, ad esempio [!DNL reports.clientname.insight.omniture.com], in modo che l&#39;URL del portale sia [!DNL http://reports.clientname.insight.omniture.com/Portal]. Configurate il [!DNL email.asa] file una volta implementata la modifica.

