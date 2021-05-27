---
description: Passaggi per inviare nuovamente i rapporti per e-mail.
title: Invio di rapporti per e-mail
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# Invio di rapporti per e-mail{#resending-reports-by-email}

Passaggi per inviare nuovamente i rapporti per e-mail.

Se il parametro **[!UICONTROL Allow Report Regeneration]** nel file [!DNL Report.cfg] è impostato su [!DNL True], quando apporti modifiche a un file [!DNL Report.cfg] e salvi di nuovo il file sul server, Report Server rigenera automaticamente i rapporti in quel set. Non invia nuovamente i rapporti via e-mail.

1. Nella scheda [!DNL Reports] , seleziona la sottocartella (scheda o sottodirectory a discesa) per il set di rapporti che desideri inviare nuovamente.
1. Fai clic su **[!UICONTROL Report.cfg]**. Vengono visualizzati i parametri del [!DNL Report.cfg] per questo set di rapporti.
1. Modifica il parametro **[!UICONTROL Start Date]** in base all&#39;ora futura in cui dovranno essere inviati i rapporti.
1. Salva il file facendo clic con il pulsante destro del mouse su **[!UICONTROL Report.cfg (modified)]** nella parte superiore dei parametri e facendo clic su **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
I rapporti in questo set vengono rigenerati e vengono inviati per e-mail ai destinatari specificati.
