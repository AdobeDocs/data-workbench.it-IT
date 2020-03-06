---
description: Le trasformazioni e le dimensioni utilizzano le condizioni per determinare quando determinate istruzioni o azioni si applicano ai campi di registro.
solution: Analytics
title: Informazioni sulle condizioni
topic: Data workbench
uuid: 882fe761-895c-4226-a019-270c50ae6da2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Informazioni sulle condizioni{#about-conditions}

Le trasformazioni e le dimensioni utilizzano le condizioni per determinare quando determinate istruzioni o azioni si applicano ai campi di registro.

Il parametro Condizione voce di registro utilizza le condizioni per determinare quali voci di registro includere nel processo di costruzione del dataset. Questa appendice descrive i diversi tipi di condizioni disponibili all&#39;interno del server workbench dati.

Una condizione rientra in una delle due categorie seguenti:

* **[!DNL Test Operations]:**[!DNL Compare],[!DNL Not Empty],[!DNL Range][!DNL Regular Expression]e[!DNL String Match]le condizioni vengono utilizzate per verificare i diversi stati nei campi di registro disponibili.

* **[!DNL Boolean Operations]:**Le condizioni[!DNL And],[!DNL Or]e[!DNL Neither]le condizioni sono utilizzate per combinare le operazioni di prova descritte in precedenza. Ad esempio, se si dispone di una[!DNL Range]condizione e di una[!DNL String Match]condizione che devono essere entrambe false per eseguire l&#39;azione appropriata, queste due operazioni dovrebbero essere figlio della[!DNL Neither]condizione. Tenere presente che la[!DNL And]condizione viene utilizzata come radice di tutti i test di condizione nel sistema.

