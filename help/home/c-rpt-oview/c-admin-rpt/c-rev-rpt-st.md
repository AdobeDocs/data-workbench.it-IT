---
description: Informazioni sullo stato del server di report e del set di report.
solution: Analytics
title: Verifica dello stato del rapporto
topic: Data workbench
uuid: 0f78a9fd-83d5-4e05-b7d1-d841033a5616
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verifica dello stato del rapporto{#reviewing-report-status}

Informazioni sullo stato del server di report e del set di report.

* [Stato del server di report](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-1a84f22439ee4a4ba2b3434e51e82ce0)
* [Stato set di rapporti](../../../home/c-rpt-oview/c-admin-rpt/c-rev-rpt-st.md#section-8569b94266b74a1f85d2a85106a2aaef)

## Stato del server di report {#section-1a84f22439ee4a4ba2b3434e51e82ce0}

**Frequenza consigliata:** Solo se necessario

[!DNL Report] invia al server del workbench dati informazioni sullo stato del [!DNL Report] server ogni due minuti. Queste informazioni sono visibili sotto il [!DNL Report Server Status] nodo nell&#39; [!DNL Detailed Status] interfaccia.

**Per aprire la[!DNL Detailed Status]visualizzazione**

1. Nel workbench dati, fare clic con il pulsante destro del mouse in un&#39;area di lavoro e scegliere **[!UICONTROL Admin]** > **[!UICONTROL Servers]**.

1. Nell&#39; [!DNL Servers] interfaccia fare clic con il pulsante destro del mouse sull&#39;icona del server workbench dati a cui il [!DNL Report] computer si collega e fare clic su **[!UICONTROL Detailed Status.]**

1. Fai clic su **[!UICONTROL Report Server Status]** (Fine).

Se al server workbench dati [!DNL Report] sono collegati più di una voce, ciascuna di esse viene visualizzata [!DNL Report Server] nel vettore Stato. L’intervallo di due minuti può essere ignorato specificando un valore nel parametro Intervallo di stato (secondi) nel [!DNL Reporting] nodo del [!DNL ReportServer.cfg] file.

Per informazioni sul [!DNL ReportServer.cfg] file, consultate [Configurare il set](../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/t-config-rpt-set.md#task-cfb2fd0c28bc48c2acdd582fe0d670d0)di report. Per informazioni sulla configurazione [!DNL Report], consultate [Installazione dei rapporti](../../../home/c-rpt-oview/c-inst-rpt/c-inst-rpt.md#concept-3b8696a5b7f04ebfaafec7ff55890d91).

Per ulteriori informazioni su [!DNL Detailed Status]questo argomento, vedere il capitolo relativo alle interfacce amministrative della Guida *utente di Workbench* dati.

## Stato set di rapporti {#section-8569b94266b74a1f85d2a85106a2aaef}

**Frequenza consigliata:** Solo se necessario

[!DNL Report] trasmette al server Workbench dati le informazioni sullo stato di ciascun set di rapporti. Le informazioni di base, ad esempio quando un set di report viene generato e dove viene distribuito, vengono visualizzate nel workbench dati sopra il set di report in testo verde. Durante l&#39;esecuzione dei report, [!DNL Report] Server invia un messaggio ogni due minuti che indica la percentuale di completamento delle query correnti. Questo intervallo di due minuti può essere ignorato specificando un valore nel parametro Intervallo messaggi di completamento (secondi) nel [!DNL Reporting] nodo del [!DNL ReportServer.cfg] file.

![](assets/report_status.png)

>[!NOTE]
>
>Se si è verificato un errore durante l&#39;esecuzione di un rapporto, l&#39;errore è indicato in rosso sotto la miniatura del rapporto. È possibile fare clic con il pulsante destro del mouse sull&#39;area di lavoro per visualizzare il messaggio di errore completo.

