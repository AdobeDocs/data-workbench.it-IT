---
description: Il prodotto dashboard richiede una licenza fornita da Adobe ClientCare.
title: Aggiungi chiave di licenza del dashboard
uuid: 51ec87a8-e9cc-4aa1-8d13-a79612a13d17
exl-id: bf532fb0-9287-4c15-aa4c-07f7bd0fdba7
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 12%

---

# Aggiungi chiave di licenza del dashboard{#add-dashboard-license-key}

Il prodotto dashboard richiede una licenza fornita da Adobe ClientCare.

1. Apri **[!UICONTROL SQL Management Studio]** come amministratore.
1. Apri il database creato dal dashboard (ad esempio, thinclientdb).
1. Fai clic con il pulsante destro del mouse sulla tabella **[!UICONTROL Configuration]** e fai clic su **[!UICONTROL Edit Top 200 Rows]**.
1. Trova il campo **[!UICONTROL licenseKey]** e immetti la chiave fornita da Adobe ClientCare nella colonna **[!UICONTROL Value]** .
1. Riavvia il **[!UICONTROL Application Pool]** nel **[!UICONTROL IIS Manager Console]**.
