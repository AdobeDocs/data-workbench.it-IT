---
description: Le trasformazioni e le dimensioni utilizzano condizioni per determinare quando determinate istruzioni o azioni si applicano ai campi di registro.
title: Informazioni sulle condizioni
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---

# Informazioni sulle condizioni{#about-conditions}

Le trasformazioni e le dimensioni utilizzano condizioni per determinare quando determinate istruzioni o azioni si applicano ai campi di registro.

Il parametro Log Entry Condition utilizza condizioni per determinare quali voci di registro devono essere incluse nel processo di costruzione del set di dati. La presente appendice descrive i diversi tipi di condizioni disponibili all’interno del server di Data Workbench.

Una condizione rientra in una delle due categorie seguenti:

* **[!DNL Test Operations]:** [!DNL Compare],  [!DNL Not Empty],  [!DNL Range],  [!DNL Regular Expression] e  [!DNL String Match] le condizioni vengono utilizzate per testare i diversi stati nei campi di log disponibili.

* **[!DNL Boolean Operations]:** Le  [!DNL And]condizioni  [!DNL Or],  [!DNL Neither]  e vengono utilizzate per combinare le operazioni di prova descritte sopra. Ad esempio, se disponi di una condizione [!DNL Range] e di una condizione [!DNL String Match] che devono essere entrambe false per eseguire l’azione appropriata, queste due operazioni saranno figlio della condizione [!DNL Neither] . La condizione [!DNL And] viene utilizzata come radice di tutti i test di condizione nel sistema.
