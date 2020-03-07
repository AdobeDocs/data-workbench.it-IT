---
description: Il parametro Sblocca nel file Insight.cfg di un utente specifica se l’utente dispone dell’autorizzazione per sbloccare temporaneamente le aree di lavoro bloccate per la modifica.
solution: Analytics
title: Impostate il parametro unlock
topic: Data workbench
uuid: db094e32-7d82-4f93-a492-a6bed33ae722
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Impostate il parametro unlock{#set-the-unlock-parameter}

Il parametro Sblocca nel file Insight.cfg di un utente specifica se l’utente dispone dell’autorizzazione per sbloccare temporaneamente le aree di lavoro bloccate per la modifica.

Se il parametro Sblocca è già presente nel [!DNL Insight.cfg] file dell&#39;utente, è possibile modificarlo utilizzando Workbench dati. Se non è già presente nel [!DNL Insight.cfg] file dell&#39;utente, è necessario aggiungerlo al file utilizzando un editor di testo, ad esempio Blocco note.

**Per impostare un[!DNL Unlock]parametro esistente nel file Insight.cfg**

1. In un’area di lavoro, fate clic con il pulsante destro del mouse **[!UICONTROL Admin]** > **[!UICONTROL Client Configuration]**. Si apre il [!DNL Insight.cfg] file.
1. Per il parametro Sblocca, digitate true o false. True consente all&#39;utente di sbloccare temporaneamente qualsiasi area di lavoro bloccata, mentre false non lo fa.
1. Per salvare le modifiche alla configurazione, fai clic con il pulsante destro del mouse **[!UICONTROL Insight.cfg (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save as Insight.cfg]**.

**Per aggiungere il parametro Sblocca al file Insight.cfg**

1. Accedere alla directory di installazione di Workbench dati e aprire il [!DNL Insight.cfg] file utilizzando un editor di testo, come Blocco note.
1. Aggiungete il parametro Sblocca alla fine del file, come nell’esempio seguente:

[!DNL Unlock = bool: false]

1. Impostate il valore su true o false. True consente all&#39;utente di sbloccare temporaneamente qualsiasi area di lavoro bloccata, mentre false non lo fa.
1. Salvate e chiudete il file.

