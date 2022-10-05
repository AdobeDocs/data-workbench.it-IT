---
description: I filtri di profilo vincolano l’ambito dei dati disponibili da un set di dati.
title: Filtri di profilo incorporati
uuid: d6854d2c-4643-476e-8a44-f188e18cb115
exl-id: bb167487-415d-44a8-9a0a-9a76d90ba5c0
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 1%

---

# Filtri di profilo incorporati{#built-in-profile-filters}

{{eol}}

I filtri di profilo vincolano l’ambito dei dati disponibili da un set di dati.

Oltre ai filtri di elaborazione e trasformazione dei registri che possono essere applicati prima o durante la creazione di un set di dati, sono disponibili altri filtri di profilo che influiscono sull’ambito dei dati disponibili per la selezione da un set di dati. Questa sezione descrive solo l&#39;ultimo tipo di filtri speciali.

I seguenti filtri di profilo sono disponibili per l’utente dopo la creazione di un set di dati:

* Filtro per sottoinsiemi di dati
* Filtro sessione interrotto

>[!NOTE]
>
>È possibile creare e applicare altri filtri tramite la loro presenza nella directory Filtri di un profilo.

## Sottoimpostazione dati {#section-0defb44315d94254ab6e629ec3d6f420}

Un sottoinsieme di dati agisce come filtro di dati consentendoti di selezionare solo gli elementi dimensionali dei dati che ti interessano.

La creazione di sottoinsiemi di dati riduce il tempo necessario per calcolare le risposte esatte alle query. Se il sottoinsieme di dati specificato è sufficientemente piccolo, Data Workbench può recuperare tutti i dati necessari da Insight Server e rispondere alle domande sul sottoinsieme in modo rapido e preciso. Questa funzione è particolarmente utile se sai che, ad esempio, l’analisi di un giorno di dati o sessioni da un particolare referente richiederà diverse ore.

Gli utenti possono creare autonomamente sottoinsiemi di dati oppure accedere ai sottoinsiemi di dati definiti in un profilo ereditato o di lavoro. Quando un utente crea un sottoinsieme del set di dati (selezionando i dati desiderati in Insight e facendo clic con il pulsante destro del mouse nell’area di lavoro e scegliendo Dati > Sottoinsieme), viene creato un file Subset.filter di dati nella cartella Filtri all’interno della directory del profilo utente. Questo filtro definisce il sottoinsieme di dati selezionato e lo salva per un utilizzo futuro.

>[!NOTE]
>
>Puoi creare più sottoinsiemi di dati e attivarli per visualizzarne diverse parti. Quando si desidera visualizzare tutti i dati, si ricorda di disattivare l’impostazione dei dati secondari. In caso contrario, i valori delle metriche non saranno rappresentativi di tutti i dati nel set di dati.

## Filtro sessione interrotto {#section-1608e97da6464b11aea27cbb7f3160e4}

Il filtro di sessione interrotta è una formula metrica che può essere facilmente modificata per soddisfare qualsiasi requisito di filtro. Nei profili sito predefiniti, il filtro sessioni interrotte è configurato per includere tutti i visitatori con un flag Visitorized impostato su 1. Il valore 1 indica la presenza di un cookie di tracciamento per quel visitatore.

Di seguito è riportato il testo del file Filter.filter della sessione interrotto predefinito fornito da Adobe nel pacchetto di rilascio per i profili del sito.

```
entity = derived_filter:
   formula = string: Visitorized_Flag="1"
   model = ref: wdata/model
```

Per impostazione predefinita, le aree di lavoro dispongono del filtro Sessione interrotta applicato sia alla selezione che ai relativi parametri di riferimento e può essere attivato facendo clic con il pulsante destro del mouse nell’area di lavoro e facendo clic su Dati > Filtro sessione interrotta.

È possibile fare riferimento al filtro sessione interrotta nelle espressioni filtro come Broken_Session_Filter, anche se non è abilitato per l&#39;area di lavoro corrente. Vedi [espressioni filtro](https://experienceleague.adobe.com/docs/data-workbench/using/client/t-open-ins.html#Syntax_for_Identifiers) per ulteriori informazioni.
