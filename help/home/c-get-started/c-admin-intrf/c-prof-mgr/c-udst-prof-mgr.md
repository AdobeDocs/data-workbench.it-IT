---
description: I nomi delle cartelle e dei file inclusi nell’implementazione vengono visualizzati sul lato sinistro di Profile Manager.
title: Profile Manager (Gestione profili)
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 0%

---


# Profile Manager (Gestione profili) {#profile-manager}

{{eol}}

I nomi delle cartelle e dei file inclusi nell’implementazione vengono visualizzati sul lato sinistro di Profile Manager.

I profili che compongono la tua applicazione vengono visualizzati come colonne individuali nella [!DNL Profile Manager]. Tali profili includono più profili ereditati e un unico profilo di lavoro.

>[!NOTE]
>
>Il profilo di lavoro (un profilo di set di dati o un profilo specifico per un ruolo) è il profilo caricato all’apertura di Data Workbench.

I segni di spunta (e i relativi colori) indicano le cartelle del profilo sul server di Data Workbench e nei computer di Data Workbench in cui si trova ogni file, se esistono più copie di un file e se tali copie hanno la stessa data e ora di modifica. Questi file vengono sincronizzati tra il server Data Workbench e i computer Data Workbench durante il download del profilo.

Di seguito è riportato un esempio [!DNL Profile Manager] per un&#39;implementazione HBX:

![](assets/client-prof.png)

Da [!DNL Profile Manager] è possibile aprire qualsiasi altro manager (ad esempio, il [!DNL Dimensions Manager] o [!DNL Reports Manager]), che presentano solo determinate porzioni di [!DNL Profile Manager]. Puoi anche creare nuovi gestori di profili. Vedi [Creazione di nuovi gestori di profili](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3).

Un segno di spunta accanto al nome di un file in una particolare colonna indica che un file con quel nome si trova nella cartella denominata in quella colonna (profilo). Mentre ti muovi a destra nella [!DNL Profile Manager], i file hanno la precedenza su quelli a sinistra, ovvero ogni profilo ereditato si basa sui profili a sinistra nel [!DNL Profile Manager]. Ad esempio, se disponi di un file con lo stesso nome e nella stessa posizione nel [!DNL Base] profilo (colonna) e [!DNL User] profilo (colonna), il file nel [!DNL User] viene utilizzato al posto del file nel [!DNL Base] profilo.

## Cercare profili {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

Con Data Workbench 5.5, è stato aggiunto un campo di ricerca per trovare i profili richiesti nella [!DNL Profile Manager].

![](assets/client-prof2.png)

I seguenti tipi di colonne vengono visualizzati nel [!DNL Profile Manager]:

* La *nome profilo ereditato* Le colonne contengono segni di spunta per i file che risiedono in ciascuna cartella del profilo. I profili ereditati includono i profili interni forniti da Adobe, nonché tutti i profili specifici per l’azienda o specifici per il ruolo creati e gestiti dall’utente. Nell’esempio precedente, i profili interni includono Base, Traffico, Valore, Marketing e così via. Interno [!DNL Base] profile, che contiene i blocchi predefiniti di base e le informazioni di configurazione necessarie per eseguire l’applicazione Adobe, viene fornito con ogni implementazione. Gli altri profili interni contengono elementi (aree di lavoro, metriche, dimensioni derivate e così via) relativi a particolari tipi di informazioni, ad esempio traffico web o marketing. Adobe fornisce solo i profili appropriati per il tipo di dati che stai analizzando e per il settore.

   >[!NOTE]
   >
   >Per impostazione predefinita, i profili interni (quelli forniti da Adobe) non possono essere modificati. Tutte le personalizzazioni devono verificarsi nel set di dati o nei profili specifici per il ruolo o in altri profili creati. Se stai creando una nuova applicazione e devi modificare un profilo interno, devi modificare il parametro Modifica profili interni in [!DNL Insight.cfg] file. Vedi [Parametri di configurazione di Insight](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) per ulteriori informazioni. Prima di procedere, contattare Adobe Consulting Services.

* La *nome profilo di lavoro* Questa colonna contiene sempre i segni di spunta per i file che si trovano nella cartella del profilo di lavoro corrente. Nell&#39;esempio precedente, il profilo di lavoro è Dataset. Il profilo di lavoro è un profilo di set di dati o un profilo specifico per un ruolo. I file in questa cartella hanno la precedenza su tutti i file con gli stessi nomi presenti in qualsiasi cartella di profilo ereditata.
* La [!DNL User] Questa colonna, sempre l&#39;ultima, contiene i segni di spunta per i file e le cartelle che risiedono come file locali nella cartella User\*profile name*. La struttura di directory della cartella Utente imita quella del profilo di lavoro e ogni cartella Nome profilo utente\** contiene copie locali delle aree di lavoro, delle metriche, delle dimensioni e dei file di configurazione per quel particolare profilo. Queste copie locali hanno la precedenza su tutti i file con gli stessi nomi in qualsiasi cartella di profilo ereditata o di lavoro. I file nel [!DNL User] sono state create e salvate solo nella cartella User\*profile name* oppure si trovano in un profilo interno o di lavoro e nella cartella User\*profile name*. I file contenuti in ciascuna cartella possono essere identici o meno e possono avere la stessa data e ora di modifica.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Per evitare di modificare il set di dati solo localmente, il server Data Workbench ignora le copie locali del [!DNL profile.cfg] e tutti i file presenti nelle cartelle Dataset o Export nella cartella User\*profile name*. I file ignorati sono identificati da uno sfondo rosso [!DNL User] e un avviso &quot;Ignored in User directory&quot; nel menu di scelta rapida. Per implementare le modifiche apportate nelle copie locali di questi file, è necessario salvarli nel profilo di lavoro in modo che possano essere sincronizzati con il server Data Workbench. Per i passaggi necessari per salvare i file nel profilo di lavoro, vedi [Pubblicazione di file nel profilo di lavoro](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9).
   >    
   >    * Un trattino (-) invece di un segno di spunta in una colonna identifica un file vuoto (zero byte). Data Workbench considera i file a byte zero come inesistenti, il che consente di utilizzarli per nascondere i file inclusi in un profilo a sinistra. Vedi [Nascondere i file utilizzando file vuoti (a byte zero)](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491).


## Determinare le versioni dei file {#section-225d732246b94cbe87acdfa9c881d6af}

Come indicato nella sezione precedente, i segni di spunta nella [!DNL Profile Manager] sono codificati in base al colore, in modo da identificare facilmente dove si trova un file e se le copie multiple di un file sono state modificate in momenti diversi.

Se un file o una directory compressa è esattamente uguale al file o alla directory a sinistra, ha lo stesso segno di spunta colore del file o della directory in quella colonna (profilo). Se è diverso da qualsiasi file o directory alla sua sinistra, oppure il file o la directory esiste solo nel [!DNL User] il segno di spunta è bianco.

![](assets/vis_ProfMgr_LocalFiles.png)

La [!DNL Profile Manager] nell’esempio precedente, indica quanto segue:

* Un segno di spunta bianco per [!DNL A New Metric.metric] il file viene visualizzato solo nel [!DNL User] , che indica che disponi solo di una copia locale del file, che non è stata pubblicata (o caricata) sul server Data Workbench affinché altri utenti di Data Workbench possano accedervi.

* Contrassegni per [!DNL Average Score.metric] il nome del file viene visualizzato nei filmati e [!DNL User] colonne. Il segno di spunta nel [!DNL User] La colonna ha lo stesso colore del segno di spunta nella colonna Filmati, che indica che la copia locale del file ha la stessa data e ora di modifica del file nella cartella Filmati.

* Contrassegni per [!DNL Average Score Error.metric] il nome del file viene visualizzato nei filmati e [!DNL User] colonne. Il segno di spunta nel [!DNL User] La colonna è bianca e indica che la copia locale del file ha una data o un’ora di modifica diversa rispetto al file presente nella cartella Filmati.

