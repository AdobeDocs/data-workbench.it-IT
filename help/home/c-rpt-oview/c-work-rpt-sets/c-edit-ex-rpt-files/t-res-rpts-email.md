---
description: Passaggi per inviare nuovamente i rapporti per e-mail.
title: Invio di rapporti per e-mail
uuid: 384dfa1f-6a72-4fef-886e-bf2290f5993f
exl-id: eb37fd3e-6e7b-4672-bcf0-fffa9f10997d
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 6%

---

# Invio di rapporti per e-mail{#resending-reports-by-email}

{{eol}}

Passaggi per inviare nuovamente i rapporti per e-mail.

Se la **[!UICONTROL Allow Report Regeneration]** nel [!DNL Report.cfg] file impostato su [!DNL True]quando apporti modifiche a un [!DNL Report.cfg] e salvare di nuovo il file sul server, Report Server rigenera automaticamente i report in quel set. Non invia nuovamente i rapporti via e-mail.

1. Sulla [!DNL Reports] selezionare la sottocartella (scheda o sottodirectory a discesa) per il set di rapporti che si desidera inviare nuovamente.
1. Fai clic su **[!UICONTROL Report.cfg]**. I parametri del [!DNL Report.cfg] per la visualizzazione del set di rapporti.
1. Modificare la **[!UICONTROL Start Date]** Indica l&#39;ora futura in cui dovranno essere inviati i rapporti.
1. Salva il file facendo clic con il pulsante destro del mouse **[!UICONTROL Report.cfg (modified)]** nella parte superiore dei parametri e facendo clic su **[!UICONTROL Save to]***&lt; **[!UICONTROL server location]**>*.
I rapporti in questo set vengono rigenerati e vengono inviati per e-mail ai destinatari specificati.
