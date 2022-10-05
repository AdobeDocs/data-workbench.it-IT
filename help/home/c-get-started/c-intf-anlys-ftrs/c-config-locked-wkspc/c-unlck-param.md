---
description: Il parametro Sblocca nel file Insight.cfg di un utente specifica se l’utente dispone dell’autorizzazione per sbloccare temporaneamente le aree di lavoro bloccate per la modifica.
title: Impostate il parametro di sblocco
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
exl-id: 5eda919f-4cfe-4692-9dbf-f7cf64fde1de
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 3%

---

# Impostate il parametro di sblocco{#set-the-unlock-parameter}

{{eol}}

Il parametro Sblocca nel file Insight.cfg di un utente specifica se l’utente dispone dell’autorizzazione per sbloccare temporaneamente le aree di lavoro bloccate per la modifica.

Se il parametro Sblocca è già presente nel [!DNL Insight.cfg] file, puoi modificare il parametro utilizzando Data Workbench. Se non è già presente nel [!DNL Insight.cfg] file, è necessario aggiungerlo al file utilizzando un editor di testo, ad esempio Blocco note.

**Per impostare un [!DNL Unlock] nel file Insight.cfg**

1. In un’area di lavoro, fai clic con il pulsante destro del mouse su **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. La [!DNL Insight.cfg] viene aperto il file .
1. Per il parametro Sblocca, digitare true o false. True consente all&#39;utente di sbloccare temporaneamente qualsiasi area di lavoro bloccata, mentre false non lo consente.
1. Per salvare le modifiche di configurazione, fai clic con il pulsante destro del mouse su **[!UICONTROL Insight.cfg (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save as Insight.cfg]**.

**Per aggiungere il parametro Unlock al file Insight.cfg**

1. Passa alla directory di installazione di Data Workbench e apri la [!DNL Insight.cfg] utilizzando un editor di testo, ad esempio Blocco note.
1. Aggiungi il parametro Sblocca alla fine del file, come nell’esempio seguente:

[!DNL Unlock = bool: false]

1. Imposta il valore su true o false. True consente all&#39;utente di sbloccare temporaneamente qualsiasi area di lavoro bloccata, mentre false non lo consente.
1. Salva e chiudi il file.
