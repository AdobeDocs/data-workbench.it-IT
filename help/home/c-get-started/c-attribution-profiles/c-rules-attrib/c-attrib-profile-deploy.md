---
description: Il profilo di attribuzione è un profilo ereditato e pronto per essere rilasciato. In combinazione con il profilo Adobe SC e il feed di dati Analytics (SC/Insight), il profilo può essere implementato per esporre rapidamente nuovi modelli di attribuzione tra i canali digitali.
title: Distribuzione del profilo di attribuzione
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
exl-id: 287e1710-7e74-4904-b258-7b811ad484b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 3%

---

# Distribuzione del profilo di attribuzione{#deploying-the-attribution-profile}

{{eol}}

Il profilo di attribuzione è un profilo ereditato e pronto per essere rilasciato. In combinazione con il profilo Adobe SC e il feed di dati Analytics (SC/Insight), il profilo può essere implementato per esporre rapidamente nuovi modelli di attribuzione tra i canali digitali.

Dopo aver salvato il profilo di attribuzione sul server principale, sono necessari due passaggi aggiuntivi per integrarlo nel profilo corrente all’interno del [!DNL Profile] directory: (1) Imposta il file Profile.cfg e (2) Dichiara i campi obbligatori.

## Configurazione del file Profile.cfg {#section-7531cb865d994207baba692a6fc842d7}

Come tutti i profili, il profilo di attribuzione deve essere aggiunto al [!DNL profile.cfg] file. Poiché il profilo di attribuzione dipende dal profilo SC di Adobe, il profilo SC di Adobe deve essere elencato per primo nel file di configurazione prima del profilo di attribuzione.

>[!NOTE]
>
>Questi passaggi richiedono una nuova trasformazione del set di dati.

1. Apri [!DNL profile.cfg] nella cartella del profilo personalizzato. Apri in [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. Se il profilo di attribuzione non è elencato nel file di configurazione, aggiungilo all’elenco. ![](assets/new_profile_cfg.png)

1. Assicurati che **[!UICONTROL Attribution]** sotto la **[!UICONTROL Adobe SC]** stringa di profilo.

1. Salva il [!DNL profile.cfg] e quindi salvarlo sul server da Profile Manager.

## Dichiarazione dei campi obbligatori {#section-23d4273af0c34b7a85ae3430e2c9350e}

Il profilo Attribution prende campi predefiniti e, con una serie di trasformazioni, li espone in modi nuovi e utili attraverso dimensioni estese. Per fornire il valore più immediato, il profilo di attribuzione dipende dai campi disponibili con il profilo Adobe SC.

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabili predefinite </th> 
   <th colname="col2" class="entry"> Nome campo e posizione decoder (Adobe SC) </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Campaign </td> 
   <td colname="col2"> <p>campagna x, #199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Canali marketing </td> 
   <td colname="col2"> <p>x-va_closer_detail, #162 </p> <p>x-va_instance_event, #163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento ordine </td> 
   <td colname="col2"> <p>ordine x, 206 </p> <p>x-purchaseid, #200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricavi </td> 
   <td colname="col2"> entrate x, #205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unità </td> 
   <td colname="col2"> <p>unità x, #204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Verifica che questi campi siano dichiarati nel gruppo decoder utilizzato per definire l’origine dati Adobe Analytics. Il gruppo di decodificatori predefinito viene fornito in [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. Verifica che questi campi siano dichiarati nella variabile **[!UICONTROL Fields]** della sezione [!DNL SC Fields.cfg] file. Questo file può trovarsi in [!DNL Dataset\Log Processing\SC Fields.cfg].

## Aggiunte di attribuzione e risoluzione dei problemi {#section-168133a8a1a54e1281e532033878d246}

Il profilo Attribution ha aggiunto un file di configurazione, [!DNL 0a_Marketing Channels.cfg], che copia il valore del [!DNL x-va_closer_detail] in un nuovo campo denominato [!DNL x-marketing-channel], quando [!DNL x-va_instance_event] il campo corrisponde a &quot;1&quot;. Entrambi [!DNL x-va_closer_detail] e [!DNL x-va_instant_event] vengono decodificati per impostazione predefinita e passati dalla decodifica nei pacchetti installati disponibili quando si esegue l&#39;aggiornamento alla versione 6.2.

La [!DNL x-marketing-channel] viene quindi utilizzato nella dimensione Semplice denominata Canale di marketing.

>[!IMPORTANT]
>
>Se hai modificato i profili rimuovendo i campi inutilizzati in precedenza che sono in uso, verifica che la [!DNL x-va_closer_detail] e [!DNL x-va_instance_event] i campi vengono decodificati e trasmessi per l’uso.

Se mancano campi, riceverai un messaggio nello stato dettagliato :

```
<b>x-va_closer_detail</b> is not available
```

oppure

```
<b>x-va_instance_event</b> is not available
```
