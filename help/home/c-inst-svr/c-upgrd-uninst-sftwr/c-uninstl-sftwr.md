---
description: Istruzioni per disinstallare Insight Server, Transform o Repeater (Trasforma o Ripetitore).
title: Disinstallazione del software
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 3%

---

# Disinstallazione del software{#uninstalling-your-software}

{{eol}}

Istruzioni per disinstallare Insight Server, Transform o Repeater (Trasforma o Ripetitore).

## Disinstallazione dell’Adobe di Insight Server {#section-7d7befe672854df79bb6c28ec02f6670}

1. Annulla la registrazione [!DNL Insight Server] Servizio Windows.

   1. Apri un prompt dei comandi e passa alla sottodirectory bin nella cartella in cui hai installato [!DNL Insight Server].

      Esempio: [!DNL C:\Adobe\Server\bin]

   1. Al prompt dei comandi, esegui il seguente comando per arrestarlo e annullarne la registrazione come servizio in Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Elimina [!DNL Insight Server] directory di installazione.

## Disinstallazione di Transform {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Utilizza i seguenti passaggi per aggiornare il [!DNL profile.cfg] file per ogni profilo con cui stavi utilizzando [!DNL Transform].

   1. Apri [!DNL Profile Manager].
   1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nel [!DNL User] colonna.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La [!DNL profile.cfg] viene visualizzata la finestra .

   1. In [!DNL profile.cfg] finestra, eliminare [!DNL Transform] voce di profilo dal vettore Directory.

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta [!DNL profile.cfg] in [!DNL User] , quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Elimina [!DNL Transform] dalla cartella [!DNL Profiles] nella cartella [!DNL Insight Server] directory di installazione.

## Disinstallazione del Repeater (Ripetitore) {#section-2f94141d956749d88f549dbea26e5272}

1. Annulla la registrazione [!DNL Repeater] Servizio Windows.

   1. Apri un prompt dei comandi e passa alla sottodirectory bin nella cartella in cui hai installato [!DNL Repeater].

      Esempio: [!DNL D:\Adobe\Repeater\bin]

   1. Al prompt dei comandi, esegui il seguente comando per arrestarlo e annullarne la registrazione come servizio in Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Elimina [!DNL Repeater] directory di installazione.
