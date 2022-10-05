---
description: Il prodotto dashboard richiede una licenza fornita da Adobe ClientCare.
title: Aggiungi chiave di licenza del dashboard
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# Aggiungi chiave di licenza del dashboard{#add-dashboard-license-key}

{{eol}}

Il prodotto dashboard richiede una licenza fornita da Adobe ClientCare.

1. Apri **[!UICONTROL SQL Management Studio]** come amministratore.
1. Apri il database creato dal dashboard (ad esempio, thinclientdb).
1. Fai clic con il pulsante destro del mouse sul pulsante **[!UICONTROL Configuration]** tabella e fai clic su **[!UICONTROL Edit Top 200 Rows]**.
1. Trova il **[!UICONTROL licenseKey]** e immetti la chiave fornita da Adobe ClientCare nel **[!UICONTROL Value]** colonna.
1. Riavvia **[!UICONTROL Application Pool]** in **[!UICONTROL IIS Manager Console]**.
