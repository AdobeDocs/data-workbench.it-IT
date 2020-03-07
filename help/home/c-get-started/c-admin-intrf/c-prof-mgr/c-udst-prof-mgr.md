---
description: I nomi delle cartelle e dei file inclusi nell’implementazione vengono visualizzati sul lato sinistro di Gestione profili.
solution: Analytics
title: Gestione profili
topic: Data workbench
uuid: c3a19a56-c96b-4661-b656-b845feba4b6f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Gestione profili{#profile-manager}

I nomi delle cartelle e dei file inclusi nell’implementazione vengono visualizzati sul lato sinistro di Gestione profili.

I profili che compongono l’applicazione vengono visualizzati come singole colonne nella [!DNL Profile Manager]. Tali profili includono più profili ereditati e un unico profilo di lavoro.

>[!NOTE]
>
>Il profilo di lavoro (un profilo set di dati o un profilo specifico per un ruolo) è il profilo caricato all&#39;apertura di Workbench dati.

I segni di spunta (e i relativi colori) indicano le cartelle del profilo nei computer del server Workbench dati e Workbench dati in cui risiede ciascun file, se esistono più copie di un file e se tali copie multiple hanno la stessa data e ora di modifica. Questi file vengono sincronizzati tra il server Workbench dati e i computer Workbench dati durante il download del profilo.

Esempio [!DNL Profile Manager] per un’implementazione HBX:

![](assets/client-prof.png)

Dal [!DNL Profile Manager] menu potete aprire qualsiasi altro manager (ad esempio, il [!DNL Dimensions Manager] o [!DNL Reports Manager]), che visualizza solo porzioni specifiche di [!DNL Profile Manager]. Potete anche creare nuovi manager di profilo. Consultate [Creazione di nuovi manager](../../../../home/c-get-started/c-intf-anlys-ftrs/c-cstm-prof-files-mgrs/c-new-prof-mgrs.md#concept-0021e006523e4d538aaa16322731d9d3)di profilo.

Un segno di spunta accanto al nome di un file in una particolare colonna indica che un file con lo stesso nome risiede nella cartella indicata nella colonna (profilo). Quando vi spostate a destra nella [!DNL Profile Manager], i file hanno la precedenza su quelli a sinistra, ovvero ogni profilo ereditato si basa sui profili a sinistra nella [!DNL Profile Manager]. Ad esempio, se avete un file con lo stesso nome e nella stessa posizione nel [!DNL Base] profilo (colonna) e nel [!DNL User] profilo (colonna), il file nel [!DNL User] profilo viene utilizzato invece del file nel [!DNL Base] profilo.

## Cercare profili {#section-91f873f1d7ed4fd6a5f3c3ac08cfa623}

Con Workbench dati 5.5, è stato aggiunto un campo di ricerca per trovare i profili richiesti in [!DNL Profile Manager].

![](assets/client-prof2.png)

I seguenti tipi di colonne sono visualizzati in [!DNL Profile Manager]:

* Le colonne del nome *del profilo* ereditato contengono indicatori di spunta per i file che risiedono in ciascuna cartella del profilo. I profili ereditati includono i profili interni forniti da Adobe, nonché eventuali profili specifici per la società o specifici per i ruoli creati e mantenuti. Nell&#39;esempio precedente, i profili interni includono Base, Traffico, Valore, Marketing e così via. Il [!DNL Base] profilo interno, che contiene i blocchi costitutivi di base e le informazioni di configurazione necessarie per eseguire l&#39;applicazione Adobe, viene fornito con ogni implementazione. Gli altri profili interni contengono elementi (aree di lavoro, metriche, dimensioni derivate e così via) relativi a tipi particolari di informazioni, come il traffico Web o il marketing. Adobe fornisce solo i profili appropriati per il tipo di dati che stai analizzando e per il tuo settore.

   >[!NOTE]
   >
   >Per impostazione predefinita, i profili interni (forniti da Adobe) non possono essere modificati. Tutta la personalizzazione deve avvenire nel dataset o nei profili specifici del ruolo o in altri profili creati. Se si sta creando una nuova applicazione e si desidera modificare un profilo interno, è necessario modificare il parametro Modifica profili interni nel [!DNL Insight.cfg] file. Per ulteriori informazioni, consulta Parametri [di configurazione](../../../../home/c-get-started/c-insght-config-param.md#concept-14da97d0756348e885c08ca9e866074b) di Insight. Prima di eseguire questa operazione, contattare i servizi di consulenza Adobe.

* La colonna del nome *del profilo di* lavoro, che è sempre la colonna &quot;dall&#39;ultimo all&#39;altro&quot;, contiene i segni di spunta per i file che risiedono nella cartella del profilo di lavoro corrente. Nell&#39;esempio precedente, il profilo di lavoro è Dataset. Il profilo di lavoro è un profilo di set di dati o un profilo specifico per il ruolo. I file contenuti in questa cartella hanno la precedenza su tutti i file con gli stessi nomi presenti in qualsiasi cartella di profilo ereditata.
* La [!DNL User] colonna, che è sempre l&#39;ultima colonna, contiene indicatori di spunta per file e cartelle che risiedono come file locali nella cartella Utente\*nome profilo*. La struttura di directory della cartella Utente imita quella del profilo di lavoro, e ogni cartella Utente\*nome profilo* contiene copie locali dei file di area di lavoro, metriche, dimensioni e configurazione per quel particolare profilo. Queste copie locali hanno la precedenza su qualsiasi file con gli stessi nomi in qualsiasi cartella di profilo ereditata o di lavoro. I file nella [!DNL User] colonna sono stati creati e salvati solo nella cartella Utente\*profile name*, oppure risiedono in un profilo interno o di lavoro nonché nella cartella Utente\*profile name*. I file contenuti in ciascuna cartella possono essere identici o meno e possono avere o meno la stessa data e ora di modifica.

   >[!NOTE]
   >
   >
   >    
   >    
   >    * Per evitare di modificare il set di dati solo localmente, il server Workbench dati ignora le copie locali del [!DNL profile.cfg] file e tutti i file delle cartelle Dataset o Export nella cartella User\*profile name*. I file ignorati sono identificati da uno sfondo rosso nella [!DNL User] colonna e un avviso &quot;Ignorato nella directory utente&quot; nel menu di scelta rapida. Per implementare le modifiche apportate nelle copie locali di questi file, è necessario salvarle nel profilo di lavoro in modo che possano essere sincronizzate con il server Workbench dati. Per i passaggi necessari per salvare i file nel profilo di lavoro, consultate [Pubblicazione dei file nel profilo](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/t-pub-files-wkg-prof.md#task-a0106e010c834d16bd60eef4721b6af9)di lavoro.
      >    
      >    
   * Un trattino (-) invece di un segno di spunta in una colonna identifica un file vuoto (a byte zero). Workbench dati considera i file a zero byte come inesistenti, il che consente di utilizzarli per nascondere i file inclusi in un profilo a sinistra. Consultate [Nascondere i file utilizzando file](../../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-empty-files.md#concept-e776fac9e5904bed8c13b9d5eb17c491)vuoti (a byte zero).


## Determinare le versioni dei file {#section-225d732246b94cbe87acdfa9c881d6af}

Come indicato nella sezione precedente, i segni di spunta [!DNL Profile Manager] sono codificati a colori in modo da identificare facilmente dove si trova un file e se le copie multiple di un file sono state modificate in momenti diversi.

Se un file o una directory compressa è esattamente uguale al file o alla directory a sinistra, ha lo stesso segno di spunta colore del file o della directory in quella colonna (profilo). Se è diverso da qualsiasi file o directory a sinistra, o se il file o la directory esiste solo nella [!DNL User] colonna, il segno di spunta è bianco.

![](assets/vis_ProfMgr_LocalFiles.png)

L’ [!DNL Profile Manager] esempio riportato sopra indica quanto segue:

* Un segno di spunta bianco per il [!DNL A New Metric.metric] file viene visualizzato solo nella [!DNL User] colonna, a indicare che si dispone solo di una copia locale del file, ma non è stata pubblicata (o caricata) nel server Workbench dati per consentire agli altri utenti di Workbench dati di accedervi.

* Gli indicatori di controllo per il nome del [!DNL Average Score.metric] file vengono visualizzati nelle [!DNL User] colonne Filmati e Filmati. Il segno di spunta nella [!DNL User] colonna ha lo stesso colore del segno di spunta nella colonna Filmati, che indica che la copia locale del file ha la stessa data e ora di modifica del file nella cartella Filmati.

* Gli indicatori di controllo per il nome del [!DNL Average Score Error.metric] file vengono visualizzati nelle [!DNL User] colonne Filmati e Filmati. Il segno di spunta nella [!DNL User] colonna è bianco e indica che la copia locale del file ha una data o un&#39;ora modificate diversa da quella del file nella cartella Filmati.

