---
description: Se non si desidera ereditare un file di configurazione da un profilo ereditato interno o da un altro (vale a dire, si desidera che le istruzioni nel file vengano ignorate durante la creazione del set di dati), ma non si desidera modificare il file, è possibile creare un file vuoto (zero byte) con lo stesso nome e memorizzare il file in un altro profilo.
solution: Analytics
title: Nascondere i file di configurazione del set di dati
topic: Data workbench
uuid: eb33cf54-e067-4af2-a10e-7ffe43910e4f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Nascondere i file di configurazione del set di dati{#hiding-dataset-configuration-files}

Se non si desidera ereditare un file di configurazione da un profilo ereditato interno o da un altro (vale a dire, si desidera che le istruzioni nel file vengano ignorate durante la creazione del set di dati), ma non si desidera modificare il file, è possibile creare un file vuoto (zero byte) con lo stesso nome e memorizzare il file in un altro profilo.

**Per azzerare un file di configurazione dataset**

1. In [!DNL Profile Manager], aprite le cartelle e sottocartelle necessarie per individuare il file a zero.
1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto al nome del file, quindi fare clic **[!UICONTROL Make Local]**.
1. Aprite il file locale in un editor di testo come Blocco note ed eliminatene il contenuto.
1. Salvate e chiudete il file.
1. In [!DNL Profile Manager], salvare il file a byte zero in un profilo a destra del profilo in cui risiede il file originale. Il file a byte zero deve avere la precedenza rispetto al file originale.

   In [!DNL Profile Manager], un trattino (-), invece di un segno di spunta, in una colonna identifica il file a byte zero come mostrato nell&#39;esempio seguente.

   ![](assets/vis_ProfileManager_ZeroByteFile.png)

Quando si rielabora il set di dati, il set di dati non contiene i componenti del set di dati definiti dal file originale.

>[!NOTE]
>
>Se si crea un file di configurazione a byte zero che definisce una dimensione estesa utilizzata in una visualizzazione o una definizione di metrica, il workbench dati genera un errore per tale visualizzazione o metrica, rispettivamente.

È inoltre possibile utilizzare file a byte zero per spostare una metrica, una dimensione o un filtro in un&#39;altra posizione nel profilo o per nascondere le voci di menu. Per ulteriori informazioni, vedere la Guida *utente di Workbench* dati.
