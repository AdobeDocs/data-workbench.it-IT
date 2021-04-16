---
description: Le operazioni booleane combinano i risultati delle operazioni di test, che funzionano come elementi secondari delle operazioni booleane.
title: Operazioni booleane
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Operazioni booleane{#boolean-operations}

Le operazioni booleane combinano i risultati delle operazioni di test, che funzionano come elementi secondari delle operazioni booleane.

Per informazioni sulle operazioni di test, vedere [Operazioni di test](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Quando si definisce un&#39;operazione [!DNL boolean], è possibile definire zero o più elementi secondari per l&#39;operazione.

**Aggiunta di una condizione figlio a un&#39;operazione booleana**

1. Fare clic con il pulsante destro del mouse sul nome o sul numero corrispondente all&#39;operazione [!DNL Boolean].
1. Fai clic su **[!UICONTROL Add new child]** e scegli uno dei tipi di condizioni disponibili da aggiungere.
1. Ripetere i passaggi 1 e 2 finché non sono state aggiunte tutte le condizioni figlio desiderate per l&#39;operazione [!DNL Boolean].

   >[!NOTE]
   >
   >Quando si fa clic con il pulsante destro del mouse sul nome o sul numero corrispondente a un&#39;operazione [!DNL Boolean], viene visualizzata l&#39;opzione di menu [!DNL Add new sibling]. Un elemento di pari livello è un’altra condizione che si trova nella stessa posizione relativa nella gerarchia delle condizioni dell’operazione [!DNL Boolean] su cui hai fatto clic con il pulsante destro del mouse. L’aggiunta di un nuovo elemento di pari livello per un’operazione [!DNL Boolean] equivale all’aggiunta di una nuova condizione facendo clic con il pulsante destro del mouse sul parametro [!DNL Condition] o [!DNL Log Entry Condition] .

**Per rimuovere una condizione figlio da un&#39;operazione booleana:**

1. Fare clic con il pulsante destro del mouse sul nome della condizione figlio o sul numero corrispondente alla condizione figlio che si desidera rimuovere dall&#39;operazione [!DNL Boolean].
1. Fare clic su **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, dove numero è il numero corrispondente alla condizione figlio che si desidera rimuovere.

Questa sezione illustra le seguenti condizioni:

* [E](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Nessuno](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [Oppure](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## E {#section-a14dba4b07cc4ab9aeb20868f773db7c}

La condizione [!DNL And] può avere zero o più condizioni figlio e restituisce true quando nessuno dei nodi figlio restituisce false.

La condizione [!DNL And] costituisce il funzionamento principale di tutti i test di condizione all’interno del server di Data Workbench. Se la condizione [!DNL And] non contiene elementi secondari, la condizione restituisce true e l&#39;operazione associata continua. Per questo motivo, le azioni che hanno solo la condizione [!DNL And] come test della condizione vengono sempre eseguite e perché vengono utilizzate come root per tutti i test della condizione.

Questo esempio mostra come viene utilizzata una condizione [!DNL And] per assicurarsi che la trasformazione [!DNL Copy] si verifichi quando si è verificata solo la data della voce di registro nell&#39;anno 2006 e che la pagina richiesta sia [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Né {#section-7e48b61266aa43ecbc48b979bf5e939b}

La condizione [!DNL Neither] può avere zero o più condizioni figlio e restituisce false se una qualsiasi delle condizioni figlio restituisce true. Se la condizione [!DNL Neither] non contiene elementi figlio, nessuno dei relativi elementi figlio può restituire true. Di conseguenza, la condizione [!DNL Neither] restituisce true.

L’esempio seguente mostra una condizione [!DNL Neither] con due condizioni [!DNL Range] come elementi secondari. Come definito, la condizione [!DNL Neither] esclude le voci di registro che si sono verificate tra il 1° gennaio 2007 e il 10 gennaio 2007 o tra il 12 gennaio 2007 e il 14 gennaio 2007. Tale condizione può essere utilizzata come [!DNL Log Entry Condition] per eliminare le transazioni da un set di dati durante i periodi in cui si è verificato un problema noto con i dati raccolti.

![](assets/cfg_Condition_NeitherCondition.png)

## Oppure {#section-a3aa0f56b6234f2680fa81939228326b}

La condizione [!DNL Or] può avere zero o più condizioni figlio e restituisce true se almeno una delle sue condizioni figlio restituisce true. Se la condizione [!DNL Or] non contiene elementi figlio, nessuno dei relativi elementi figlio può restituire true. Di conseguenza, la condizione [!DNL Or] restituisce false.

Questo esempio mostra la condizione [!DNL Or] con una condizione [!DNL String Match] e una condizione [!DNL Range] come elementi secondari. La condizione [!DNL Or] è soddisfatta solo se il valore [!DNL x-hasproblem] del log è impostato su yes o se la voce del log si è verificata nell&#39;intervallo di tempo compreso tra il 1° gennaio 2007 e il 10 gennaio 2007.

![](assets/cfg_Condition_OrCondition.png)
