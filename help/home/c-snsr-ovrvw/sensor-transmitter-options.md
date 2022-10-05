---
description: Informazioni sui comandi di avvio del trasmettitore sensore per UNIX e per Windows.
title: Opzioni della riga di comando del Sensor Transmitter (Trasmettitore del sensore)
uuid: 8d077d76-a709-494e-a176-07ca3e761662
exl-id: f4b27859-8fab-42cd-bad0-b32f87764668
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 5%

---

# Opzioni della riga di comando del Sensor Transmitter (Trasmettitore del sensore){#sensor-transmitter-command-line-options}

{{eol}}

Informazioni sui comandi di avvio del trasmettitore sensore per UNIX e per Windows.

## Comando di avvio per UNIX {#section-e8e7a6e62971499ba5f633d896590949}

Per avviare il trasmettitore Sensor su uno stelo UNIX, utilizzare il seguente comando:

```
txlogd -f configFileName
```

dove configFileName è il nome completo del file di configurazione del trasmettitore (txlogd.conf).

Per impostazione predefinita, il trasmettitore viene eseguito come processo in background (un daemon) e scrive i messaggi operativi nel registro di sistema.

Di seguito è riportato un elenco completo degli switch della riga di comando per txlogd:

| Interruttore | Descrizione |
|---|---|
| -f | Specifica il nome completo del file di configurazione (txlogd.conf). Se non si specifica questo interruttore, il trasmettitore cerca txlogd.conf nella directory corrente. |
| -n | Avvia il trasmettitore in modalità interattiva (non come processo in background). |
| -i | Avvia il trasmettitore in modalità interattiva e indirizza l&#39;output di debug a stdout. |
| -d | Avvia il trasmettitore come processo in background e indirizza l&#39;output di debug a txlogd-debug.log nella directory corrente. |
| -c | Avvia il trasmettitore e crea il file della coda del disco, se non esiste. Se la coda del disco esiste già, questo parametro viene ignorato. |
| -x | Avvia il trasmettitore e lo fa uscire dopo la trasmissione dell&#39;ultimo pacchetto nella coda del disco. È possibile utilizzare questa opzione per svuotare la coda in preparazione di un’operazione amministrativa, ad esempio la creazione di un nuovo file di coda. |

## Comando di avvio per Windows {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

Per avviare Sensor e registrarlo come servizio su un sistema Windows, utilizzare il seguente comando:

```
txlog /regserver
```
