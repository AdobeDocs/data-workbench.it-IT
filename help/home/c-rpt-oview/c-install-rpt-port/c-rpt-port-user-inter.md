---
description: I set di rapporti devono essere configurati in un modo specifico per produrre rapporti visualizzati correttamente tramite Report Portal (Portale dei rapporti).
title: Personalizzare l’interfaccia utente del Report Portal (Portale dei rapporti)
uuid: d1ea88e2-7b9e-4b1e-a826-dbe7c2e75976
exl-id: 1f7c807d-d896-448f-b9dd-9fe6a68ef27e
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 2%

---

# Personalizzare l’interfaccia utente del Report Portal (Portale dei rapporti){#customize-the-report-portal-user-interface}

{{eol}}

I set di rapporti devono essere configurati in un modo specifico per produrre rapporti visualizzati correttamente tramite Report Portal (Portale dei rapporti).

Interfaccia utente per [!DNL Report Portal] è progettato per visualizzare una scheda per ogni cartella del set di rapporti che viene visualizzata nella directory di output ed è elencata nella [!DNL profiles.xml] e il [!DNL Admin] , che deve essere aggiunta al [!DNL TopNavigation.xml] file da visualizzare. Per ulteriori informazioni sulla visualizzazione del [!DNL Admin] scheda , vedi [Collegamento di una cartella di output a una scheda nell&#39;utente in corso...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee).

![](assets/report_portal_home.png)

* [Verifica della compatibilità dei set di rapporti con il Report Portal (Portale dei rapporti) in corso...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-2b141e5d198a4bbea455699126c24706)
* [Collegamento di una cartella di output a una scheda nell&#39;utente in corso...](../../../home/c-rpt-oview/c-install-rpt-port/c-rpt-port-user-inter.md#section-3f6bc47d37ed448e871f4f685f46acee)

## Verifica della compatibilità dei set di rapporti con Report Portal (Portale dei rapporti) {#section-2b141e5d198a4bbea455699126c24706}

Un set di rapporti definisce un lavoro pianificato per [!DNL Report]. Si compone di due elementi:

* Cartella che definisce la raccolta di aree di lavoro desiderate [!DNL Report] da generare come rapporti.
* Un file di configurazione ( [!DNL Report.cfg]).

Tra le altre cose, il [!DNL Report.cfg] informazioni sui file [!DNL Report] quando generare i rapporti e dove salvare i file di output. I set di rapporti si trovano nella cartella Report sul server di Data Workbench. Un profilo può visualizzare un qualsiasi numero di set di rapporti.

Per garantire la compatibilità con [!DNL Report Portal], i set di rapporti devono soddisfare i seguenti requisiti:

* La directory di output per i set di rapporti deve contenere un [!DNL profiles.xml] file.
* Ogni set di rapporti deve includere un rapporto di primo livello denominato &quot;*NomeSetReport* Riepilogo&quot;, dove *NomeSetReport* corrisponde al nome del set di rapporti. Ad esempio: [!DNL Profile Manager] mostra due set di rapporti: &quot;Home&quot; e &quot;Traffico&quot;. Ogni set di rapporti definisce un rapporto di riepilogo ( [!DNL Home Summary.vw] e [!DNL Traffic Summary.vw], rispettivamente).

![](assets/rptPort_scrn_RptSets.png)

In [!DNL Report Portal], il rapporto di riepilogo viene visualizzato nella scheda del set di rapporti. Il rapporto di riepilogo può contenere qualsiasi area di lavoro, finestra o visualizzazione scelta.

* Il rapporto di riepilogo deve essere l’unico rapporto presente nella cartella di livello superiore per un set di rapporti. Tutti gli altri rapporti devono essere inseriti in sottocartelle. Se inserisci altri rapporti nella cartella principale, non puoi visualizzarli attraverso il portale.

## Collegamento di una cartella di output a una scheda nell’interfaccia utente {#section-3f6bc47d37ed448e871f4f685f46acee}

Specifica delle schede desiderate [!DNL Report Portal] per visualizzare, devi configurare un [!DNL TopNavigation.xml] file per ogni profilo. Questo file determina quali set di rapporti vengono visualizzati come schede nell’interfaccia utente per un particolare profilo, nonché l’ordine di tali schede. La [!DNL TopNavigation.xml] Il file si trova nella cartella \*PortalName*\PortalFiles\Core\TopNav\*profileName*.

**Per modificare il file TopNavigation.xml**

1. Sul computer in cui è in esecuzione IIS, apri la [!DNL TopNavigation.xml] in un editor di testo come Blocco note.
1. Modifica l’elenco di `<TopNav>` in modo da definire i nomi e l&#39;ordine dei set di rapporti di cui si desidera ottenere l&#39;output [!DNL Report Portal] per visualizzare, come nell’esempio seguente:

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
   >La [!DNL Admin] è una scheda incorporata che fornisce funzionalità aggiuntive. Se non lo includi nel [!DNL TopNavigation.xml] file, questa scheda non viene visualizzata e la relativa funzionalità non è disponibile.

1. In \*PortalName*\PortalFiles\Core\TopNav\ folder, crea una cartella per il profilo successivo.
1. Copia il [!DNL TopNavigation.xml] dalla prima cartella del profilo e incollala nella nuova cartella.
1. Modifica le [!DNL TopNavigation.xml] se necessario, salva il file.
1. Ripeti i passaggi 3-5 per tutti gli altri profili disponibili nel portale.
