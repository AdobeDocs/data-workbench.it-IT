---
description: I set di report devono essere configurati in un modo specifico per produrre report visualizzati correttamente tramite il portale dei report.
solution: Analytics
title: Personalizzare l'interfaccia utente del portale di report
topic: Data workbench
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Personalizzare l&#39;interfaccia utente del portale di report{#customize-the-report-portal-user-interface}

I set di report devono essere configurati in un modo specifico per produrre report visualizzati correttamente tramite il portale dei report.

L&#39;interfaccia utente per [!DNL Report Portal] è progettata per visualizzare una scheda per ogni cartella del set di report che viene visualizzata nella directory di output ed è elencata nel [!DNL profiles.xml] file, così come la [!DNL Admin] scheda incorporata, che deve essere aggiunta al [!DNL TopNavigation.xml] file da visualizzare. Per ulteriori informazioni sulla visualizzazione della [!DNL Admin] scheda incorporata, vedere [Collegamento di una cartella di output a una scheda nell&#39;utente...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Garanzia di compatibilità dei set di rapporti con il portale di rapporti in corso...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Collegamento di una cartella di output a una scheda dell&#39;utente in corso...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Garanzia di compatibilità dei set di rapporti con il portale di rapporti {#section-2b141e5d198a4bbea455699126c24706}

Un set di rapporti definisce un processo pianificato per [!DNL Report]. È costituito da due elementi:

* Una cartella che definisce la raccolta di aree di lavoro da [!DNL Report] generare come rapporti.
* Un file di configurazione ( [!DNL Report.cfg]).

Tra le altre cose, il [!DNL Report.cfg] file indica [!DNL Report] quando generare i rapporti e dove salvare i file di output. I set di report risiedono nella cartella Reports del server workbench dati. Un profilo può visualizzare un numero qualsiasi di set di report.

Per garantire la compatibilità con [!DNL Report Portal], i set di rapporti devono soddisfare i seguenti requisiti:

* La directory di output per i set di report deve contenere un [!DNL profiles.xml] file configurato.
* Ogni set di report deve includere un report di primo livello denominato &quot;*ReportSetName* Summary&quot;, in cui *ReportSetName* corrisponde al nome del set di report. Ad esempio, quanto segue [!DNL Profile Manager] mostra due set di report, &quot;Home&quot; e &quot;Traffic&quot;. Ogni set di rapporti definisce un rapporto di riepilogo ( [!DNL Home Summary.vw] e, rispettivamente, [!DNL Traffic Summary.vw]).

![](assets/rptPort_scrn_RptSets.png)

In [!DNL Report Portal]questo caso, il rapporto di riepilogo viene visualizzato nella scheda del set di rapporti. Il rapporto di riepilogo può contenere qualsiasi area di lavoro, finestra o visualizzazione selezionata.

* Il rapporto di riepilogo deve essere l&#39;unico rapporto nella cartella di livello principale per un set di report. Tutti gli altri rapporti devono essere inseriti in sottocartelle. Se inserite altri rapporti nella cartella di livello principale, non potete visualizzarli attraverso il portale.

## Collegamento di una cartella di output a una scheda nell’interfaccia utente {#section-3f6bc47d37ed448e871f4f685f46acee}

Per specificare le schede che si desidera [!DNL Report Portal] visualizzare, è necessario configurare un [!DNL TopNavigation.xml] file per ciascun profilo. Questo file determina quali set di report vengono visualizzati come schede nell&#39;interfaccia utente per un particolare profilo, nonché l&#39;ordine di tali schede. Il [!DNL TopNavigation.xml] file risiede nella cartella \*PortalName*\PortalFiles\Core\TopNav\*profileName*.

**Per modificare il file TopNavigation.xml**

1. Nel computer in cui è in esecuzione IIS, aprite il [!DNL TopNavigation.xml] file in un editor di testo come Blocco note.
1. Modificate l&#39;elenco di `<TopNav>` elementi in modo che definisca i nomi e l&#39;ordine dei set di report di cui desiderate [!DNL Report Portal] visualizzare l&#39;output, come nell&#39;esempio seguente:

   ```
   <?xml version="1.0" encoding="UTF-8" standalone="no" ?>
   <TOPNAV_ELEMENTS>
   <TOPNAV>
       <NAME>Monthly Web</NAME>
     </TOPNAV>
     <TOPNAV>
       <NAME>Weekly Web</NAME>
     </TOPNAV>
   <TOPNAV> 
         <NAME>Admin</NAME> 
     </TOPNAV>
   </TOPNAV_ELEMENTS>
   ```

   >[!NOTE]
   >
   >La [!DNL Admin] scheda è una scheda incorporata che fornisce funzionalità aggiuntive. Se non lo si inserisce nel [!DNL TopNavigation.xml] file, questa scheda non viene visualizzata e la relativa funzionalità non è disponibile.

1. In \*PortalName*\PortalFiles\Core\TopNav\ folder, create una cartella per il profilo successivo.
1. Copiate il [!DNL TopNavigation.xml] file dalla prima cartella del profilo e incollatelo nella nuova cartella.
1. Modificate il file [!DNL TopNavigation.xml] come necessario, quindi salvatelo.
1. Ripetete i passaggi da 3 a 5 per tutti gli altri profili disponibili nel portale.

