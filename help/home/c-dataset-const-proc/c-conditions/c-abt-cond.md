---
description: Le trasformazioni e le dimensioni utilizzano condizioni per determinare quando determinate istruzioni o azioni si applicano ai campi di registro.
title: Informazioni sulle condizioni
uuid: 882fe761-895c-4226-a019-270c50ae6da2
exl-id: 0d44282f-1327-4f11-90fc-7e6a2ef8dc76
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 2%

---

# Informazioni sulle condizioni{#about-conditions}

{{eol}}

Le trasformazioni e le dimensioni utilizzano condizioni per determinare quando determinate istruzioni o azioni si applicano ai campi di registro.

Il parametro Log Entry Condition utilizza condizioni per determinare quali voci di registro devono essere incluse nel processo di costruzione del set di dati. La presente appendice descrive i diversi tipi di condizioni disponibili all’interno del server di Data Workbench.

Una condizione rientra in una delle due categorie seguenti:

* **[!DNL Test Operations]:** [!DNL Compare], [!DNL Not Empty], [!DNL Range], [!DNL Regular Expression]e [!DNL String Match] vengono utilizzate per verificare stati diversi nei campi di log disponibili.

* **[!DNL Boolean Operations]:** La [!DNL And], [!DNL Or]e [!DNL Neither] si utilizzano le condizioni per combinare le operazioni di prova descritte in precedenza. Ad esempio, se hai una [!DNL Range] condizione e [!DNL String Match] condizione che deve essere entrambe false per intraprendere l&#39;azione appropriata, si renderebbe queste due operazioni figli del [!DNL Neither] condizione. Tieni presente che [!DNL And] viene utilizzata come radice di tutti i test di condizione nel sistema.
