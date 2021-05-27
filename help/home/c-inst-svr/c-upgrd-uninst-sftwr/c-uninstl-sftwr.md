---
description: Istruzioni per disinstallare Insight Server, Transform o Repeater (Trasforma o Ripetitore).
title: Disinstallazione del software
uuid: 79cf0db6-0f99-40fa-a7b0-38dd8d7246bd
exl-id: 3ba5e5e3-c1a2-4ecb-9f88-a3fe923837e7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 3%

---

# Disinstallazione del software{#uninstalling-your-software}

Istruzioni per disinstallare Insight Server, Transform o Repeater (Trasforma o Ripetitore).

## Disinstallazione dell&#39;Adobe di Insight Server {#section-7d7befe672854df79bb6c28ec02f6670}

1. Annullare la registrazione del servizio [!DNL Insight Server] Windows.

   1. Apri un prompt dei comandi e passa alla sottodirectory bin nella cartella in cui hai installato [!DNL Insight Server].

      Esempio: [!DNL C:\Adobe\Server\bin]

   1. Al prompt dei comandi, eseguire il comando seguente per arrestarlo e annullarne la registrazione come servizio in Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Elimina la directory di installazione [!DNL Insight Server].

## Disinstallazione di Transform {#section-5e6a604dadb5477ba4dc9f93c9be0897}

1. Utilizza i passaggi seguenti per aggiornare il file [!DNL profile.cfg] per ogni profilo con cui stavi utilizzando [!DNL Transform].

   1. Apri [!DNL Profile Manager].
   1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].

   1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Viene visualizzata la finestra [!DNL profile.cfg].

   1. Nella finestra [!DNL profile.cfg], elimina la voce di profilo [!DNL Transform] dal vettore Directory.

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL profile.cfg] nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Elimina la cartella [!DNL Transform] dalla cartella [!DNL Profiles] nella directory di installazione [!DNL Insight Server].

## Disinstallazione di Repeater {#section-2f94141d956749d88f549dbea26e5272}

1. Annullare la registrazione del servizio [!DNL Repeater] Windows.

   1. Apri un prompt dei comandi e passa alla sottodirectory bin nella cartella in cui hai installato [!DNL Repeater].

      Esempio:  [!DNL D:\Adobe\Repeater\bin]

   1. Al prompt dei comandi, eseguire il comando seguente per arrestarlo e annullarne la registrazione come servizio in Microsoft Windows:

      ```
      InsightServer64.exe /unregserver
      ```

1. Elimina la directory di installazione [!DNL Repeater].
