---
description: Prima di configurare l’esperimento, è necessario creare il contenuto alternativo da utilizzare nell’esperimento.
solution: Analytics,Analytics
title: Creazione del contenuto di prova
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
exl-id: fd46c6af-37e8-452a-880d-147b7d0cfe21
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 4%

---

# Creazione del contenuto di prova{#creating-the-test-content}

Prima di configurare l’esperimento, è necessario creare il contenuto alternativo da utilizzare nell’esperimento.

Il gruppo di controllo viene inviato all’URI originale, mentre il gruppo di test viene inviato al nuovo URI alternativo.

Per evitare confusione, non riutilizzare i nomi dei file dei gruppi di test. Ad esempio, se esegui un esperimento utilizzando un file di gruppo di test denominato [!DNL test2.asp], non utilizzare [!DNL test2.asp] come nome per il file di test nell’esperimento successivo.

Per l’ipotesi che lo spostamento del collegamento grafico &quot;Richiedi una demo&quot; sulla tua home page influisca sulla conversione del visitatore, creiamo la home page alternativa contenente il collegamento grafico &quot;Richiedi una demo&quot; nella nuova posizione. Nella sezione seguente viene descritto come specificare la sostituzione dell’URI del gruppo di controllo [!DNL index.asp] con l’URI del gruppo di test [!DNL index2.asp] per una determinata percentuale di visitatori.
