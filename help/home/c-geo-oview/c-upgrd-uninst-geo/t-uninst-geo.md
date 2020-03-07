---
description: Procedura per disinstallare data workbenchGeography.
solution: Analytics
title: Disinstallazione della geografia del workbench dati
topic: Data workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Disinstallazione della geografia del workbench dati{#uninstalling-data-workbench-geography}

Procedura per disinstallare data workbenchGeography.

>[!NOTE]
>
>Se il profilo con il quale si utilizza il workbench dati [!DNL Geography] è in esecuzione in un cluster di server workbench dati, disinstallare il [!DNL Geography] profilo dal server workbench dati master nel cluster.

1. Utilizzare i passaggi seguenti per aggiornare il [!DNL profile.cfg] file per ciascun profilo con il quale si utilizzava il workbench dati [!DNL Geography].

   1. Aprite il [!DNL Profile Manager].
   1. Fare clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fare clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella [!DNL User] colonna.

   1. Fare clic con il pulsante destro del mouse sul segno di spunta appena creato e scegliere **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene [!DNL profile.cfg] visualizzata la finestra.

   1. Nella [!DNL profile.cfg] finestra, eliminate la voce di [!DNL Geography] profilo dal [!DNL Directories] vettore.

   1. Se hai utilizzato un servizio dati, elimina la voce [!DNL IP Geo-intelligence] o del [!DNL IP Geo-location] profilo dal [!DNL Directories] vettore.

   1. Fare clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fare clic su **[!UICONTROL Save]**.

   1. Fare [!DNL Profile Manager]clic con il pulsante destro del mouse sul segno di spunta [!DNL profile.cfg] nella [!DNL User] colonna, quindi scegliere **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Eliminare la cartella Geografia dalla cartella Profili nella directory di installazione del server workbench dati.
1. Se hai utilizzato un servizio dati, elimina la cartella Geo-Intelligence o Geolocalità IP dalla cartella Profili nella directory di installazione del server workbench dati.
1. Eliminare la cartella Geografia dalla cartella Ricerche nella directory di installazione del server workbench dati.
1. Se hai utilizzato un servizio dati, elimina la cartella Geo-Intelligence o Geolocalità IP dalla cartella Ricerche nella directory di installazione del server workbench dati.
1. Se sono state create nuove immagini di terreno, eliminare il [!DNL Terrain Images.cfg] file dalla cartella Components nella directory di installazione del server workbench dati.
