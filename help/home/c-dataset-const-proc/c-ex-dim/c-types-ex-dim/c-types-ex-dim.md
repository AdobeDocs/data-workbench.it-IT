---
description: Insight Server consente di definire dimensioni numerabili, semplici, da molti a molti, numeriche, denormali e temporali da includere nel set di dati.
title: Tipi di dimensioni estese
uuid: 68f42903-0599-43f2-8b5b-da9e171d77b1
exl-id: 13a52ece-b68b-45bc-ac2d-d68c91742c9d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 2%

---

# Tipi di dimensioni estese{#types-of-extended-dimensions}

Insight Server consente di definire dimensioni numerabili, semplici, da molti a molti, numeriche, denormali e temporali da includere nel set di dati.

Ogni tipo di dimensione dispone di un set di parametri i cui valori vengono modificati per fornire istruzioni specifiche affinché Insight Server crei le dimensioni durante la fase di trasformazione della costruzione del set di dati.

Sebbene alcuni dei parametri differiscano tra i tipi di dimensione, tutti richiedono la specifica di una dimensione padre (il parametro Parent). La dimensione padre determina quali voci di registro dalle origini di registro vengono fornite come input per la nuova dimensione. In altre parole, le voci di registro associate agli elementi della dimensione padre sono quelle associate alla nuova dimensione prima di applicare qualsiasi filtro. La dimensione padre determina anche la posizione della nuova dimensione all’interno della gerarchia del set di dati, denominata schema del set di dati. Per informazioni sull&#39;interfaccia che mostra lo schema del set di dati, vedere [Strumenti di configurazione del set di dati](../../../../home/c-dataset-const-proc/c-dataset-config-tools/c-dataset-config-tools.md#concept-6e058b7691834cf79dcfd1573f78d4f5).

Dopo che Insight Server utilizza la dimensione padre per determinare quali voci di registro devono essere considerate nella creazione della dimensione, applica le condizioni specificate (il parametro Condition ) per svuotare le voci di registro che non soddisfano la condizione. Il server identifica quindi il valore del campo di input specificato (il parametro Input) per ogni voce di registro e applica l&#39;operazione specificata (il parametro Operation), se applicabile.

>[!NOTE]
>
>Se una voce di registro non soddisfa le condizioni di una dimensione estesa, Insight Server sostituisce i valori vuoti per tutti i campi della voce di registro. La voce di registro effettiva esiste ancora e l&#39;operazione specificata determina se viene utilizzato il valore vuoto del campo [!DNL Input].
