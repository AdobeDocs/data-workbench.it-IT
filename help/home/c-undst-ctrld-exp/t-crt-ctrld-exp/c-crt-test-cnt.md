---
description: Prima di configurare l’esperimento, dovete creare il contenuto alternativo da utilizzare nell’esperimento.
solution: Insight,Analytics
title: Creazione del contenuto di prova
topic: Data workbench
uuid: d7996522-38a6-4bb8-9736-d71157c17b45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Creazione del contenuto di prova{#creating-the-test-content}

Prima di configurare l’esperimento, dovete creare il contenuto alternativo da utilizzare nell’esperimento.

Il gruppo di controllo viene inviato all’URI originale, mentre il gruppo di test viene inviato al nuovo URI alternativo.

Per evitare confusione, non riutilizzate i nomi dei file dei gruppi di test. Ad esempio, se eseguite un esperimento utilizzando un file di gruppo di test denominato [!DNL test2.asp], non utilizzate [!DNL test2.asp] come nome il file di test nell&#39;esperimento successivo.

Per l&#39;ipotesi che spostando il collegamento grafico &quot;Richiedi una demo&quot; sulla pagina principale si verifichi un impatto sulla conversione del visitatore, creeremo la pagina principale alternativa contenente il collegamento grafico &quot;Richiedi una demo&quot; nella nuova posizione. Nella sezione seguente viene descritto come specificare quindi che l’URI del gruppo di controllo deve [!DNL index.asp] essere sostituito con l’URI del gruppo di test [!DNL index2.asp] per una determinata percentuale di visitatori.
