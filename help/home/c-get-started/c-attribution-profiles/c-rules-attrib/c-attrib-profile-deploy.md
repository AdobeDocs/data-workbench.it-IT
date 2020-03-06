---
description: Il profilo Attribuzione è un profilo ereditato, pronto per essere rilasciato. In combinazione con il profilo Adobe SC e il feed di dati Analytics (SC/Insight), il profilo può essere implementato per esporre rapidamente nuovi modelli di attribuzione tra canali digitali.
title: Distribuzione del profilo di attribuzione
uuid: acc4e92a-2af1-4993-bae7-015ece3da26c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Distribuzione del profilo di attribuzione{#deploying-the-attribution-profile}

Il profilo Attribuzione è un profilo ereditato, pronto per essere rilasciato. In combinazione con il profilo Adobe SC e il feed di dati Analytics (SC/Insight), il profilo può essere implementato per esporre rapidamente nuovi modelli di attribuzione tra canali digitali.

Dopo aver salvato il profilo di attribuzione sul server principale, sono necessari due passaggi aggiuntivi per integrarlo nel profilo corrente all&#39;interno della [!DNL Profile] directory: (1) Impostate il file Profile.cfg e (2) Dichiarate i campi obbligatori.

## Impostazione del file Profile.cfg {#section-7531cb865d994207baba692a6fc842d7}

Come tutti i profili, anche il profilo Attribuzione deve essere aggiunto al [!DNL profile.cfg] file. Poiché il profilo Attribuzione dipende dal profilo Adobe SC, il profilo Adobe SC deve essere elencato per primo nel file di configurazione prima del profilo Attribution.

>[!NOTE]
>
>Questi passaggi richiederanno una nuova trasformazione del dataset.

1. Aprite il [!DNL profile.cfg] file nella cartella del profilo personalizzato. (Apri in [!DNL server\Profiles\(custom profile name)\profile.cfg].

1. Se il profilo Attribuzione non è elencato nel file di configurazione, aggiungetelo all&#39;elenco. ![](assets/new_profile_cfg.png)

1. Assicurarsi che la **[!UICONTROL Attribution]** stringa sia elencata sotto la stringa del **[!UICONTROL Adobe SC]** profilo.

1. Salvare il [!DNL profile.cfg] file aggiornato e salvarlo sul server da Gestione profili.

## Dichiarazione dei campi obbligatori {#section-23d4273af0c34b7a85ae3430e2c9350e}

Il profilo Attribuzione prende campi predefiniti e con una serie di trasformazioni questi campi vengono esposti in modi nuovi e utili attraverso le dimensioni estese. Per fornire il valore più immediato, il profilo Attribuzione dipende dai campi disponibili con il profilo Adobe SC.

<table id="table_97751B73CCAA4B96BB162641A178A68A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabili predefinite </th> 
   <th colname="col2" class="entry"> Nome campo e posizione decoder (Adobe SC) </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Campagna </td> 
   <td colname="col2"> <p>x-campaign, #199 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Canali marketing </td> 
   <td colname="col2"> <p>x-va_closer_detail, #162 </p> <p>x-va_instance_event, #163 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Evento order </td> 
   <td colname="col2"> <p>x-order, #206 </p> <p>x-purchaseid, #200 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricavi </td> 
   <td colname="col2"> x-Revenue, #205 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unità </td> 
   <td colname="col2"> <p>x-units, #204 </p> </td> 
  </tr> 
 </tbody> 
</table>

1. Verifica che questi campi siano dichiarati nel gruppo decodificatore utilizzato per definire l&#39;origine dati di Adobe Analytics. Il gruppo di decodificatori predefinito è fornito in [!DNL Dataset\Log Procesing\Decoding Instructions.cfg].
1. Verificate che questi campi siano dichiarati nella **[!UICONTROL Fields]** sezione del [!DNL SC Fields.cfg] file. In questo file si trova [!DNL Dataset\Log Processing\SC Fields.cfg].

## Aggiunte di attribuzione e risoluzione dei problemi {#section-168133a8a1a54e1281e532033878d246}

Il profilo Attribuzione ha aggiunto un file di configurazione [!DNL 0a_Marketing Channels.cfg], che copia il valore del [!DNL x-va_closer_detail] campo in un nuovo campo denominato [!DNL x-marketing-channel], quando il [!DNL x-va_instance_event] campo corrisponde a &quot;1&quot;. Sia [!DNL x-va_closer_detail] che [!DNL x-va_instant_event] vengono decodificati per impostazione predefinita e passati dalla decodifica nei pacchetti installati disponibili quando si esegue l&#39;aggiornamento alla versione 6.2.

Il [!DNL x-marketing-channel] campo viene quindi utilizzato nella dimensione Semplice denominata Canale marketing.

>[!IMPORTANT]
>
>Se avete modificato i profili rimuovendo i campi precedentemente inutilizzati che vengono ora utilizzati, sarà necessario verificare che i campi [!DNL x-va_closer_detail] e [!DNL x-va_instance_event] i campi siano stati decodificati e passati per l&#39;uso.

Se mancano i campi, riceverai un messaggio nello stato dettagliato:

```
<b>x-va_closer_detail</b> is not available
```

 oppure 

```
<b>x-va_instance_event</b> is not available
```

