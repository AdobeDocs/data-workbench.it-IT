---
description: Il workbench dati ora supporta l'IME (Input Method Editor) come processo di immissione di testo secondario per le lingue internazionali.
solution: Analytics
title: Installazione dell’Editor del metodo di input
topic: Data workbench
uuid: 2a4dc6de-9dd7-4280-b410-fb88a135fe45
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Installazione dell’Editor del metodo di input{#installing-the-input-method-editor}

Il workbench dati ora supporta l&#39;IME (Input Method Editor) come processo di immissione di testo secondario per le lingue internazionali.

Gli IME consentono di immettere caratteri internazionali utilizzando una serie di metodi adatti alla lingua locale. Workbench dati offre una finestra di dialogo di immissione che consente di aprire e utilizzare l&#39;IME desiderato per i campi di testo.

>[!NOTE]
>
>Per la versione data workbench 6.1, sarà supportata solo la tastiera cinese semplificato virtuale. L&#39;inserimento di altre lingue tramite l&#39;IME potrebbe causare un comportamento imprevisto.

## Utilizzo di un IME {#section-5f008d75a7b24119ab6aebc55454f927}

Per utilizzare la funzione di immissione del testo IME mobile:

1. Fare clic **[!UICONTROL Alt + Space]** per qualsiasi area di immissione testo.
1. Immettete i valori utilizzando l&#39;IME del sistema.
1. Per chiudere la finestra di dialogo di input, selezionate il **[!UICONTROL Enter]** tasto o fate clic sul **[!UICONTROL OK]** pulsante.

   La finestra di dialogo scompare e i caratteri vengono visualizzati nel campo selezionato.

**Aggiornamento del file Insight.cfg**

Per utilizzare l&#39;IME, è necessario aggiornare il [!DNL Insight.cfg] file con la seguente impostazione:

```
Localized IME = bool: true
```

Se questa impostazione non esiste nel file di configurazione, premere **[!UICONTROL Alt + Space]** non attiva la funzione IME.

**Iniziare Insight in un&#39;altra lingua:** Per supportare meglio le risorse localizzate come una schermata iniziale e per supportare più lingue in futuro, il workbench dati richiede argomenti della riga di comando che identifichino la lingua da caricare. La lingua predefinita è l’inglese.

L&#39;avvio del workbench dati in cinese richiede di richiamare [!DNL Insight.exe] con l&#39;argomento &quot;-zh-cn&quot;:

```
Insight.exe -zh-cn
```

Questi argomenti della riga di comando non fanno distinzione tra maiuscole e minuscole.
