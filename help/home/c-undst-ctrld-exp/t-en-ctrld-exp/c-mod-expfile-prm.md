---
description: Il parametro ExpFile punta alla posizione del file di configurazione dell'esperimento, che definisce l'esperimento.
solution: Insight,Analytics
title: Modifica del parametro ExpFile
topic: Data workbench
uuid: bf146f46-f541-4969-8d90-af1a0c969344
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Modifica del parametro ExpFile{#modifying-the-expfile-parameter}

Il parametro ExpFile punta alla posizione del file di configurazione dell&#39;esperimento, che definisce l&#39;esperimento.

L’impostazione di questo parametro consente di eseguire esperimenti. Per i passaggi necessari per creare il file di configurazione dell&#39;esperimento, consultate [Configurazione e distribuzione dell&#39;esperimento](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

Di seguito è riportato un esempio del parametro ExpFile:

```
ExpFile /home/experiment.txt
```

Questo file di testo delimitato da tabulazioni ( [!DNL .txt]) può trovarsi ovunque nella [!DNL Sensor] cartella e può avere un nome semplice.

Verificate di registrare il percorso della directory degli esperimenti e il nome del file di configurazione specificato, perché dovete salvare il file di configurazione dell&#39;esperimento (da descritto più avanti in questa guida) utilizzando questo nome e in questa directory.

>[!NOTE]
>
>Se questo parametro non viene impostato in modo identico su ogni computer del cluster Web in cui [!DNL Sensor] è installato, la sperimentazione controllata non funziona.

Questa voce può essere preconfigurata e rimanere nel file di [!DNL Sensor] configurazione su base continuativa senza effetti negativi. Se il nome del file di configurazione dell&#39;esperimento specificato non è trovato da [!DNL Sensor] o è vuoto (ovvero esiste ma non ha contenuto), [!DNL Sensor] non esegue l&#39;esperimento, registra un evento di errore sul server HTTP e continua a funzionare normalmente in tutti gli altri aspetti.
