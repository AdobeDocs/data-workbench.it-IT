---
description: Il parametro ExpFile punta alla posizione del file di configurazione dell'esperimento, che definisce l'esperimento.
solution: Analytics
title: Modifica del parametro ExpFile
uuid: bf146f46-f541-4969-8d90-af1a0c969344
exl-id: 9c527ef9-aeda-4d83-8b98-a7dccbd55fe8
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 3%

---

# Modifica del parametro ExpFile{#modifying-the-expfile-parameter}

Il parametro ExpFile punta alla posizione del file di configurazione dell&#39;esperimento, che definisce l&#39;esperimento.

L&#39;impostazione di questo parametro consente di eseguire esperimenti. Per i passaggi necessari per creare il file di configurazione dell&#39;esperimento, vedi [Configurazione e distribuzione dell’esperimento](../../../home/c-undst-ctrld-exp/t-crt-ctrld-exp/c-cnfg-dply-exp.md#concept-50f1de0242904698937bb72b3ea1b429).

Di seguito è riportato un esempio del parametro ExpFile :

```
ExpFile /home/experiment.txt
```

Questo file di testo delimitato da tabulazioni ( [!DNL .txt]) può trovarsi in qualsiasi punto della [!DNL Sensor] e può avere un nome conveniente.

Assicurati di registrare la posizione della directory degli esperimenti e il nome del file di configurazione specificato perché devi salvare il file di configurazione dell’esperimento (da descritto più avanti in questa guida) utilizzando questo nome e in questa directory.

>[!NOTE]
>
>Se non si imposta questo parametro in modo identico su ogni computer del cluster Web in cui un [!DNL Sensor] è installato, la sperimentazione controllata non funziona.

Questa voce può essere preconfigurata e rimanere nel [!DNL Sensor] file di configurazione su base continuativa senza effetti negativi. Se il nome del file di configurazione dell&#39;esperimento specificato non viene trovato da [!DNL Sensor] o è vuoto (cioè esiste ma non ha contenuto), [!DNL Sensor] non esegue l’esperimento, registra un evento di errore sul server HTTP e continua a funzionare normalmente per tutti gli altri aspetti.
