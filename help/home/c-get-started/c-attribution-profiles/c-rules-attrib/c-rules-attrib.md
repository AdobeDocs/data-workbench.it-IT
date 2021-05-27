---
description: Utilizzando il nuovo profilo di attribuzione basato su regole in Data Workbench, puoi analizzare rapidamente gli eventi di attribuzione e assegnare le responsabilità in modo da ottenere una conversione corretta definita dall’utente. Il profilo Attribution include le informazioni necessarie per l’impostazione e l’estensione delle funzioni dell’architetto di dati e include aree di lavoro predefinite che consentono all’analista di iniziare subito l’analisi.
title: Profilo di attribuzione
uuid: 500e9e86-cffc-4f0d-a397-6521b493bf9a
exl-id: 29946f22-1d39-44ca-9474-13dbe228751c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 0%

---

# Profilo di attribuzione{#attribution-profile}

Utilizzando il nuovo profilo di attribuzione basato su regole in Data Workbench, puoi analizzare rapidamente gli eventi di attribuzione e assegnare le responsabilità in modo da ottenere una conversione corretta definita dall’utente. Il profilo Attribution include le informazioni necessarie per l’impostazione e l’estensione delle funzioni dell’architetto di dati e include aree di lavoro predefinite che consentono all’analista di iniziare subito l’analisi.

Il profilo Attribution ti consente di acquisire una nuova prospettiva sulle relazioni tra le tue attività di marketing e una generazione di lead di successo o una conversione delle vendite. Il profilo Attribution ti aiuta a qualificare le interazioni che devono ricevere l’allocazione di credito per i ricavi realizzati o la partecipazione a valle nel percorso cliente. Consente di identificare l’impatto delle attività e dei costi di marketing, analizzando rapidamente gli eventi di attribuzione e quindi assegnando la responsabilità per i primi o gli ultimi contatti o altri eventi che portano a una vendita di successo.

<!-- <a id="section_648A288E4CA84D579884BC161085C4D5"></a> -->

>[!IMPORTANT]
>
>Il profilo di attribuzione è configurato per l’uso immediato da parte degli utenti che hanno implementato il profilo Adobe SC che utilizza il feed di dati di Analytics (SC/Insight). Per impostazione predefinita, gli eventi Marketing e Conversion vengono utilizzati come tipi predefiniti di interazioni valutate nei modelli basati sulle regole forniti.

Per ulteriori informazioni, consulta [Distribuzione del profilo di attribuzione](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-profile-deploy.md#concept-fbcb5800cd6a40cc901e61f3882988c0) e [Modelli di attribuzione](../../../../home/c-get-started/c-attribution-profiles/c-rules-attrib/c-attrib-models.md#concept-e209c7e86a5c4008ad6d78fdf4ea032d) .

## Architettura e aree di lavoro di Analytics {#section-27c6aff70ba147cca6e11451e127afb4}

All’interno del profilo Attribuzione, le aree di lavoro Architetto e Analista sono definite in schede separate all’interno del workbench.

![](assets/attribution_profile_tabs.png)

**Aree di lavoro di architettura**

Nella scheda **Attribution** , fai clic sulla scheda **[!UICONTROL Architect Workspace]** per aprire le aree di lavoro progettate specificatamente per impostare i file di configurazione per la modellazione di attribuzione di base.

![](assets/attribution_profile_arch.png)

La scheda Architettura include le aree di lavoro che consentono di esaminare tutti i file di configurazione presenti nella cartella dei set di dati del profilo. Ad esempio, **[!UICONTROL Attribution Configuration - Step 1]** ti consente di identificare i valori di attribuzione all’interno della sezione Trasformazione del file [!DNL profile.cfg].

![](assets/attribution_profile_arch_step1.png)

**Aree di** lavoro di analisiFai clic sulla  **[!UICONTROL Analyst]** **[!UICONTROL Workspaces]** scheda per aprire le analisi predefinite delle aree di lavoro utilizzando le dimensioni e le metriche fornite con il profilo di attribuzione.

Queste aree di lavoro sono organizzate in quattro categorie:

1. **Rapporti di base: crea un singolo modello all’interno di un’area di lavoro.** 
1. **Comparative** Reports (Report comparativi) ha esteso le analisi presentando più modelli in un&#39;unica visualizzazione.
1. **I** rapporti sulle indagini espandono i modelli di reporting per presentare i modelli di attribuzione in diversi formati. Questa sezione introduce ed espone anche i rapporti di ponderazione basati sulla posizione.
1. **I** rapporti sui percorsi forniscono visibilità al percorso di marketing del cliente con visualizzazioni di percorsi multipli per esplorare ed esprimere appieno i flussi di processo e i percorsi di interazione

![](assets/attribution_profile_analyst.png)

La scheda Analyst include aree di lavoro preconfigurate con i rapporti. Ad esempio, **[!UICONTROL First Attribution]** ti consente di selezionare dalla tabella **[!UICONTROL Campaign]** per visualizzare l’attribuzione **[!UICONTROL Revenue]** in base a **[!UICONTROL Time]**.

![](assets/attribution_profile_analyst_step1.png)
