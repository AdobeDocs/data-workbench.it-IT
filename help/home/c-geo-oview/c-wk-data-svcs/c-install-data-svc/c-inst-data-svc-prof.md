---
description: I profili dei servizi dati (IP Geo-intelligence e IP Geo-location) sono profili interni che forniscono funzionalità aggiuntive all’applicazione Adobe.
solution: Analytics
title: Installazione del profilo del servizio dati
topic: Data workbench
uuid: 1c03d0cd-7eaa-4e48-bbff-8bfad8fed9e9
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installazione del profilo del servizio dati{#installing-the-data-service-profile}

I profili dei servizi dati (IP Geo-intelligence e IP Geo-location) sono profili interni che forniscono funzionalità aggiuntive all’applicazione Adobe.

Come per tutti gli altri profili interni forniti da Adobe, tali profili non devono essere modificati. Tutta la personalizzazione deve avvenire nel dataset o nei profili specifici del ruolo o in altri profili creati.

I profili del servizio dati includono i seguenti dataset che includono i file da installare in un server workbench dati:

* **Profili\*nome *profilo \Dataset\Log Processing\Traffic\IP.cfg:** Elenca il campo c-ip da passare dall&#39;elaborazione del registro alla trasformazione.
* **Profili\*nome *profilo \Dataset\Transformation\Geography\IPLookup.cfg:** Definisce una trasformazione IPLookup che produce diversi campi di dati geografici utilizzando il file di ricerca IP Geo-intelligence o geolocalità IP fornito.

Per informazioni sui set di dati di trasformazione e sui file di inclusione, vedere la Guida alla configurazione del set di *dati*.

Inoltre, ogni profilo del servizio dati fornisce un file livello punto elemento denominato [!DNL IP Coordinates.layer]. Questo file di livello consente di mappare dinamicamente le posizioni del set di dati sul globo utilizzando indirizzi IP. Dopo l&#39;installazione, il livello viene memorizzato nella cartella Profili\*nome servizio dati*\Maps all&#39;interno della directory di installazione del server workbench dati.

Il [!DNL IP Coordinates.layer] file fa riferimento alla dimensione Coordinate, definita nel [!DNL Coordinates.cfg] file fornito con il [!DNL Geography] profilo e che si trova nella cartella Dataset\Transformation\Geography folder. Ogni elemento della dimensione Coordinate definito nel dataset viene mappato sul globo utilizzando le informazioni di latitudine e longitudine contenute in tale elemento. Per ulteriori informazioni sui livelli dei punti degli elementi che utilizzano punti dinamici, consultate [Definizione dei livelli dei punti elemento mediante i punti](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyr-file-frmt/c-dyn-pts.md#concept-77ae65bedc3f465489bc135ae7e3c2f3)dinamici.

>[!NOTE]
>
>Se avete installato il servizio dati IP Geo-intelligence e IP Geo-location prima della versione 5.1, il file del livello dei punti dell&#39;elemento fa riferimento a un file di ricerca invece di usare punti dinamici. Ogni file di livello fa riferimento al file di ricerca dei codici geografici IP e alla dimensione del codice geografico IP. Il file di ricerca dei geocodici IP contiene un elenco di geocodici IP (posizioni geografiche basate sull&#39;indirizzo IP) e la latitudine e la longitudine di ciascuna di esse. Ogni elemento di una dimensione del geocodice IP definito nel set di dati viene mappato sul globo utilizzando la latitudine e la longitudine elencate per tale geocodice IP nel file di ricerca dei codici geografici IP.

Il nome del file di livello e i file a cui fa riferimento differiscono per ciascun servizio dati:

* Il [!DNL IP Geocodes D.layer] file viene installato con il profilo IP Geo-Intelligence (Digital Envoy). Questo livello punto elemento fa riferimento al file di [!DNL IP Geocodes D yyyymmdd.txt] ricerca (che è necessario aggiornare periodicamente) e alla dimensione D del geocodice IP.

* Il [!DNL IP Geocodes Q.layer] file viene installato con il profilo Geo-location (Quova) IP. Questo livello punto elemento fa riferimento al file di [!DNL IP Geocodes Q yyyymmdd.txt] ricerca (che è necessario aggiornare periodicamente) e alla dimensione Q del Geocode IP.

Per ulteriori informazioni sui livelli dei punti degli elementi che utilizzano i file di ricerca, vedere [Definizione dei livelli dei punti elemento con riferimento ai file](../../../../home/c-geo-oview/c-wk-img-lyrs/c-elmt-pt-lyrs/c-elmt-pt-lyrs-ref-lkp-files/c-elmt-pt-lyrs-ref-lkp-files.md#concept-c40bd0890a984112bce831b596827f0f)di ricerca.

## Per installare il profilo di geolocalità IP o geolocalità IP {#section-6dff402ffdcb4b31b9bcd0c40a5f7625}

>[!NOTE]
>
>Le seguenti istruzioni di installazione presuppongono l&#39;installazione di workbench dati e la creazione di una connessione tra Workbench dati e Server workbench dati su cui si sta installando workbench dati [!DNL Geography]. In caso contrario, vedere la Guida *utente di Workbench* dati.

1. Aprite la cartella Profili dal [!DNL .zip] file ricevuto da Adobe.
1. Copiare la cartella Geo-intelligence IP o Geolocalità IP nella cartella Profili nella directory di installazione del server workbench dati. Volete finire con un ...\Profiles\IP Geo-intelligence folder or a ...\Profiles\IP Geo-location on your data workbench server as shown in the following example. I nomi delle altre cartelle all’interno della [!DNL Profiles] cartella possono essere diversi da quelli visualizzati.

   ![](assets/Geo_installProfiles_dirIP.png)

1. Per aggiornare il [!DNL profile.cfg] file per ciascun profilo con il quale si desidera utilizzare il [!DNL IP Geo-intelligence] o il [!DNL IP Geo-location] profilo, procedere come segue.

   1. Aprite il **[!UICONTROL Profile Manager]**.
   1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene [!DNL profile.cfg] visualizzata la finestra.

   1. Nella [!DNL profile.cfg]finestra, fare clic con il pulsante destro del mouse **[!UICONTROL Directories]** e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

      Per aggiungere la nuova directory alla fine dell&#39;elenco di directory, fare clic con il pulsante destro del mouse sul numero o sul nome dell&#39;ultima directory dell&#39;elenco e scegliere **[!UICONTROL Add new]** > **[!UICONTROL Directory]**.

   1. Digitare il nome della nuova directory: [!DNL IP Geo-intelligence] o io [!DNL P Geo-location].

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare [!DNL Profile Manager]clic con il pulsante destro del mouse sul segno di spunta [!DNL profile.cfg] nella [!DNL User] colonna, quindi scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

>[!NOTE]
>
>Non salvate il file di configurazione modificato in alcun profilo interno fornito da Adobe (incluso il [!DNL IP Geo-location] profilo o il [!DNL IP Geo-intelligence] profilo), in quanto le modifiche vengono sovrascritte quando installate gli aggiornamenti a tali profili.

