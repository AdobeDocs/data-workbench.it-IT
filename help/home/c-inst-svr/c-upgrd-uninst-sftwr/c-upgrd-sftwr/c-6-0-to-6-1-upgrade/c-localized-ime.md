---
description: Data Workbench ora supporta l’IME (Input Method Editor) come processo di immissione di testo secondario per le lingue internazionali.
title: Installazione di Input Method Editor
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
exl-id: 3fcc58f5-29a9-427e-831a-44d527614b56
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 4%

---

# Installazione di Input Method Editor{#installing-the-input-method-editor}

{{eol}}

Data Workbench ora supporta l’IME (Input Method Editor) come processo di immissione di testo secondario per le lingue internazionali.

Gli IME consentono di immettere caratteri internazionali utilizzando diversi metodi adatti alla lingua locale. Data Workbench fornisce una finestra di dialogo di input che consente di aprire e utilizzare l’IME desiderato per i campi di testo.

>[!NOTE]
>
>Per la versione 6.1 di Data Workbench, sarà supportato solo la tastiera cinese semplificata virtuale. L&#39;immissione di altre lingue tramite l&#39;IME potrebbe causare un comportamento imprevisto.

## Utilizzo di un IME {#section-5f008d75a7b24119ab6aebc55454f927}

Per utilizzare la funzione di immissione testo IME mobile:

1. Fai clic su **[!UICONTROL Alt + Space]** per qualsiasi area di immissione testo.
1. Immettere i valori utilizzando l&#39;IME del sistema.
1. Chiudi la finestra di dialogo di input selezionando la **[!UICONTROL Enter]** o fai clic su **[!UICONTROL OK]** pulsante .

   La finestra di dialogo scompare e i caratteri vengono quindi visualizzati nel campo selezionato.

**Aggiornamento del file Insight.cfg**

Per utilizzare l&#39;IME, è necessario aggiornare il [!DNL Insight.cfg] file con questa impostazione:

```
Localized IME = bool: true
```

Se questa impostazione non esiste nel file di configurazione, premere **[!UICONTROL Alt + Space]** non attiva la funzione IME.

**Avviare Insight in un’altra lingua:** Per supportare meglio le risorse localizzate come una schermata iniziale e in futuro più lingue, Data Workbench richiede argomenti a riga di comando che identificano la lingua da caricare. La lingua predefinita è l’inglese.

Per avviare Data Workbench in cinese è necessario richiamare [!DNL Insight.exe] con l’argomento &quot;-zh-cn&quot;:

```
Insight.exe -zh-cn
```

Questi argomenti della riga di comando non sono sensibili all’uso di maiuscole e minuscole.
