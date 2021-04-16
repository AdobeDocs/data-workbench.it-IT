---
description: Il sito utilizza i cookie per identificare in modo univoco i visitatori del sito web e monitorarne il comportamento nel tempo.
title: Informazioni sul cookie v1st
uuid: 6112cafe-51e3-42f0-8554-4a653dea782a
exl-id: c5e8e1cb-686b-4d31-821e-60beb2808f80
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 2%

---

# Informazioni sul cookie v1st{#understanding-the-v-st-cookie}

Il sito utilizza i cookie per identificare in modo univoco i visitatori del sito web e monitorarne il comportamento nel tempo.

La prima volta che un particolare browser (considerato un visitatore) effettua una richiesta del tuo sito web, [!DNL Sensor] collabora con il tuo server web per impostare un cookie persistente, cs(cookie)(v1st), che viene interpretato internamente all&#39;interno del sistema come x-trackingid. Questo cookie persistente viene impostato in aggiunta a qualsiasi altro cookie che il sito potrebbe altrimenti impostare. Questo cookie ottimizza la possibilità di tenere traccia dei visitatori in più sessioni, consentendo così di eseguire molti tipi di analisi altrimenti impossibili.

[!DNL Sensor] assegna una chiave numerica a 64 bit nel cookie per identificare i nuovi visitatori che effettuano una richiesta del sito come identificatore univoco. Quando il [!DNL Sensor] visualizza una richiesta da un browser, controlla se nei dati della richiesta esiste &quot;cs(cookie)(v1st)&quot;, un cookie persistente di prima parte impostato da [!DNL Sensor]. Se cs(cookie)(v1st) non è presente, [!DNL Sensor], attraverso il server web, comunica al browser di impostarlo. A differenza di altre soluzioni, [!DNL Sensor] è in grado di impostare questo cookie sulla prima richiesta del visitatore.

Di seguito è riportata l’intestazione standard del cookie persistente inviata al browser alla prima richiesta del sito dal server web, nella direzione [!DNL Sensor]. Il formato può essere definito al momento della configurazione se desideri un nome o una data di scadenza diversi. Ad esempio:

```
Set-Cookie:v1st=3D80DCA944D60E16; path=/; expires=Wed, 19 Feb 2020 14:28:00 GMT
```

Questo cookie viene impostato una sola volta, sulla prima richiesta effettuata al tuo sito da quel visitatore. Viene quindi raccolto da quel visitatore ogni volta che il browser effettua una richiesta (pagina o richiesta di oggetto incorporato) del tuo sito in futuro. Le dimensioni del cookie sono molto ridotte per ridurre al minimo la quantità di larghezza di banda utilizzata per trasmetterla ai server con ogni richiesta di quel browser al tuo sito.

L’accettazione di un cookie persistente è a discrezione del browser. La maggior parte degli utenti web capisce cosa fanno i cookie e riconosce anche che i cookie di prima parte forniscono loro un prezioso vantaggio consentendo di personalizzare il contenuto del sito in base alle loro preferenze. Questi cookie di prime parti non sono bloccati dalle impostazioni di sicurezza predefinite dei browser più diffusi. Se un utente sceglie di bloccare i cookie di prima parte, le richieste di visualizzazione della pagina rimangono registrate, ma i dati di misurazione di tali richieste non possono essere correlati in modo affidabile a un particolare visitatore o alle relative sessioni sul sito. Molti siti, soprattutto siti dinamici sofisticati, utilizzano già cookie di prime parti, che in molti casi sono necessari per consentire alle applicazioni web di funzionare per il visitatore. Un passo indietro da un cookie persistente è un cookie di sessione, che consente a una serie di richieste di essere unite in una sessione, ma non consente il tracciamento tra sessioni dei visitatori. [!DNL Site] è in grado di sessionizzare i dati dei visitatori in base ai cookie di sessione o al numero IP, ma entrambi i metodi determinano in modo significativo i tipi e il valore dell’analisi che possono essere condotti con  [!DNL Site] o qualsiasi altro sistema di analisi e reporting delle attività web.
