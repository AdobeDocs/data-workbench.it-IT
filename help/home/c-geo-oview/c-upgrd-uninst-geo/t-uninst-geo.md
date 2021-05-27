---
description: Procedura per disinstallare data workbenchGeography.
title: Disinstallazione della geografia di Data Workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 3%

---

# Disinstallazione della geografia di Data Workbench{#uninstalling-data-workbench-geography}

Procedura per disinstallare data workbenchGeography.

>[!NOTE]
>
>Se il profilo con cui utilizzi Data Workbench [!DNL Geography] è in esecuzione su un cluster di server di Data Workbench, disinstalla il profilo [!DNL Geography] dal server principale di Data Workbench nel cluster.

1. Utilizza i passaggi seguenti per aggiornare il file [!DNL profile.cfg] per ciascun profilo con cui stavi utilizzando Data Workbench [!DNL Geography].

   1. Apri [!DNL Profile Manager].
   1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nella colonna [!DNL User].

   1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. Viene visualizzata la finestra [!DNL profile.cfg].

   1. Nella finestra [!DNL profile.cfg] , elimina la voce di profilo [!DNL Geography] dal vettore [!DNL Directories].

   1. Se hai utilizzato un servizio dati, elimina la voce di profilo [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] dal vettore [!DNL Directories].

   1. Fai clic con il pulsante destro del mouse su **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta per [!DNL profile.cfg] nella colonna [!DNL User], quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Elimina la cartella Geografia dalla cartella Profili nella directory di installazione del server di Data Workbench.
1. Se utilizzi un servizio dati, elimina la cartella Geo-intelligence IP o Geo-location IP dalla cartella Profiles nella directory di installazione del server di Data Workbench.
1. Elimina la cartella Geografia dalla cartella Ricerche nella directory di installazione del server di Data Workbench.
1. Se utilizzi un servizio dati, elimina la cartella Geo-intelligence IP o Geo-location IP dalla cartella Ricerche nella directory di installazione del server di Data Workbench.
1. Se hai creato nuove immagini del terreno, elimina il file [!DNL Terrain Images.cfg] dalla cartella Componenti nella directory di installazione del server di Data Workbench.
