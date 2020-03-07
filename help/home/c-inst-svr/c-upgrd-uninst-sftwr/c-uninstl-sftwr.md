---
description: Istruzioni per disinstallare Insight Server, Transform o Ripetitore.
solution: Insight
title: Disinstallazione del software
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Disinstallazione del software{#uninstalling-your-software}

Istruzioni per disinstallare Insight Server, Transform o Ripetitore.

## Disinstallazione di Adobe Insight Server {#section-7d7befe672854df79bb6c28ec02f6670}

1. Annullamento della registrazione del servizio [!DNL Insight Server] Windows.

   1. Aprite un prompt dei comandi e andate alla sottodirectory bin nella cartella in cui avete installato [!DNL Insight Server].

      Esempio: [!DNL C:\Adobe\Server\bin]

   1. Al prompt dei comandi, eseguite il comando seguente per arrestarlo e annullarne la registrazione come servizio in Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Eliminate la directory di [!DNL Insight Server] installazione.

## Disinstallazione di Transform {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Per aggiornare il [!DNL profile.cfg] file per ciascun profilo con cui si stava utilizzando, procedere come segue [!DNL Transform].

   1. Aprite il [!DNL Profile Manager].
   1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Viene [!DNL profile.cfg] visualizzata la finestra.

   1. Nella [!DNL profile.cfg] finestra, eliminate la voce di [!DNL Transform] profilo dal vettore Directory.

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare [!DNL Profile Manager]clic con il pulsante destro del mouse sul segno di spunta [!DNL profile.cfg] nella [!DNL User] colonna, quindi scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Eliminate la [!DNL Transform] cartella dalla [!DNL Profiles] cartella nella directory di [!DNL Insight Server] installazione.

## Disinstallazione Ripetitore {#section-2f94141d956749d88f549dbea26e5272}

1. Annullamento della registrazione del servizio [!DNL Repeater] Windows.

   1. Aprite un prompt dei comandi e andate alla sottodirectory bin nella cartella in cui avete installato [!DNL Repeater].

      Esempio: [!DNL D:\Adobe\Repeater\bin]

   1. Al prompt dei comandi, eseguite il comando seguente per arrestarlo e annullarne la registrazione come servizio in Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Eliminate la directory di [!DNL Repeater] installazione.

