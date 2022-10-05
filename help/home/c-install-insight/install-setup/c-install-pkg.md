---
description: File inclusi nel pacchetto di installazione Data Workbench.
title: File inclusi nel pacchetto di installazione
uuid: 46cda536-ea71-4840-bd7f-3fe9e0242c33
exl-id: 086fb49c-d492-4670-938b-7ede70a7cd16
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 5%

---

# File inclusi nel pacchetto di installazione{#files-included-in-the-installation-package}

{{eol}}

File inclusi nel pacchetto di installazione Data Workbench.

Le seguenti directory sono incluse nel pacchetto Insight .

## File di programma {#section-ddb14bf42cdd4dc7a6b4310a5b4388e4}

L&#39;eseguibile della workstation (**[!DNL Insight.exe]**) e i file di supporto vengono installati per impostazione predefinita in questa cartella.

```
C:\Program Files\Adobe\Adobe Analytics\Data Workbench
```

<table id="table_56BAC85184A04E7680FBB4B36DE73285"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Directory </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.exe </span> </b> </td> 
   <td colname="col2"> L'eseguibile del client Data Workbench. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> insight.ini </span> </b> </td> 
   <td colname="col2"> Imposta la lingua e il percorso per il <span class="filepath"> Appdata </span> cartella. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.zbin </span> </b> </td> 
   <td colname="col2"> <p>Data Workbench ora supporta un IME (Input Method Editor) come processo di immissione di testo secondario che consente di immettere caratteri internazionali dalla tastiera utilizzando una casella di testo mobile. Data Workbench supporterà l’inglese per impostazione predefinita, ma consente anche di caricare altri file per supportare le lingue internazionali, ad esempio una tastiera cinese virtuale (Pinyin IME). </p> <p>Un nuovo file dizionario <span class="filepath"> (Insight.zbin </span>) è richiesto dall'applicazione client per supportare l'IME. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> unins000.exe </span></b> </td> 
   <td colname="col2"> Eseguibile per disinstallare Workstation ed eliminare i file. </td> 
  </tr> 
 </tbody> 
</table>

## File AppData {#section-afddeedf8d29451f996fa46b2dfe932c}

File di dati (**[!DNL Insight.cfg]**, Profili, Certificati, log di traccia e file utente) vengono salvati per impostazione predefinita in:

```
<filepath>
  C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
</filepath>
```

<table id="table_DBA4DBB54C57409C8EC116C686A08560"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Directory </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Insight.cfg </span> </b> </td> 
   <td colname="col2"> Il file di configurazione Data Workbench. Definisce i parametri all'interno dei quali opera la Data Workbench. Vedi <a href="../../../home/c-install-insight/install-setup/c-conn-isvr.md#concept-9f47b2cd7c12492693a2cf810cfc1d9e"> Configurazione della connessione a Insight Server </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Base </span> </b> </td> 
   <td colname="col2"> <p>Contiene i file di programma per Data Workbench. </p> <p> <p>Nota: Non rimuovere o modificare nessuno di questi file. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Certificati </span> </b> </td> 
   <td colname="col2"> Contiene il file del certificato, <span class="filepath"> trust_ca_cert.pem </span>e il certificato digitale utente denominato per la Data Workbench. Vedi <a href="../../../home/c-install-insight/install-setup/c-dgtl-crtf.md#concept-4c6a900074d4464fb6ec7862f7e54f10"> Download e installazione del certificato digitale </a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Configurazione </span> </b> </td> 
   <td colname="col2"> Contiene i file utilizzati per la configurazione di Workstation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Informazioni geografiche </span></b> </td> 
   <td colname="col2"> File per il rendering grafico di visualizzazioni geografiche. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Traccia </span></b> </td> 
   <td colname="col2"> File di registro generati dalla workstation. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> Profili </span></b> </td> 
   <td colname="col2"> <i>AdobeSC</i>, <i>Analisi predittiva</i> e altri file di configurazione del profilo. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> <span class="filepath"> InsightSetup.exe </span></b> </td> 
   <td colname="col2"> Installazione guidata per installare computer client aggiuntivi nel <b> <span class="filepath"> Software/Insight </span></b> cartella. </td> 
  </tr> 
 </tbody> 
</table>
