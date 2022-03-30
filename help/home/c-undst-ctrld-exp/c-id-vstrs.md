---
description: Una tipica configurazione del sito utilizza i cookie per identificare in modo univoco i visitatori del sito web e tracciarne il comportamento nel tempo.
solution: Analytics
title: In che modo il sito identifica i visitatori?
uuid: e1e451b8-e827-4010-bda9-9147c3b09958
exl-id: 2783ee11-6d6a-463d-86b5-dd63e490201f
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# In che modo il sito identifica i visitatori?{#how-does-site-identify-visitors}

Una tipica configurazione del sito utilizza i cookie per identificare in modo univoco i visitatori del sito web e tracciarne il comportamento nel tempo.

La prima volta che un particolare browser (considerato un visitatore) effettua una richiesta del tuo sito web, [!DNL Sensor] funziona con il server web per impostare un cookie persistente (per impostazione predefinita) [!DNL cs(cookie)(v1st)]), interpretata internamente all&#39;interno del sistema come [!DNL x-trackingid]. Questo cookie viene impostato una sola volta, sulla prima richiesta effettuata al sito web da quel visitatore. Viene quindi raccolto da quel visitatore ogni volta che il browser effettua una richiesta (pagina o richiesta di oggetto incorporato) del tuo sito web in futuro.

L’accettazione di un cookie persistente è a discrezione del browser. Se un utente sceglie di bloccare i cookie persistenti, le relative richieste di visualizzazione della pagina vengono comunque registrate, ma i dati di misurazione di tali richieste non sono correlati a un particolare visitatore o alle relative sessioni sul sito web, a meno che non si implementi un metodo alternativo di identificazione del visitatore, ad esempio l’utilizzo della trasformazione Hash nei campi IP e UserAgent.

>[!NOTE]
>
>Gli esperimenti del sito possono essere analizzati solo nei set di dati in cui l’unico metodo di identificazione del visitatore in uso è il [!DNL Sensor] imposta il metodo cookie persistente. I sensori in esecuzione su server J2EE (JBoss, Tomcat, WebLogic e WebSphere) non supportano la sperimentazione controllata.

Durante un esperimento controllato, gli utenti che non accettano i cookie possono essere inseriti in diversi gruppi sperimentali da un clic all&#39;altro. Questo diventa un problema solo se esegui l&#39;analisi dei test con il filtro sessione interrotto disattivato [!DNL Insight], Adobe non consigliato.

Per ulteriori informazioni sul filtro sessioni interrotte, consulta la sezione * [!DNL Insight] Guida utente*.

Se un visitatore cancella il cookie durante un esperimento, al visitatore viene assegnato un nuovo cookie e potenzialmente può essere assegnato a un gruppo diverso. Poiché l’Adobe identifica il visitatore come nuovo, l’esperimento non viene invalidato.
