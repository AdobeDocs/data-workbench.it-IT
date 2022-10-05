---
description: Utilizza il profilo di cronologia di Data Workbench per vedere in che modo la configurazione, l’hardware e altre modifiche influiscono sulle prestazioni, sulla stabilità e sulla capacità del server nel tempo.
title: Area di lavoro di cronologia di Data Workbench
uuid: 61c45cae-f255-4d20-bb6b-f318c8dd8214
exl-id: e6d7e924-641e-468c-a828-16ebe1c8724f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 2%

---

# Area di lavoro di cronologia di Data Workbench{#data-workbench-historic-workspace}

{{eol}}

Utilizza il profilo di cronologia di Data Workbench per vedere in che modo la configurazione, l’hardware e altre modifiche influiscono sulle prestazioni, sulla stabilità e sulla capacità del server nel tempo.

Il profilo Storico include un profilo basato su [Prestazioni del profilo](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-184a86f9de054970bf68515bb9dea85d) set di dati e basati su server [Prestazioni server](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5dad5870384b40e094d50173fcd90a09) set di dati **[!UICONTROL Performance]** scheda . Si tratta dei set di dati più comunemente utilizzati visualizzati per una prospettiva passata delle prestazioni del server di Data Workbench. Inoltre, puoi visualizzare il [Componenti](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) e [Modalità di elaborazione](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) selezionando la **[!UICONTROL Up Time]** scheda .

![](assets/Historic_Performance.png)

Inoltre, puoi visualizzare il [Componenti](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) e [Modalità di elaborazione](../../../home/monitoring-installation/monitoring-profiles/monitoring-historical-using.md#section-5be7223abb384784bafe7b37c764ea66) selezionando la **[!UICONTROL Up Time]** scheda .

Per ulteriori informazioni di riferimento sulle dimensioni utilizzate nel profilo di cronologia di Data Workbench, consulta [Dimension nel profilo storico di Insight.](../../../home/monitoring-installation/monitoring-appendix/monitoring-historical.md#concept-a42837c9c9274f83ad5bc5a6720f02b0)

## Area di lavoro Prestazioni profilo {#section-184a86f9de054970bf68515bb9dea85d}

Questo set di dati include le metriche rilevanti seguenti per il monitoraggio di Data Workbench.

* MegaBytes di input rapido al minuto: metriche che visualizzano dati pesanti durante l&#39;elaborazione del registro iniziale.
* MegaBytes di unione rapida al minuto: metriche che mostrano la trasformazione.

![](assets/Historic_Profile_Performance.png)

>[!NOTE]
>
>Per eseguire una valutazione reale delle prestazioni del tuo profilo, osserva il tasso anziché il tempo di calendario trascorso. La velocità viene misurata come valori modificati tra il polling ogni dieci minuti.

## Area di lavoro delle prestazioni del server {#section-5dad5870384b40e094d50173fcd90a09}

Questo set di dati monitora le metriche del server oltre l’ambito dei profili inclusi e include le seguenti metriche pertinenti del server per il monitoraggio di Data Workbench.

* Minuti di sweep stimati — Tempo stimato di risoluzione delle query.
* Millisecondi di latenza del sondaggio — Indicatore di quanto è occupato il software misurando quanto tempo ci vuole per ottenere attraverso un ciclo completo di manutenzione di ogni componente.

![](assets/Historic_Server_Performance.png)

## Area di lavoro dei componenti {#section-5be7223abb384784bafe7b37c764ea66}

Questo set di dati si trova nella scheda Up Time (Tempo di attivazione).

![](assets/Up_Time.png)

Il set di dati Componenti include due aspetti relativi allo stato dei componenti:

* Metrica delle comunicazioni: il processo del server di Data Workbench ha risposto?
* Metrica Tutti i componenti : nella pagina Stato dettagliato è riportato un elenco dei componenti che l’host sta utilizzando nei processi server di Data Workbench. Se un componente si trova in uno stato di errore, viene elencato nella tabella Componenti in Errore.

![](assets/Up_Time_components.png)

## Area di lavoro in modalità di elaborazione {#section-3e1dedb9474e4b4ba513240943e76817}

Questa area di lavoro si trova nella scheda Up Time (Tempo di attivazione). Questa area di lavoro consente di osservare quanto tempo viene impiegato nelle modalità di input rapido, di unione rapida e in tempo reale.

![](assets/Up_Time_Processing_mode.png)

Questo set di dati fornisce importanti caratteristiche di caricamento del server, ad esempio l’identificazione del carico di dati per

* Giorno della settimana (ad esempio un tasso di ingresso rapido il martedì e il mercoledì),
* Ora del giorno (quale percentuale del giorno è in modalità Fast Input?)
