---
description: Workbench dati può essere configurato per consentire solo ad alcuni utenti di modificare determinate aree di lavoro.
solution: Analytics
title: Configurare un'area di lavoro bloccata
topic: Data workbench
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurare un&#39;area di lavoro bloccata{#configure-a-locked-workspace}

Workbench dati può essere configurato per consentire solo ad alcuni utenti di modificare determinate aree di lavoro.

Mentre un’area di lavoro è bloccata, gli utenti possono effettuare selezioni nella maggior parte delle visualizzazioni e ordinare i dati nelle tabelle, ma non possono altrimenti modificare l’area di lavoro. Questa funzionalità impedisce agli utenti di apportare modifiche non intenzionali alle aree di lavoro.

I tre elementi seguenti consentono di controllare il blocco degli spazi di lavoro:

* **Un file folder.lock o nome **area di lavoro.lock:** Un [!DNL folder.lock] [!DNL name.lock] file specifica se le aree di lavoro di una determinata cartella sono bloccate, mentre un file di area di lavoro specifica se una particolare area di lavoro è bloccata.

* **Il parametro Sblocca nel[!DNL Insight.cfg]file di un utente:** Questo parametro specifica se l&#39;utente può sbloccare temporaneamente le aree di lavoro bloccate.
* **Opzione di menu Sblocca temporaneamente:** Quando il parametro Sblocca nell&#39;area dell&#39;utente [!DNL Insight.cfg] è impostato su true, questa opzione viene visualizzata automaticamente nel menu della barra del titolo di ogni area di lavoro bloccata per consentire all&#39;utente di sbloccarla.

Per informazioni sui [!DNL folder.lock] file dell’area di lavoro e sui [!DNL name.lock] file, consultate la sezione seguente. Per informazioni sull’impostazione del parametro Sblocca, consultate [Impostazione del parametro](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f)Sblocca. Per informazioni sull’ [!DNL Temporarily Unlock menu] opzione, consultate [Sblocco di un’area di lavoro](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
