---
description: Informazioni sullo stato del server di rapporto e del set di rapporti.
title: Verifica dello stato del rapporto
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
exl-id: a986f148-f019-457c-ade8-a4eaecbb1de7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 2%

---

# Verifica dello stato del rapporto{#reviewing-report-status}

{{eol}}

Informazioni sullo stato del server di rapporto e del set di rapporti.

* [Stato del server di rapporto](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Stato del set di rapporti](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Stato del server di rapporto {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Frequenza consigliata:** Solo quando necessario

[!DNL Report] invia al server di Data Workbench informazioni sullo stato del [!DNL Report] Server. Queste informazioni possono essere visualizzate nella sezione [!DNL Report Server Status] nel nodo [!DNL Detailed Status] interfaccia.

**Per aprire [!DNL Detailed Status] visualizzazione**

1. All’interno di Data Workbench, fai clic con il pulsante destro del mouse in un’area di lavoro e fai clic su **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. In [!DNL Servers] , fai clic con il pulsante destro del mouse sull’icona del server di Data Workbench che [!DNL Report] il computer si connette a e fai clic su **[!UICONTROL Detailed Status.]**

1. Fai clic su **[!UICONTROL Report Server Status]**.

Se più di uno [!DNL Report] è connesso al server di Data Workbench, viene visualizzata una voce per ogni [!DNL Report Server] nel vettore Stato. È possibile ignorare l’intervallo di due minuti specificando un valore nel parametro Intervallo di stato (secondi) nel [!DNL Reporting] nodo [!DNL ReportServer.cfg] file.

Per informazioni sulla [!DNL ReportServer.cfg] file, vedi [Configurare il set di rapporti](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0). Per informazioni sulla configurazione [!DNL Report], vedi [Installazione del rapporto](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Per ulteriori informazioni [!DNL Detailed Status], vedere il capitolo relativo alle interfacce amministrative *Guida utente di Data Workbench*.

## Stato del set di rapporti {#section-8569b94266b74a1f85d2a85106a2aaef}

**Frequenza consigliata:** Solo quando necessario

[!DNL Report] trasmette le informazioni sullo stato di ciascun set di rapporti al server Data Workbench. Le informazioni di base, ad esempio quando un set di rapporti viene generato e dove viene distribuito, vengono visualizzate in workbench dati sopra il set di rapporti in testo verde. Durante l&#39;esecuzione dei rapporti, [!DNL Report] Il server invia un messaggio ogni due minuti indicando la percentuale di completamento delle query correnti. È possibile ignorare questo intervallo di due minuti specificando un valore nel parametro Intervallo messaggi di completamento (secondi) nel [!DNL Reporting] nodo [!DNL ReportServer.cfg] file.

![](assets/report_status.png)

>[!NOTE]
>
>Se si è verificato un errore durante l&#39;esecuzione di un report, l&#39;errore è indicato in rosso sotto la miniatura del report. Per visualizzare il messaggio di errore completo, fai clic con il pulsante destro del mouse sull’area di lavoro.
