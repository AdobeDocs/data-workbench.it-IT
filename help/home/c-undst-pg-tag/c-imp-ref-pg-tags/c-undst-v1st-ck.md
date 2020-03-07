---
description: Il sito utilizza i cookie per identificare in modo univoco i visitatori del sito Web e per monitorare il loro comportamento nel tempo.
solution: Analytics
title: Il cookie v1st
topic: Data workbench
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Il cookie v1st{#understanding-the-v-st-cookie}

Il sito utilizza i cookie per identificare in modo univoco i visitatori del sito Web e per monitorare il loro comportamento nel tempo.

La prima volta che un particolare browser (considerato un visitatore) effettua una richiesta del sito Web, [!DNL Sensor] collabora con il server Web per impostare un cookie persistente, cs(cookie)(v1st), che viene interpretato internamente all&#39;interno del sistema come x-trackingid. Questo cookie persistente viene impostato in aggiunta a qualsiasi altro cookie che il sito potrebbe altrimenti impostare. Questo cookie ottimizza la possibilità di monitorare i visitatori in più sessioni, consentendo la creazione di molti tipi di analisi altrimenti impossibili.

[!DNL Sensor] assegna una chiave numerica a 64 bit nel cookie per identificare i nuovi visitatori che effettuano una richiesta del sito come identificatore univoco. Quando viene [!DNL Sensor] visualizzata una richiesta da un browser, viene verificato se nei dati della richiesta esiste &quot;cs(cookie)(v1st)&quot;, un cookie persistente di prima parte impostato da [!DNL Sensor], Se cs(cookie)(v1st) non è presente, [!DNL Sensor]tramite il server Web informa il browser di impostarlo. A differenza di altre soluzioni, [!DNL Sensor] è possibile impostare questo cookie sulla prima richiesta del visitatore.

Di seguito è riportata l&#39;intestazione standard del cookie persistente inviata al browser alla prima richiesta del sito da parte del server Web, nella direzione di [!DNL Sensor]. Il formato può essere definito al momento della configurazione se si desidera un nome o una data di scadenza differente. Ad esempio:

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Questo cookie viene impostato una sola volta, sulla prima richiesta effettuata al sito dal visitatore. Viene quindi raccolto da quel visitatore ogni volta che il browser effettua una richiesta (pagina o oggetto incorporato) del sito in futuro. Le dimensioni del cookie sono molto ridotte per ridurre al minimo la quantità di larghezza di banda utilizzata per trasmetterlo ai server con ogni richiesta da quel browser al sito.

L’accettazione di un cookie persistente avviene a discrezione del browser. La maggior parte degli utenti del web capisce cosa fanno i cookie e riconosce anche che i cookie di prime parti forniscono loro un prezioso vantaggio nel consentire il contenuto del sito di essere personalizzato in base alle loro preferenze. Questi cookie di prime parti non vengono bloccati dalle impostazioni di protezione predefinite dei browser più diffusi. Se un utente sceglie di bloccare i cookie di prime parti, le relative richieste di visualizzazione della pagina vengono ancora registrate, ma i dati di misurazione di tali richieste non possono essere correlati in modo affidabile a un particolare visitatore o alle relative sessioni sul sito. Molti siti, soprattutto siti dinamici sofisticati, utilizzano già cookie di prime parti, che in molti casi sono necessari per consentire alle applicazioni Web di funzionare per il visitatore. Un passo indietro da un cookie persistente è un cookie di sessione, che consente a una serie di richieste di essere unite in una sessione, ma non consente il tracciamento intersessione dei visitatori. [!DNL Site] è in grado di sottoporre a sessione i dati dei visitatori in base ai cookie di sessione o al numero IP, ma entrambi i metodi si differenziano in modo significativo dai tipi e dal valore dell&#39;analisi che è possibile eseguire con [!DNL Site] o con qualsiasi altro sistema di analisi e reporting dell&#39;attività Web.
