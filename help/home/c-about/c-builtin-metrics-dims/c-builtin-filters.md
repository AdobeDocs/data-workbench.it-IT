---
description: I filtri profilo limitano l'ambito dei dati disponibili da un set di dati.
solution: Analytics
title: Filtri di profilo incorporati
topic: Data workbench
uuid: d6854d2c-4643-476e-8a44-f188e18cb115
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Filtri di profilo incorporati{#built-in-profile-filters}

I filtri profilo limitano l&#39;ambito dei dati disponibili da un set di dati.

Oltre ai filtri di elaborazione e trasformazione del registro che possono essere applicati prima o durante la creazione di un dataset, sono disponibili altri filtri di profilo che influiscono sull&#39;ambito dei dati disponibili per la selezione da un dataset. Questa sezione descrive solo l&#39;ultimo tipo di filtri speciali.

Dopo la creazione di un set di dati, gli utenti possono accedere ai seguenti filtri profilo:

* Filtro per sottoinsiemi di dati
* Filtro sessione interrotta

>[!NOTE]
>
>È possibile creare e applicare altri filtri attraverso la loro presenza nella directory Filters di un profilo.

## Subimpostazione dati {#section-0defb44315d94254ab6e629ec3d6f420}

Un sottoinsieme di dati funge da filtro di dati e consente di selezionare solo gli elementi dimensionali dei dati di interesse.

La creazione di sottoinsiemi di dati riduce il tempo necessario per calcolare le risposte esatte alle query. Se il sottoinsieme di dati specificato è sufficientemente piccolo, Workbench dati può recuperare tutti i dati necessari da Insight Server e rispondere alle domande sul sottoinsieme in modo rapido e accurato. Ciò è particolarmente utile se sai che, ad esempio, l&#39;analisi di un giorno di dati o sessioni da un particolare referente richiederà diverse ore.

Gli utenti possono creare autonomamente sottoinsiemi di dati oppure accedere ai sottoinsiemi di dati definiti in un profilo ereditato o di lavoro. Quando un utente crea un sottoinsieme di dati (selezionando i dati desiderati in Insight e facendo clic con il pulsante destro del mouse nell’area di lavoro e scegliendo Dati > Sottoinsieme), viene creato un file Data Subset.filter nella cartella Filters all’interno della directory del profilo Utente. Questo filtro definisce il sottoinsieme di dati selezionato e salva il sottoinsieme per un utilizzo futuro.

>[!NOTE]
>
>Potete creare più sottoinsiemi di dati e attivarli per visualizzare diverse porzioni di dati. Ricordare di disattivare l&#39;opzione Sottoinsieme dati quando si desidera visualizzare tutti i dati. In caso contrario, i valori delle metriche non saranno rappresentativi di tutti i dati nel set di dati.

## Filtro sessione interrotta {#section-1608e97da6464b11aea27cbb7f3160e4}

Il filtro di sessione interrotto è una formula metrica che può essere facilmente modificata per soddisfare qualsiasi requisito di filtro. Nei profili di sito predefiniti, il filtro sessioni interrotte è configurato per includere tutti i visitatori con un flag Visitorized impostato su 1. Il valore 1 indica la presenza di un cookie di tracciamento per quel visitatore.

Di seguito è riportato il testo del file Filter.filter di sessione interrotto predefinito fornito da Adobe nel pacchetto di rilascio per i profili del sito.

```
entity = derived_filter:
   formula = string: Visitorized_Flag="1"
   model = ref: wdata/model
```

Per impostazione predefinita, le aree di lavoro presentano il filtro Sessione interrotta applicato sia alla selezione che ai parametri di riferimento, che può essere attivato facendo clic con il pulsante destro del mouse nell&#39;area di lavoro e scegliendo Dati > Filtro sessione interrotta.

Nelle espressioni del filtro è possibile fare riferimento al filtro di sessione interrotta come filtro Broken_Session_Filter, anche se non è abilitato per l&#39;area di lavoro corrente. Per ulteriori informazioni, consultate Espressioni [di](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Identifiers) filtro.
