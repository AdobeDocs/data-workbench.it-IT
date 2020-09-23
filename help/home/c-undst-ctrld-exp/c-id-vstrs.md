---
description: Una tipica configurazione del sito utilizza i cookie per identificare in modo univoco i visitatori del sito Web e monitorarne il comportamento nel tempo.
solution: Analytics,Analytics
title: In che modo il sito identifica i visitatori?
topic: Data workbench
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---


# In che modo il sito identifica i visitatori?{#how-does-site-identify-visitors}

Una tipica configurazione del sito utilizza i cookie per identificare in modo univoco i visitatori del sito Web e monitorarne il comportamento nel tempo.

La prima volta che un particolare browser (considerato un visitatore) effettua una richiesta del sito Web, [!DNL Sensor] collabora con il server Web per impostare un cookie persistente (per impostazione predefinita [!DNL cs(cookie)(v1st)]), che viene interpretato internamente all’interno del sistema come [!DNL x-trackingid]. Questo cookie viene impostato solo una volta, sulla prima richiesta effettuata dal visitatore sul sito Web. Viene quindi raccolto da quel visitatore ogni volta che il browser effettua una richiesta (pagina o oggetto incorporato) del sito Web in futuro.

L’accettazione di un cookie persistente avviene a discrezione del browser. Se un utente sceglie di bloccare i cookie persistenti, le relative richieste di visualizzazione della pagina vengono ancora registrate, ma i dati di misurazione di tali richieste non sono correlati a un particolare visitatore o alle relative sessioni sul sito Web, a meno che non implementiate un metodo alternativo di identificazione del visitatore, ad esempio l’utilizzo della trasformazione Hash nei campi IP e UserAgent.

>[!NOTE]
>
>Gli esperimenti sul sito possono essere analizzati solo nei set di dati in cui l&#39;unico metodo di identificazione del visitatore in uso è il metodo di cookie persistente [!DNL Sensor] impostato. I sensori in esecuzione su server J2EE (JBoss, Tomcat, WebLogic e WebSphere) non supportano la sperimentazione controllata.

Durante un esperimento controllato, gli utenti che non accettano i cookie possono essere inseriti in diversi gruppi di esperimenti da un click all&#39;altro. Questo diventa un problema solo se eseguite l&#39;analisi di test con il filtro sessione interrotto disattivato [!DNL Insight], che  Adobe non è consigliato.

Per ulteriori informazioni sul filtro di sessione interrotta, vedere la * [!DNL Insight] Guida utente*.

Se un visitatore cancella il cookie durante un esperimento, al visitatore viene assegnato un nuovo cookie e potenzialmente può essere assegnato a un gruppo diverso. Poiché  Adobe identifica il visitatore come nuovo, l&#39;esperimento non viene invalidato.
