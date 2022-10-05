---
description: Procedura per disinstallare data workbenchGeography.
title: Disinstallazione della geografia di Data Workbench
uuid: 038b2dfb-4db2-42c6-85c3-bc5d776e7736
exl-id: e3898423-3b28-4786-834a-1d1ff9deb7c6
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 3%

---

# Disinstallazione della geografia di Data Workbench{#uninstalling-data-workbench-geography}

{{eol}}

Procedura per disinstallare data workbenchGeography.

>[!NOTE]
>
>Se si utilizza il profilo con cui si utilizza Data Workbench [!DNL Geography] è in esecuzione su un cluster di server di Data Workbench, disinstalla [!DNL Geography] profilo dal server di Data Workbench principale nel cluster.

1. Utilizza i seguenti passaggi per aggiornare il [!DNL profile.cfg] file per ogni profilo con cui stavi utilizzando Data Workbench [!DNL Geography].

   1. Apri [!DNL Profile Manager].
   1. Fai clic con il pulsante destro del mouse sul segno di spunta accanto a [!DNL profile.cfg] e fai clic su **[!UICONTROL Make Local]**. Un segno di spunta per questo file viene visualizzato nel [!DNL User] colonna.

   1. Fai clic con il pulsante destro del mouse sul segno di spunta appena creato e fai clic su **[!UICONTROL Open]** > **[!UICONTROL from the workbench]**. La [!DNL profile.cfg] viene visualizzata la finestra .

   1. In [!DNL profile.cfg] finestra, eliminare [!DNL Geography] voce di profilo da [!DNL Directories] vettore.

   1. Se utilizzi un servizio dati, elimina la [!DNL IP Geo-intelligence] o [!DNL IP Geo-location] voce di profilo da [!DNL Directories] vettore.

   1. Fai clic con il pulsante destro del mouse **[!UICONTROL (modified)]** nella parte superiore della finestra e fai clic su **[!UICONTROL Save]**.

   1. In [!DNL Profile Manager], fai clic con il pulsante destro del mouse sul segno di spunta [!DNL profile.cfg] in [!DNL User] , quindi fai clic su **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.

1. Elimina la cartella Geografia dalla cartella Profili nella directory di installazione del server di Data Workbench.
1. Se utilizzi un servizio dati, elimina la cartella Geo-intelligence IP o Geo-location IP dalla cartella Profiles nella directory di installazione del server di Data Workbench.
1. Elimina la cartella Geografia dalla cartella Ricerche nella directory di installazione del server di Data Workbench.
1. Se utilizzi un servizio dati, elimina la cartella Geo-intelligence IP o Geo-location IP dalla cartella Ricerche nella directory di installazione del server di Data Workbench.
1. Se hai creato nuove immagini del terreno, elimina [!DNL Terrain Images.cfg] dalla cartella Componenti nella directory di installazione del server di Data Workbench.
