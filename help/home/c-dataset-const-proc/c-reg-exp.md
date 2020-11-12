---
description: Le espressioni regolari vengono utilizzate in tutti i campi di ricerca workbench dati, compresi i pannelli delle entità di query.
solution: Analytics
title: Espressioni regolari
topic: Data workbench
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
translation-type: tm+mt
source-git-commit: 0727e5b18c89a22b6ee775b1293d3b68e5cee81c
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 2%

---


# Espressioni regolari{#regular-expressions}

Le espressioni regolari vengono utilizzate in tutti i campi di ricerca workbench dati, compresi i pannelli delle entità di query.

* [Informazioni sulle espressioni regolari](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [Terminologia delle espressioni regolari](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [Informazioni sulla corrispondenza letterale](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [Utilizzo dei metacaratteri](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [Estrazione pattern](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## Informazioni sulle espressioni regolari {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

Un&#39;espressione regolare è un pattern di testo, composto da una combinazione di caratteri alfanumerici e caratteri speciali noti come metacaratteri, che individua i pattern ed estrae le sottostringhe dal testo. Le espressioni regolari sono ampiamente utilizzate nella programmazione informatica e sono parte integrante di linguaggi come Perl.

Per identificare ed estrarre pattern di stringhe complessi, il server workbench dati utilizza espressioni regolari in alcune delle trasformazioni e condizioni. Di seguito è riportata una breve guida alle espressioni regolari.

Questa appendice non è un&#39;introduzione completa alle espressioni regolari. Un riferimento particolarmente buono è la pubblicazione O&#39;Reilly *Mastering Regular Expressions, 2nd Edition* di Jeffrey E. F. Friedl.

## Terminologia delle espressioni regolari {#section-80b0d54f731e448391532ab3eb3c525c}

| Termine | Definizione |
|---|---|
| Letterale | Un letterale è un carattere utilizzato in un&#39;espressione regolare per individuare una sequenza specifica di caratteri. Ad esempio, per trovare un prodotto in [!DNL shop/products.html], il prodotto stringa è letterale, o quello che stiamo letteralmente cercando nella stringa. |
| Metacaratterio | Un metacarattere è un carattere speciale che ha un&#39;interpretazione univoca nel contesto delle espressioni regolari. Ad esempio, il punto (.) è un metacarattere utilizzato per far corrispondere qualsiasi carattere. |
| Sequenza di escape | Una sequenza di escape è semplicemente un modo per dire al motore di espressione regolare che vorremmo usare uno dei metacaratteri come letterale. Le sequenze di escape iniziano sempre con il carattere barra rovesciata (`\`). Posizionando la barra rovesciata (che è anche un metacarattere) davanti a un metacarattero, il motore di espressione regolare interpreta il metacarattero con escape come letterale. Ad esempio, se si desidera che il metacarattere corrisponda al periodo (`.`), è necessario utilizzare una sequenza di escape. Tuttavia, per corrispondere a uno dei punti nella stringa 168.196.0.11, è possibile utilizzare l&#39;espressione regolare costituita da una barra rovesciata e un punto (`\.`). |
| Pattern | Terminologia abbreviata per l&#39;espressione regolare. In sostanza, un&#39;espressione regolare è un pattern a cui si sta tentando di trovare una corrispondenza rispetto alla stringa di destinazione. |
| Stringa di destinazione | Questo termine si riferisce alla stringa all&#39;interno della quale si sta cercando per individuare il pattern desiderato. |

## Informazioni sulla corrispondenza letterale {#section-ec4497e3160c47ba9b828d939761b3e0}

La corrispondenza letterale prende una stringa letterale senza caratteri escape e cerca nella stringa di destinazione per vedere se si tratta di una sottostringa della stringa di destinazione.

In questo esempio viene illustrato il funzionamento della corrispondenza letterale. Considerare la situazione in cui i dati vengono raccolti dal traffico del sito Web e il campo cs(referrer) contiene il seguente valore:

`http://www.abc.com/adventurenews/today.html?ad=123AZ45`

Per determinare se il referente rappresenta qualcuno che ha fatto clic su uno degli annunci, è necessario verificare se il referente contiene la stringa annuncio. È possibile utilizzare semplicemente la stringa letterale ad per cercare la stringa di destinazione e determinare se un annuncio pubblicitario è stato utilizzato per indirizzare il traffico al sito. Anche se questo corrisponderebbe alla stringa di destinazione, corrisponderebbe in due posizioni ed è quindi ambiguo e può portare a falsi positivi.

L&#39;URL seguente contiene la stringa ad in due posizioni diverse:

`http://www.abc.com/ad vertnews/today.html?ad =123AZ45`

Pertanto, se state cercando di determinare quali sessioni sono iniziate a seguito di una particolare campagna pubblicitaria, è chiaro che non è sufficiente utilizzare semplicemente l&#39;annuncio letterale come espressione regolare. Modificando il valore letterale in &quot;ad=&quot; si eliminerebbe questa ambiguità e l’espressione corrisponderebbe solo a una singola corrispondenza. Tuttavia, anche questo potrebbe non essere sufficiente a garantire che il referente facesse parte della campagna pubblicitaria. Considerate il referente seguente:

`http://www.xyz.com/hello.html?pad=something`

Non potete controllare gli URL che altri utenti potrebbero usare per creare collegamenti al sito. La corrispondenza letterale è un meccanismo troppo semplice per individuare le sessioni iniziate a seguito della campagna pubblicitaria. Nella sezione seguente viene illustrato come utilizzare i metacaratteri per ottenere una corrispondenza più flessibile e potente.

## Utilizzo dei metacaratteri {#section-e29a804336304ea1ba33d40d60139aa2}

Un metacarattere è un carattere speciale in un programma o in un campo di dati che fornisce informazioni sugli altri caratteri.

| metacarattero | description |
|---|---|
| . (punto) | Corrisponde a un singolo carattere, ad esempio: `re:x.z` corrisponde a &quot;xyz&quot; o &quot;xxz&quot;. |
| * (stella) | Corrisponde a uno o più caratteri, ad esempio: `re:Z*` corrisponde a &quot;ZZZ&quot;. |
| ? (carattere jolly) | Corrisponde a 0 o 1 dell&#39;espressione precedente per imporre una corrispondenza minima, ad esempio: `xy?z` restituisce &quot;xy&quot; e &quot;xyz&quot;. |

È inoltre possibile utilizzare espressioni regolari comuni aggiuntive per creare stringhe di ricerca più complesse.

**Elenchi, intervalli e OR**

La corrispondenza letterale consente di cercare una singola stringa, ma tra parentesi, trattini e pipe è possibile definire un elenco di elementi da cercare nella stringa di destinazione.

<table id="table_18B86955EC3748079E7C176273ADE92B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo metacarattere... </th> 
   <th colname="col2" class="entry"> Il processore delle espressioni regolari... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Parentesi quadrate ([ ]) </td> 
   <td colname="col2"> Associare uno qualsiasi dei caratteri all'interno della parentesi con una singola posizione carattere. Ad esempio, [AB] è un'istruzione per far corrispondere la lettera A o la lettera B e [0123456789] indica che corrisponde a qualsiasi carattere compreso tra 0 e 9. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Trattino (-) </td> 
   <td colname="col2"> <p>Corrisponde a un intervallo di caratteri. Così, invece di scrivere [0123456789] potremmo semplicemente scrivere [0-9]. </p> <p> Può essere esteso a intervalli di caratteri e a più intervalli all’interno di un unico set di parentesi. Ad esempio, [0-9A-C] corrisponde ai caratteri da 0 a 9 e da A a C. </p> <p> <p>Nota:  Per verificare se un trattino (-) è un letterale tra parentesi quadre, deve essere primo o ultimo. Ad esempio, [-0-9] test per - e da 0 a 9. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Pipe (|) </td> 
   <td colname="col2"> Eseguire una corrispondenza tra due scelte e una stringa di destinazione specifica. Ad esempio, b|nat corrisponde a bat o nat. </td> 
  </tr> 
 </tbody> 
</table>

Prendi in considerazione gli esempi seguenti:

| Pattern | Stringa | Corrispondenza |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| Lezione`[A-Z]` | Lezioni | Nessuna corrispondenza perché la lettera a nella parte inferiore non è compresa nell&#39;intervallo tra A e Z nella parte superiore della barra. |

**Negazione**

La negazione è un modo per dire che si desidera corrispondere a qualsiasi cosa tranne i caratteri specificati. Il metacarattere di negazione, la cirflex o il caret (`^`), viene usato come primo carattere all&#39;interno di parentesi per dire che si desidera che la corrispondenza sia qualsiasi cosa tranne i caratteri rimanenti tra parentesi. Ad esempio, per far corrispondere qualsiasi carattere tranne il punto e virgola (`;`), è necessario scrivere

[`^;`]

Questo corrisponde a qualsiasi carattere tranne il punto e virgola.

**Posizionamento**

Per forzare una corrispondenza all&#39;inizio o alla fine di una stringa di destinazione, vengono utilizzati uno dei due metacaratteri.

| Per questo metacarattere... | Il processore delle espressioni regolari... |
|---|---|
| Circumflex o Caret (`^`) | Corrispondenza rispetto all&#39;inizio della stringa. Ad esempio, ^`[Tt]`corrisponderebbe alla stringa di destinazione &quot;L&#39;inizio&quot; ma non alla stringa &quot;Questo è l&#39;inizio&quot;. |
| Simbolo del dollaro (`$`) | Corrispondenza rispetto alla fine della stringa. Ad esempio, `[Ee]`nd$ corrisponderebbe a &quot;This is the end&quot; ma non a &quot;The end is a special time&quot;. |

>[!NOTE]
>
>Quando l&#39;espressione regolare contiene ^ all&#39;inizio e $ alla fine, l&#39;intera stringa di destinazione deve corrispondere all&#39;espressione regolare.

**Qualsiasi corrispondenza**

Il punto (.) è un metacarattere speciale che corrisponde a qualsiasi carattere nella stringa di destinazione. Ad esempio, l&#39;espressione regolare `^…$` corrisponde a qualsiasi stringa di destinazione che sia esattamente lunga tre caratteri. L&#39;espressione regolare &quot;...&quot; corrisponde a qualsiasi stringa di destinazione che contenga almeno tre caratteri.

**Pattern ripetuti**

I metacaratteri di iterazione consentono di far corrispondere un pattern più di una volta.

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Per questo metacarattere... </th> 
   <th colname="col2" class="entry"> Il processore delle espressioni regolari... </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Punto interrogativo (?) </td> 
   <td colname="col2"> Nessuna istanza o un'istanza del carattere immediatamente precedente il metacarattere (?). Ad esempio, l'area del pattern?d corrisponde al rosso e alla lettura. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Asterisco (*) </td> 
   <td colname="col2"> Corrisponde a zero o più occorrenze del carattere immediatamente precedente il metacarattere (*). Ad esempio, il pattern [0-9]* corrisponde a qualsiasi numero di caratteri da 0 a 9 (qualsiasi numero intero). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Plus (+) </td> 
   <td colname="col2"> Corrisponde a una o più occorrenze del carattere o dell'intervallo precedente. Ad esempio, il pattern thre+ corrisponderebbe a tre ma non a uno. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n} </td> 
   <td colname="col2"> <p>Corrispondenza esatta del carattere o dell'intervallo di procedimento con un valore identico a n volte. Il pattern seguente corrisponde ai numeri di telefono degli Stati Uniti: <code>[0-9]{3}-[0-9]{3}-[0-9]{4}</code>. </p> <p> Sebbene non sia un pattern ottimale, determina se la stringa di destinazione è nel formato corretto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> {n,m} </td> 
   <td colname="col2"> Corrisponde al carattere precedente almeno n volte e al massimo m volte. Ad esempio, fo{1,2}d corrisponderebbe a cibo e alimenti ma non a cibo. </td> 
  </tr> 
 </tbody> 
</table>

## Estrazione pattern {#section-4389779653b64f6cb7c47615b25c1a79}

La corrispondenza dei pattern è solo una parte della potenza delle espressioni regolari. Le espressioni regolari forniscono inoltre un meccanismo per l&#39;estrazione di porzioni chiave di una stringa di destinazione. Questo avviene tramite l&#39;uso delle parentesi sinistra e destra. Tali estrazioni vengono in genere utilizzate come input in un altro processo e sono accessibili tramite l&#39;uso di *%position%*, dove position è un numero intero che fa riferimento al conteggio di cui è stato confrontato il set di parentesi.

Considerare i seguenti esempi di estrazione dei pattern:

<table id="table_BC8D471B966844049FFFCDEC0F183941"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Pattern </th> 
   <th colname="col2" class="entry"> Stringa </th> 
   <th colname="col3" class="entry"> Corrispondenza </th> 
   <th colname="col4" class="entry"> Estrazione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Win(9[58]) </td> 
   <td colname="col2"> OS=Win95 </td> 
   <td colname="col3"> Win95 </td> 
   <td colname="col4"> %1% = 95 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> (Win)(95|8) </td> 
   <td colname="col2"> OS=Win98 </td> 
   <td colname="col3"> Win98 </td> 
   <td colname="col4"> <p>%1% = Win </p> <p> %2% = 98 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mozilla/([0-9]).([0-9]) </td> 
   <td colname="col2"> Mozilla/3.0 </td> 
   <td colname="col3"> Mozilla/3,03 </td> 
   <td colname="col4"> <p>%1% = 3 </p> <p> %2% = 0 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lezione([A-Z]) </td> 
   <td colname="col2"> Lezioni </td> 
   <td colname="col3"> Nessuna corrispondenza perché la lettera a inferiore non è compresa nell'intervallo tra A e Z superiore </td> 
   <td colname="col4"> </td> 
  </tr> 
 </tbody> 
</table>

