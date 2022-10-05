---
description: Se non si desidera ereditare un file di configurazione da un profilo interno o da un altro profilo ereditato (ovvero se si desidera che le istruzioni contenute nel file vengano ignorate durante la creazione del set di dati), ma non si desidera modificare il file, è possibile creare un file vuoto (zero byte) con lo stesso nome e archiviare il file in un altro profilo.
title: Nascondere i file di configurazione del set di dati
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
exl-id: 327847d1-421a-4ed1-9a5f-2491765a34bd
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 2%

---

# Nascondere i file di configurazione del set di dati{#hiding-dataset-configuration-files}

{{eol}}

Se non si desidera ereditare un file di configurazione da un profilo interno o da un altro profilo ereditato (ovvero se si desidera che le istruzioni contenute nel file vengano ignorate durante la creazione del set di dati), ma non si desidera modificare il file, è possibile creare un file vuoto (zero byte) con lo stesso nome e archiviare il file in un altro profilo.

**Per eseguire un file di configurazione di set di dati a zero byte**

1. In [!DNL Profile Manager], apri le cartelle e le sottocartelle necessarie per individuare il file a byte zero.
1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file e fai clic su **[!UICONTROL Make Local]**.
1. Apri il file locale in un editor di testo come Blocco note ed elimina il relativo contenuto.
1. Salva e chiudi il file.
1. In [!DNL Profile Manager], salva il file a byte zero in un profilo a destra del profilo in cui si trova il file originale. Si desidera che il file a byte zero abbia la precedenza sul file originale.

   In [!DNL Profile Manager], un trattino (-), invece di un segno di spunta, in una colonna identifica il file a byte zero come mostrato nell’esempio seguente.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

Quando rielabora il set di dati, il set di dati non contiene i componenti del set di dati definiti dal file originale.

>[!NOTE]
>
>Se un file di configurazione a byte zero definisce una dimensione estesa utilizzata in una visualizzazione o una definizione di metrica, Data Workbench genera un errore per tale visualizzazione o metrica, rispettivamente.

È inoltre possibile utilizzare file a byte zero per spostare una metrica, una dimensione o un filtro in un’altra posizione nel profilo o per nascondere le voci del menu. Per informazioni, consulta la sezione *Guida utente di Data Workbench*.
