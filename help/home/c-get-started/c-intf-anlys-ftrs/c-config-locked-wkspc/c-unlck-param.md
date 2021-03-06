---
description: Il parametro Sblocca nel file Insight.cfg di un utente specifica se l’utente dispone dell’autorizzazione per sbloccare temporaneamente le aree di lavoro bloccate per la modifica.
title: Impostate il parametro di sblocco
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# Impostate il parametro di sblocco{#set-the-unlock-parameter}

Il parametro Sblocca nel file Insight.cfg di un utente specifica se l’utente dispone dell’autorizzazione per sbloccare temporaneamente le aree di lavoro bloccate per la modifica.

Se il parametro Sblocca è già presente nel file dell’utente [!DNL Insight.cfg], puoi modificare il parametro utilizzando Data Workbench. Se non è già presente nel file [!DNL Insight.cfg] dell’utente, è necessario aggiungerlo al file utilizzando un editor di testo, ad esempio Blocco note.

**Per impostare un  [!DNL Unlock] parametro esistente nel file Insight.cfg**

1. In un’area di lavoro, fai clic con il pulsante destro del mouse su **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. Viene aperto il file [!DNL Insight.cfg] .
1. Per il parametro Sblocca, digitare true o false. True consente all&#39;utente di sbloccare temporaneamente qualsiasi area di lavoro bloccata, mentre false non lo consente.
1. Per salvare le modifiche di configurazione, fai clic con il pulsante destro del mouse su **[!UICONTROL Insight.cfg (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save as Insight.cfg]**.

**Per aggiungere il parametro Unlock al file Insight.cfg**

1. Accedi alla directory di installazione di Data Workbench e apri il file [!DNL Insight.cfg] utilizzando un editor di testo, ad esempio Blocco note.
1. Aggiungi il parametro Sblocca alla fine del file, come nell’esempio seguente:

[!DNL Unlock = bool: false]

1. Imposta il valore su true o false. True consente all&#39;utente di sbloccare temporaneamente qualsiasi area di lavoro bloccata, mentre false non lo consente.
1. Salva e chiudi il file.
