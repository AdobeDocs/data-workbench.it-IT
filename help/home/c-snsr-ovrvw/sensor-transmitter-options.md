---
description: Informazioni sui comandi di avvio del trasmettitore sensore per UNIX e per Windows.
title: Opzioni della riga di comando del trasmettitore sensore
uuid: 8d077d76-a709-494e-a176-07ca3e761662
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Opzioni della riga di comando del trasmettitore sensore{#sensor-transmitter-command-line-options}

Informazioni sui comandi di avvio del trasmettitore sensore per UNIX e per Windows.

## Start-up Command for UNIX {#section-e8e7a6e62971499ba5f633d896590949}

Per avviare il trasmettitore Sensor su uno stelo UNIX, utilizzare il seguente comando:

```
txlogd -f configFileName
```

dove configFileName è il nome completo del file di configurazione del trasmettitore (txlogd.conf).

Per impostazione predefinita, il trasmettitore viene eseguito come processo in background (un daemon) e scrive messaggi operativi su syslog.

Di seguito è riportato un elenco completo degli switch della riga di comando per lo xlogd:

| Switch | Descrizione |
|---|---|
| -f | Specifica il nome completo del file di configurazione (txlogd.conf). Se non si specifica questo interruttore, il trasmettitore cerca txlogd.conf nella directory corrente. |
| -n | Avvia il trasmettitore in modalità interattiva (non come processo in background). |
| -i | Avvia il trasmettitore in modalità interattiva e indirizza l&#39;output di debug a stdout. |
| -d | Avvia il trasmettitore come processo in background e indirizza l&#39;output di debug a txlogd-debug.log nella directory corrente. |
| -c | Avvia il trasmettitore e crea il file della coda del disco, se non esiste. Se la coda del disco esiste già, questo parametro viene ignorato. |
| -x | Avvia il trasmettitore e lo fa uscire dopo la trasmissione dell&#39;ultimo pacchetto nella coda del disco. È possibile utilizzare questa opzione per svuotare la coda in preparazione di un&#39;operazione amministrativa, ad esempio la creazione di un nuovo file di coda. |

## Comando di avvio per Windows {#section-aaafbb68559a45c7a40abe6a4c80ccc0}

Per avviare Sensor e registrarlo come servizio su un sistema Windows, si utilizza il seguente comando:

```
txlog /regserver
```

