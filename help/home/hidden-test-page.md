---
title: Pagina di test nascosta
description: Questa pagina è nascosta dalla ricerca e dal sommario
hide: true
hidefromtoc: true
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Scarica Premium"
badgeExam: label="Esame ADO-E903" type="neutral"
exl-id: 02245655-511e-4e89-8846-dac85681ea91
source-git-commit: 6a10bc9a2ed41223070f3eba94b8ea7b4b1b77ab
workflow-type: tm+mt
source-wordcount: '806'
ht-degree: 3%

---

# Pagina di test nascosta

Attiva? Ricontrolla invia intorno alle 15:10. Andrà in diretta alle 15:30?

## Anteprima problema

Il paragrafo seguente non riesce a eseguire correttamente il rendering in Anteprima VSC. Non sono sicuro del perché.

Se la password viene gestita da [!DNL Adobe], è possibile [modifica la password nel tuo account di Adobe](https://helpx.adobe.com/manage-account/using/change-or-reset-password.html){target="_blank"}.

## Tipi di note

Tutti i tipi di nota supportati.

>[!NOTE]
>
>This is a standard NOTE block.

>[!TIP]
>
>This is a standard tip.

>[!IMPORTANT]
>
>Questa è una nota importante.

>[!WARNING]
>
>Questo è un avviso.

>[!CAUTION]
>
>Questa è un&#39;avvertenza.

>[!ADMIN]
>
>Questa è una nota per gli amministratori di cui viene eseguito il rendering come AMMINISTRAZIONE. Solo EXL.

>[!AVAILABILITY]
>
>Questa è una nota sulla disponibilità. Solo EXL.

>[!PREREQUISITES]
>
>Questa è una nota sui prerequisiti. Solo EXL.

>[!INFO]
>
>Questa è una nota informativa. Solo EXL.

>[!ERROR]
>
>Nota di errore. Solo EXL.

>[!SUCCESS]
>
>Questa è una nota di successo. Solo EXL.

>[!MORELIKETHIS]
>
>* Pagina 1
>* Pagina 2

## Distintivi

Un badge è un’etichetta colorata utilizzata come indicatore di contenuto. Ad esempio, puoi aggiungere un badge per contrassegnare un articolo come _Beta_ o una sezione come _Premium_. Puoi modificare il colore di un badge e associare un URL e una descrizione.

[!BADGE Esempio di badge]

Esistono due tipi of badge, ciascuno con sintassi diversa:

* **Metadati** - Visualizza il badge nella parte superiore di una pagina
* **In linea** - Visualizza il badge in cui si trova la sintassi

### Badge metadati

L’aggiunta della sintassi dei badge nei metadati posiziona un badge sopra il titolo della pagina (H1) nell’articolo.

Puoi denominare i badge, ad esempio, utilizzando _badge1_ o _badge2_. In alternativa, puoi essere più creativo (purché il nome inizi con _badge_).

Esempi di metadati:

```
badgePremium: label="Premium" type="Positive" url="https://www.premium-product.com" tooltip="Download Premium"
badgeExam: label="Exam ADO-E903" type="neutral"
```

* **badgePremium:** In questo esempio viene visualizzato un badge Premium con un URL e una descrizione comando.

* **badgeExam:** In questo esempio viene visualizzato un badge scuro con un numero ID esame.

#### Badge in linea

Specifica le informazioni del badge sulla propria riga o in un’intestazione, una tabella o un altro elemento della pagina.

Di seguito è riportata la sintassi per un badge in linea con etichetta beta, colore blu, URL e descrizione comando:

`[!BADGE Beta]{type=Informative url="https://www.example.com" tooltip="Go to example.com"}`

### Colori badge disponibili

I badge utilizzano i colori definiti nello spettro Adobe:

| Tipo | Badge |
|---|---|
| Informativo (impostazione predefinita) | [!BADGE Beta]{type=Informative url="https://www.example.com"} |
| Positivo | [!BADGE Nuova funzionalità]{type=Positive url="https://www.example.com" tooltip="Vai a example.com"} |
| Negativo | [!BADGE Interrotto]{type=negative tooltip="Questa funzione è giunta al termine del ciclo di vita"} |
| Neutro | [!BADGE Forse]{type=Neutral tooltip="Un cavaliere è caduto dal cavallo..."} |
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

### Requisiti dei distintivi

* Nei metadati sono consentiti solo due badge. Questa regola è configurabile, pertanto contattaci se hai bisogno di un’eccezione.
* È necessaria solo l’etichetta del badge. Il `type`, `url`, e `tooltip` I parametri sono facoltativi. Il `type` Il parametro determina il colore. Il `url` Il parametro consente agli utenti di fare clic sul badge per aprire un articolo o una pagina. Il `tooltip` Il parametro visualizza il testo della descrizione comandi al passaggio del mouse.
* Aggiunta di un badge a `TOC.md` file mostra il badge su ogni articolo della guida. Se specifichi un URL per il badge per passare a un articolo, assicurati di utilizzare un collegamento root (ad esempio, `/help/guide/article.md`) non un collegamento relativo (ad es. `article.md`) per tenere conto degli articoli in cartelle diverse.
* Aggiunta di un badge a `metadata-new.md` mostra il badge su ogni articolo in un archivio.
* Per i badge di metadati, assicurati che tutti i valori siano racchiusi tra virgolette. Per i badge in linea, assicurati che `url` e `tooltip` sono racchiusi tra virgolette.
* I valori validi per il tipo includono *Informativo* (impostazione predefinita, blu), *Positivo* (verde) *Negativo* (rosso), *Neutro* (grigio scuro) e *Attenzione* (giallo).
* Le etichette dei badge sono localizzate.
* Se sono specificati più badge di metadati, questi vengono visualizzati in ordine alfabetico in base al nome del badge, ad esempio `badge1:` o `badgeWeb`.
* Se desideri che l’URL venga aperto in una nuova scheda, utilizza la seguente sintassi:

  ```
  [!BADGE Open in new tab]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Open adobe.com in new tab"}
  ```

  Rendering:

  [!BADGE Apri in una nuova scheda]{type=Negative url="https://www.adobe.com newtab=true" tooltip="Apri adobe.com in una nuova scheda"}

## Evidenziazione testo

Il team Workfront ha chiesto di poter utilizzare l’evidenziazione gialla per indicare l’anteprima delle prossime funzioni. Ecco come funziona.

Esempio 1:

```
This entire paragraph should NOT be highlighted. <span class="preview"> This word is **bold** inside a highlighted sentence.</span> And this is just the last sentence.
```

Rendering:

L&#39;intero paragrafo NON deve essere evidenziato. <span class="preview"> Questa parola è **grassetto** in una frase evidenziata.</span> E questa è solo l&#39;ultima frase.

Esempio 2:

```
Highlighting should start after this paragraph.

<div class="preview">

Start of DIV.

This is a new paragraph, then an image

![image](/help/home/assets/analytics-icon-24.png)

Last highlighted item.

</div>

Not highlighted
```

Rendering:

L’evidenziazione deve iniziare dopo questo paragrafo.

<div class="preview">

Inizio DIV.

Questo è un nuovo paragrafo, quindi un’immagine

![immagine](/help/home/assets/analytics-icon-24.png)

Ultimo elemento evidenziato.

</div>

Non evidenziato

## Evidenziazione della sintassi per i blocchi di codice

L’Experience League supporta l’evidenziazione della sintassi per i blocchi di codice. Assicurati di specificare una lingua come `java` dopo il set di apri dei segni di graduazione posteriori per verificare che la sintassi sia evidenziata correttamente. Per un elenco delle lingue valide, consulta [https://prismjs.com](https://prismjs.com/#supported-languages). Se mancano le lingue, registra un ticket jira.

### Numerazione delle righe nei blocchi di codice

Aggiungi `{line-numbers="true"}` dopo la lingua per abilitare la numerazione delle righe.

Esempio con numeri di riga (&grave;&grave;&grave;`html {line-numbers="true"}`):

```html {line-numbers="true"}
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

**Inizia numerazione sulla riga _**

Aggiungi `start-number="n"` dopo la sintassi dei numeri di riga per iniziare la numerazione su un numero diverso da 1.

Esempio con nuova riga iniziale (&grave;&grave;&grave;`html {line-numbers="true" start-line="7"}`):

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

### Evidenziazione riga nei blocchi di codice

Aggiungi `highlight="n"` dopo la sintassi dei numeri di riga per evidenziare le righe all’interno di un blocco di codice. Specifica `11-13, 16` evidenzierà le righe da 11 a 13 e 16.

Esempio con evidenziazione riga (&grave;&grave;&grave;`html {line-numbers="true" start-line="7" highlight="11-13, 16"}`):

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
