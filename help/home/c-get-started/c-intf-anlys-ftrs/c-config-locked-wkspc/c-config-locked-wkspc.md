---
description: È possibile configurare la Data Workbench per consentire solo ad alcuni utenti di modificare determinate aree di lavoro.
title: Configurare un’area di lavoro bloccata
uuid: 0bb264f6-20b9-43d9-903e-1b2422af21d5
exl-id: e31a786e-064e-4f2c-9bf4-7ceafde814c0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 3%

---

# Configurare un’area di lavoro bloccata{#configure-a-locked-workspace}

È possibile configurare la Data Workbench per consentire solo ad alcuni utenti di modificare determinate aree di lavoro.

Mentre un’area di lavoro è bloccata, gli utenti possono effettuare selezioni nella maggior parte delle visualizzazioni e ordinare i dati nelle tabelle, ma in caso contrario non possono modificare l’area di lavoro. Questa funzionalità impedisce agli utenti di apportare modifiche non intenzionali alle aree di lavoro.

I tre elementi seguenti lavorano insieme per controllare il blocco delle aree di lavoro:

* **Un file folder.lock o  *workspace name*.lock:** Un  [!DNL folder.lock] file specifica se le aree di lavoro in una particolare cartella sono bloccate, mentre un  [!DNL name.lock] file workspace specifica se una particolare area di lavoro è bloccata.

* **Il parametro Sblocca nel  [!DNL Insight.cfg] file di un utente:** questo parametro specifica se l’utente può sbloccare temporaneamente le aree di lavoro bloccate.
* **L’opzione di menu Sblocca temporaneamente:** quando il parametro Sblocca nel dell’utente  [!DNL Insight.cfg] è impostato su true, questa opzione viene visualizzata automaticamente nel menu della barra del titolo di ogni area di lavoro bloccata per fornire all’utente un modo per sbloccarla.

Per informazioni sui file [!DNL folder.lock] e dell&#39;area di lavoro [!DNL name.lock], consulta la sezione seguente. Per informazioni sull&#39;impostazione del parametro Sblocca, vedere [Impostazione del parametro Sblocca](../../../../home/c-get-started/c-intf-anlys-ftrs/c-config-locked-wkspc/c-unlck-param.md#concept-b018a85c6217489aa01b17845872df7f). Per informazioni sull&#39;opzione [!DNL Temporarily Unlock menu], vedere [Sblocco di un&#39;area di lavoro](../../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).
