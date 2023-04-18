---
title: Pagina di test nascosta
description: Questa pagina è nascosta dalla ricerca e dal sommario
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
source-git-commit: fd815415e55e72ab01a1beee9b7ebed0432eded9
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 0%

---

# Pagina di test nascosta

## Badge

Un badge è un’etichetta colorata utilizzata come indicatore di contenuto. Ad esempio, puoi aggiungere un badge per contrassegnare un articolo come _Beta_ o una sezione come _Premium_. Puoi modificare il colore di un badge e associare un URL e una descrizione comando.

[!BADGE Esempio di badge]

Esistono due tipi di badge, ciascuno con sintassi diversa:

* **Metadati** - Visualizza il badge vicino alla parte superiore di una pagina
* **In linea** - Visualizza il badge in cui si trova la sintassi

![esempi di badge](assets/badge-examples.png "Esempi di badge"){width="200" zoomable="yes"}

### Badge metadati

L’aggiunta della sintassi del badge nei metadati posiziona un badge sopra il titolo della pagina (H1) nell’articolo.

Ad esempio, puoi assegnare un nome ai badge utilizzando _badge1_ o _badge2_. Oppure, puoi essere più creativo (purché il nome inizi con _badge_).

Esempi di metadati:

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium:** In questo esempio viene visualizzato un badge Premium con un URL e una descrizione comandi.

* **badgeExam:** In questo esempio viene visualizzato un badge scuro con un numero di ID dell&#39;esame.

#### Badge in linea

Specifica le informazioni del badge sulla riga corrispondente o in un’intestazione, una tabella o un altro elemento di pagina.

Di seguito è riportata la sintassi per un badge in linea con un’etichetta beta, un colore blu, un URL e una descrizione comando:

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### Colori del badge disponibili

I badge utilizzano i colori definiti in Adobe Spettro:

| Tipo | Badge |
|---|---|
| Informativo (predefinito) | [!BADGE Beta]{type=Informative url="https://www.example.com"} |
| Positivo | [!BADGE Nuova funzionalità]{type=Positive url="https://www.example.com" tooltip="Vai a example.com"} |
| Negativo | [!BADGE Disattivato]{type=negative tooltip="Questa funzione è ora terminata"} |
| Neutro | [!BADGE Forse]{type=Neutral tooltip="Un cavaliere cadde dal cavallo.."} |
| Attenzione | [!BADGE Attenzione]{type=Caution tooltip="Stato giallo"} |

Esempi di sintassi

```
|Type|Badge|
|---|---|
|Informative (default)|[!BADGE Beta]{type=Informative url="https://www.example.com"}|
|Positive|[!BADGE New Feature]{type=Positive url="https://www.example.com" tooltip="Go to example.com"}|
|Negative|[!BADGE Discontinued]{type=negative tooltip="This feature is now end of life"}|
|Neutral|[!BADGE Maybe]{type=Neutral tooltip="A rider fell off the horse..."}|
|Caution|[!BADGE Attention]{type=Caution tooltip="Yellow status"}|
```

### Requisiti per i distintivi

* Nei metadati sono consentiti solo due badge. Questa regola è configurabile, quindi informaci se hai bisogno di un&#39;eccezione.
* È richiesta solo l’etichetta del badge. La `type`, `url`e `tooltip` i parametri sono facoltativi. La `type` determina il colore. La `url` consente agli utenti di fare clic sul badge per aprire un articolo o una pagina. La `tooltip` visualizza il testo della descrizione comando al passaggio del mouse.
* Aggiunta di un badge a `TOC.md` in file viene visualizzato il badge su ogni articolo della guida. Se specifichi un URL per il badge per passare a un articolo, accertati di utilizzare un collegamento principale (ad esempio, `/help/guide/article.md`) non un collegamento relativo (ad esempio, `article.md`) per tenere conto degli articoli in cartelle diverse.
* Aggiunta di un badge a `metadata-new.md` visualizza il badge su ogni articolo di un repo.
* Per i badge per metadati, accertati che tutti i valori siano racchiusi tra virgolette. Per i badge in linea, assicurati che `url` e `tooltip` sono racchiusi tra virgolette.
* I valori di tipo validi includono *Informativo* (predefinito, blu), *Positivo* (verde), *Negativo* (rosso), *Neutro* (grigio scuro) e *Attenzione* (giallo).
* Le etichette dei badge sono localizzate.
* Se sono specificati più badge per metadati, i badge vengono visualizzati in ordine alfabetico in base al nome del badge, ad esempio `badge1:` o `badgeWeb`.
* Se desideri che l’URL venga aperto in una nuova scheda, utilizza la sintassi seguente:

   ```
   [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
   ```

   Rendering:

   [!BADGE Apri in una nuova scheda]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Apri adobe.com nella nuova scheda"}

## Evidenziazione del testo

Il team Workfront ha chiesto di poter utilizzare l’evidenziazione gialla per indicare l’anteprima delle prossime funzioni. Ecco come funziona.

Esempio:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

Rendering:

L&#39;intero paragrafo NON deve essere evidenziato. <span class="preview"> Questa parola è **audace** all&#39;interno di una frase evidenziata.</span> E questa è solo l&#39;ultima frase.

Come regola generale, utilizza `<span class="preview">` per evidenziare un paragrafo o un testo all’interno di un paragrafo e utilizzare `<div class="preview">` per più paragrafi e componenti.

## Evidenziazione della sintassi per i blocchi di codice

L&#39;Experience League supporta l&#39;evidenziazione della sintassi per i blocchi di codice. Assicurati di specificare una lingua come `java` dopo il set di apertura dei contrassegni posteriori per assicurarti che la sintassi sia evidenziata correttamente. Per un elenco delle lingue valide, vedere [https://prismjs.com](https://prismjs.com/#supported-languages). Se mancano delle lingue, registra un biglietto jira.

### Numerazione delle righe nei blocchi di codice

Aggiungi `{line-numbers="true"}` dopo la lingua per abilitare la numerazione delle righe.

Esempio con numeri di riga (&grave;&grave;&grave;&grave;`html {line-numbers="true"}`):

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**Inizia la numerazione alla riga _**

Aggiungi `start-number="n"` dopo la sintassi del numero di riga per iniziare la numerazione su un numero diverso da 1.

Esempio con nuova riga iniziale (&grave;&grave;&grave;&amp;grave)`html {line-numbers="true" start-line="7"}`):

```html {line-numbers="true" start-line="7"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```

### Evidenziazione delle linee nei blocchi di codice

Aggiungi `highlight="n"` dopo la sintassi del numero di riga per evidenziare le righe all&#39;interno di un blocco di codice. Specifica `11-13, 16` evidenziano le linee da 11 a 13 e 16.

Esempio con evidenziazione linea (&grave;&grave;&grave;&grave;`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`):

```html {line-numbers="true" start-line="7" highlight="11-13, 16"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>
<p>My second paragraph.</p>

</body>
</html>
```
