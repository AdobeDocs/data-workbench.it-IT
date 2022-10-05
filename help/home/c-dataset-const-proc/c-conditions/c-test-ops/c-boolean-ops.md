---
description: Le operazioni booleane combinano i risultati delle operazioni di test, che funzionano come elementi secondari delle operazioni booleane.
title: Operazioni booleane
uuid: 01143bc2-c867-434c-8028-86d4708e8b80
exl-id: 5b01e614-5603-43ff-9be4-aa329cca1645
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 1%

---

# Operazioni booleane{#boolean-operations}

{{eol}}

Le operazioni booleane combinano i risultati delle operazioni di test, che funzionano come elementi secondari delle operazioni booleane.

Per informazioni sulle operazioni di test, vedi [Operazioni di test](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-test-ops.md#concept-c4bf6cb9e7a94cc7ac49ca9b0b1a2144). Quando definisci un [!DNL boolean] È possibile definire zero o più elementi secondari per l&#39;operazione.

**Aggiunta di una condizione figlio a un&#39;operazione booleana**

1. Fai clic con il pulsante destro del mouse sul nome o sul numero corrispondente al [!DNL Boolean] funzionamento.
1. Fai clic su **[!UICONTROL Add new child]** e scegli uno dei tipi di condizioni disponibili da aggiungere.
1. Ripetere i passaggi 1 e 2 finché non sono state aggiunte tutte le condizioni figlio desiderate per la [!DNL Boolean] funzionamento.

   >[!NOTE]
   >
   >Quando fai clic con il pulsante destro del mouse sul nome o sul numero corrispondente a un [!DNL Boolean] viene visualizzata l&#39;operazione [!DNL Add new sibling] opzione di menu. Un pari livello è un’altra condizione nella stessa posizione relativa nella gerarchia delle condizioni del [!DNL Boolean] operazione su cui hai fatto clic con il pulsante destro del mouse. Aggiunta di un nuovo elemento di pari livello per un [!DNL Boolean] equivale ad aggiungere una nuova condizione facendo clic con il pulsante destro del mouse sul pulsante [!DNL Condition] o [!DNL Log Entry Condition] parametro .

**Per rimuovere una condizione figlio da un&#39;operazione booleana:**

1. Fare clic con il pulsante destro del mouse sul nome della condizione figlio o sul numero corrispondente alla condizione figlio che si desidera rimuovere dalla [!DNL Boolean] funzionamento.
1. Fai clic su **[!UICONTROL Remove]** &lt;* **[!UICONTROL #number]***>, dove numero è il numero corrispondente alla condizione figlio che si desidera rimuovere.

Questa sezione illustra le seguenti condizioni:

* [E](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a14dba4b07cc4ab9aeb20868f773db7c)
* [Nessuno](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-7e48b61266aa43ecbc48b979bf5e939b)
* [Oppure](../../../../home/c-dataset-const-proc/c-conditions/c-test-ops/c-boolean-ops.md#section-a3aa0f56b6234f2680fa81939228326b)

## E {#section-a14dba4b07cc4ab9aeb20868f773db7c}

La [!DNL And] La condizione può avere zero o più condizioni figlio e restituisce true quando nessuno dei nodi figlio restituisce false.

La [!DNL And] condizione forma il funzionamento principale di tutti i test di condizione all’interno del server di Data Workbench. Se la [!DNL And] condizione non contiene elementi figlio, la condizione restituisce true e l&#39;operazione associata procede. Per questo motivo le azioni che hanno solo [!DNL And] come il test della condizione viene sempre eseguito e perché viene utilizzato come radice per tutti i test della condizione.

Questo esempio mostra come [!DNL And] viene utilizzata per assicurarsi che la [!DNL Copy] La trasformazione si verifica quando solo la data della voce di registro si è verificata nell&#39;anno 2006 e che la pagina richiesta è stata [!DNL /products/purchase.asp].

![](assets/cfg_Condition_AndCondition.png)

## Nessuno {#section-7e48b61266aa43ecbc48b979bf5e939b}

La [!DNL Neither] La condizione può avere zero o più condizioni figlio e restituisce false se una qualsiasi delle condizioni figlio restituisce true. Se la [!DNL Neither] condizione non contiene figli, nessuno dei suoi figli può tornare vero. Di conseguenza, il [!DNL Neither] La condizione restituisce true.

L’esempio seguente mostra un [!DNL Neither] condizione con due [!DNL Range] condizioni come i suoi figli. Come definito, la [!DNL Neither] Questa condizione esclude le voci di registro che si sono verificate tra il 1° gennaio 2007 e il 10 gennaio 2007 o tra il 12 gennaio 2007 e il 14 gennaio 2007. Tale condizione potrebbe essere utilizzata come [!DNL Log Entry Condition] eliminare le transazioni da un set di dati durante i periodi in cui si è verificato un problema noto con i dati raccolti.

![](assets/cfg_Condition_NeitherCondition.png)

## Oppure {#section-a3aa0f56b6234f2680fa81939228326b}

La [!DNL Or] La condizione può avere zero o più condizioni figlio e restituisce true se almeno una delle sue condizioni figlio restituisce true. Se la [!DNL Or] condizione non contiene figli, nessuno dei suoi figli può tornare vero. Di conseguenza, il [!DNL Or] La condizione restituisce false.

Questo esempio mostra la [!DNL Or] condizione con [!DNL String Match] condizione e [!DNL Range] come i suoi figli. La [!DNL Or] la condizione è soddisfatta solo se la voce di registro ha [!DNL x-hasproblem] valore impostato su yes o la voce di registro si è verificata nell&#39;intervallo di tempo compreso tra il 1° gennaio 2007 e il 10 gennaio 2007.

![](assets/cfg_Condition_OrCondition.png)
