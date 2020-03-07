---
description: Passaggi per inviare nuovamente i rapporti per e-mail.
solution: Analytics
title: Invio di report per e-mail
topic: Data workbench
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Invio di report per e-mail{#resending-reports-by-email}

Passaggi per inviare nuovamente i rapporti per e-mail.

Se il **[!UICONTROL Allow Report Regeneration]** parametro nel [!DNL Report.cfg] file è impostato su [!DNL True], quando apportate modifiche a un [!DNL Report.cfg] file e lo salvate nuovamente nel server, il server di report genera automaticamente di nuovo i rapporti in quel set. Non invia nuovamente i rapporti via e-mail.

1. Nella [!DNL Reports] scheda, selezionate la sottocartella (scheda o sottodirectory a discesa) per il set di rapporti che desiderate inviare nuovamente.
1. Fai clic su **[!UICONTROL Report.cfg]** (Fine). Vengono visualizzati i parametri del set di report [!DNL Report.cfg] per il set.
1. Modificate il **[!UICONTROL Start Date]** parametro in base all&#39;ora futura in cui desiderate inviare i rapporti.
1. Salvate il file facendo clic con il pulsante destro del mouse **[!UICONTROL Report.cfg (modified)]** nella parte superiore dei parametri e facendo clic su **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
I report in questo set si rigenerano e vengono inviati per e-mail ai destinatari specificati.
