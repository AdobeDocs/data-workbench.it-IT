---
description: Le espressioni regolari vengono utilizzate in tutti i campi di ricerca di Data Workbench, compresi i pannelli entità query.
title: Espressioni regolari
uuid: f3a0119d-6fac-4f63-8dca-4db32d2a737a
exl-id: 75841a70-e78a-429b-b00d-ac107b7a87aa
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1418'
ht-degree: 2%

---

# Espressioni regolari{#regular-expressions}

{{eol}}

Le espressioni regolari vengono utilizzate in tutti i campi di ricerca di Data Workbench, compresi i pannelli entità query.

* [Informazioni sulle espressioni regolari](../../home/c-dataset-const-proc/c-reg-exp.md#section-cc9dc7293bb04fc0b41fe8acdee708f0)
* [Terminologia con espressione regolare](../../home/c-dataset-const-proc/c-reg-exp.md#section-80b0d54f731e448391532ab3eb3c525c)
* [Informazioni sulla corrispondenza letterale](../../home/c-dataset-const-proc/c-reg-exp.md#section-ec4497e3160c47ba9b828d939761b3e0)
* [Utilizzo dei metacaratteri](../../home/c-dataset-const-proc/c-reg-exp.md#section-e29a804336304ea1ba33d40d60139aa2)
* [Estrazione pattern](../../home/c-dataset-const-proc/c-reg-exp.md#section-4389779653b64f6cb7c47615b25c1a79)

## Informazioni sulle espressioni regolari {#section-cc9dc7293bb04fc0b41fe8acdee708f0}

Un’espressione regolare è un pattern di testo, costituito da una combinazione di caratteri alfanumerici e caratteri speciali noti come metacaratteri, che individua i pattern ed estrae le sottostringhe dal testo. Le espressioni regolari sono ampiamente utilizzate nella programmazione informatica e sono parte integrante di lingue come Perl.

Per identificare ed estrarre pattern di stringa complessi, il server di Data Workbench utilizza espressioni regolari in alcune delle trasformazioni e condizioni. Di seguito è riportata una breve guida alle espressioni regolari.

Questa appendice non è un’introduzione completa alle espressioni regolari. Un riferimento particolarmente valido è la pubblicazione O&#39;Reilly *Espressioni regolari di masterizzazione, 2a edizione* di Jeffrey E. F. Friedl.

## Terminologia con espressione regolare {#section-80b0d54f731e448391532ab3eb3c525c}

| Termine | Definizione |
|---|---|
| Letterale | Un letterale è un carattere utilizzato in un’espressione regolare per individuare una sequenza specifica di caratteri. Ad esempio, per trovare il prodotto in [!DNL shop/products.html], il prodotto stringa è letterale, o quello che stiamo letteralmente cercando nella stringa. |
| Metacarattero | Un metacarattero è un carattere speciale che ha un&#39;interpretazione univoca nel contesto delle espressioni regolari. Ad esempio, il punto (.) è un metacarattero utilizzato per associare qualsiasi carattere. |
| Sequenza di escape | Una sequenza di escape è semplicemente un modo per dire al motore di espressione regolare che vorremmo utilizzare uno dei metacaratteri come letterale. Le sequenze di escape iniziano sempre con il carattere barra rovesciata (`\`). Posizionando la barra rovesciata (che è anche un metacarattero) davanti a un metacarattero, il motore di espressione regolare interpreta il metacarattero evitato come un letterale. Ad esempio, se desideri ottenere una corrispondenza con il periodo del metacarattero (`.`), è necessario utilizzare una sequenza di escape. Tuttavia, per corrispondere a uno dei periodi della stringa 168.196.0.11, puoi utilizzare l’espressione regolare costituita da una barra inversa e un punto (`\.`). |
| Pattern | Terminologia abbreviata per l&#39;espressione regolare. In sostanza, un&#39;espressione regolare è un pattern a cui si sta tentando di corrispondere rispetto alla stringa di destinazione. |
| Stringa di destinazione | Questo termine si riferisce alla stringa in cui si sta cercando per individuare il pattern desiderato. |

## Informazioni sulla corrispondenza letterale {#section-ec4497e3160c47ba9b828d939761b3e0}

La corrispondenza letterale prende una stringa letterale senza caratteri di escape e cerca nella stringa di destinazione per vedere se si tratta di una sottostringa della stringa di destinazione.

In questo esempio viene illustrato il funzionamento della corrispondenza letterale. Considera una situazione in cui i dati vengono raccolti dal traffico del sito web e il campo cs(referrer) contiene il seguente valore:

`https://www.abc.com/adventurenews/today.html?ad=123AZ45`

Per determinare se il referente rappresenta un utente che ha fatto clic su uno degli annunci pubblicitari, è necessario vedere se il referrer contiene l&#39;annuncio stringa. Puoi semplicemente utilizzare la stringa letterale annuncio per cercare la stringa di destinazione e determinare se un annuncio è stato utilizzato per indirizzare il traffico al sito. Anche se questo corrisponderebbe alla stringa di destinazione, corrisponderebbe in due posizioni ed è quindi ambiguo e può portare a falsi positivi.

Il seguente URL contiene la stringa annuncio in due posizioni diverse:

`https://www.abc.com/ad vertnews/today.html?ad =123AZ45`

Pertanto, se cerchi di determinare quali sessioni sono iniziate a seguito di una particolare campagna pubblicitaria, è chiaro che non è sufficiente utilizzare semplicemente l’annuncio letterale come espressione regolare. Modificando il valore letterale in &quot;ad=&quot; si eliminerebbe questa ambiguità e si otterrebbe una sola corrispondenza nell’espressione. Tuttavia, anche questo potrebbe non essere sufficiente per garantire che il referrer facesse parte della campagna pubblicitaria. Considera il referente seguente:

`https://www.xyz.com/hello.html?pad=something`

Non hai alcun controllo sugli URL che altri utenti potrebbero utilizzare per creare collegamenti al sito. La corrispondenza letterale è un meccanismo troppo semplice per individuare le sessioni iniziate a seguito della campagna pubblicitaria. La sezione seguente illustra come utilizzare i metacaratteri per ottenere una corrispondenza più flessibile e potente.

## Utilizzo dei metacaratteri {#section-e29a804336304ea1ba33d40d60139aa2}

Un metacarattero è un carattere speciale in un programma o in un campo di dati che fornisce informazioni su altri caratteri.

| metacarattero | descrizione |
|---|---|
| . (punto) | Corrisponde a un singolo carattere, ad esempio: `re:x.z` corrisponde a &quot;xyz&quot; o &quot;xxz&quot;. |
| * (stella) | Corrisponde a uno o più caratteri, ad esempio: `re:Z*` corrisponde a &quot;ZZZ&quot;. |
| ? (carattere jolly) | Corrisponde a 0 o 1 dell&#39;espressione precedente per forzare la corrispondenza minima, ad esempio: `xy?z` corrisponde a &quot;xy&quot; e &quot;xyz&quot;. |

È inoltre possibile utilizzare espressioni regolari comuni aggiuntive per creare stringhe di ricerca più complesse.

**Elenchi, intervalli e OR**

La corrispondenza letterale consente di cercare una singola stringa, ma parentesi graffe, trattini e tubi consentono di definire un elenco di elementi da cercare nella stringa di destinazione.

<table id="table_18B86955EC3748079E7C176273ADE92B">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Per questo metacarattero... </th>
   <th colname="col2" class="entry"> Il processore di espressioni regolari.. </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Parentesi quadrate ([ ]) </td>
   <td colname="col2"> Associa uno qualsiasi dei caratteri all’interno della parentesi con una posizione di un singolo carattere. Ad esempio, [AB] è un'istruzione che deve corrispondere alla lettera A o alla lettera B e [0123456789] indica che deve corrispondere a qualsiasi carattere compreso tra 0 e 9. </td>
  </tr>
  <tr>
   <td colname="col1"> Trattino (-) </td>
   <td colname="col2"> <p>Associa un intervallo di caratteri. Così, invece di scrivere [0123456789], potevamo semplicemente scrivere [0-9]. </p> <p> Può essere esteso a intervalli di caratteri e a intervalli multipli all’interno di un set di parentesi. Ad esempio, [0-9A-C] corrisponde ai caratteri da 0 a 9 e da A a C. </p> <p> <p>Nota: Per verificare che un trattino (-) sia un letterale all'interno delle parentesi, deve essere primo o ultimo. Ad esempio, test [-0-9] per - e da 0 a 9. </p> </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Barra verticale (|) </td>
   <td colname="col2"> Associa una delle due scelte a una stringa di destinazione specificata. Ad esempio, b|nat corrisponde a bat o nat. </td>
  </tr>
 </tbody>
</table>

Prendi in considerazione gli esempi seguenti:

| Pattern | Stringa | Corrispondenza |
|---|---|---|
| Win9`[58]` | OS=Win95 | Win95 |
| Win95 | 8 | OS=Win98 | Win98 |
| `[0-9]` | Mozilla/3.0 | 3 |
| Lezione`[A-Z]` | Lezione a | Nessuna corrispondenza perché il carattere a in minuscolo non è compreso nell&#39;intervallo tra A e Z in maiuscolo. |

**Negazione**

La negazione è un modo per dire che si desidera abbinare qualsiasi cosa tranne i caratteri specificati. Il metacarattero di negazione, la cirflex o il caret (`^`), viene utilizzato come primo carattere tra parentesi per specificare che la corrispondenza deve essere qualsiasi cosa tranne i caratteri rimanenti tra parentesi. Ad esempio, per far corrispondere qualsiasi carattere tranne un punto e virgola (`;`), scrivereste

[`^;`]

Questo corrisponde a qualsiasi carattere tranne il punto e virgola.

**Posizionamento**

Per forzare una corrispondenza all’inizio o alla fine di una stringa di destinazione, vengono utilizzati uno dei due metacaratteri.

| Per questo metacarattero... | Il processore di espressioni regolari.. |
|---|---|
| Circumflex o Carrello (`^`) | Confronta con l&#39;inizio della stringa. Ad esempio, ^`[Tt]`corrisponderebbe alla stringa di destinazione &quot;L&#39;inizio&quot; ma non corrisponde a &quot;Questo è l&#39;inizio&quot;. |
| Simbolo del dollaro (`$`) | Confronta con la fine della stringa. Ad esempio: `[Ee]`E$ corrisponderebbe a &quot;This is the end&quot; ma non corrisponderebbe a &quot;The end is a special time&quot;. |

>[!NOTE]
>
>Quando l&#39;espressione regolare contiene ^ all&#39;inizio e $ alla fine, l&#39;intera stringa di destinazione deve corrispondere all&#39;espressione regolare.

**Corrispondenza a qualsiasi elemento**

Il periodo (.) è un metacarattero speciale che corrisponde a qualsiasi carattere nella stringa di destinazione. Ad esempio, l’espressione regolare `^…$` corrisponde a qualsiasi stringa di destinazione con una lunghezza di esattamente tre caratteri. L&#39;espressione regolare &quot;...&quot; corrisponde a qualsiasi stringa di destinazione che contiene almeno tre caratteri.

**Pattern ripetuti**

I metacaratteri di iterazione consentono di associare un pattern più di una volta.

<table id="table_6A14333D6C264A48ADF1EBBAF687CADD">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Per questo metacarattero... </th>
   <th colname="col2" class="entry"> Il processore di espressioni regolari.. </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Punto interrogativo (?) </td>
   <td colname="col2"> Non associare alcuna istanza o istanza del carattere immediatamente precedente il metacarattero (?). Ad esempio, l'area del pattern?d corrisponde al rosso e alla lettura. </td>
  </tr>
  <tr>
   <td colname="col1"> Asterisco (*) </td>
   <td colname="col2"> Corrispondenza a zero o più occorrenze del carattere immediatamente precedente il metacarattero (*). Ad esempio, il pattern [0-9]* corrisponde a qualsiasi numero di caratteri da 0 a 9 (qualsiasi numero intero). </td>
  </tr>
  <tr>
   <td colname="col1"> Plus (+) </td>
   <td colname="col2"> Corrispondere a una o più occorrenze del carattere o dell'intervallo precedente. Ad esempio, il pattern thre+ corrisponde a tre ma non a. </td>
  </tr>
  <tr>
   <td colname="col1"> {n} </td>
   <td colname="col2"> <p>Corrispondere esattamente n volte al carattere o all'intervallo di procedimento. Il seguente pattern corrisponde ai numeri di telefono degli Stati Uniti: <code>[0-9]{3}-[0-9]{3}-[0-9]{4}</code>. </p> <p> Sebbene non sia un pattern ottimale, determina se la stringa di destinazione è nel formato corretto. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> {n,m} </td>
   <td colname="col2"> Corrispondere al carattere precedente almeno n volte e al massimo m volte. Ad esempio, per{1,2}d corrisponderebbe a alimenti e alimenti ma non a alimenti. </td>
  </tr>
 </tbody>
</table>

## Estrazione pattern {#section-4389779653b64f6cb7c47615b25c1a79}

La corrispondenza dei pattern è solo una parte della potenza delle espressioni regolari. Le espressioni regolari forniscono inoltre un meccanismo per l&#39;estrazione di parti chiave di una stringa di destinazione. Questo viene fatto utilizzando le parentesi sinistra e destra. Queste estrazioni vengono generalmente utilizzate come input in un altro processo e sono accessibili tramite l&#39;uso di *%position%*, dove position è un numero intero che fa riferimento al numero di cui è stata confrontata l’insieme di parentesi.

Prendi in considerazione i seguenti esempi di estrazione del pattern:

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
   <td colname="col2"> Lezione a </td>
   <td colname="col3"> Nessuna corrispondenza perché la A in minuscolo non è compresa nell'intervallo tra A in maiuscolo e Z </td>
   <td colname="col4"> </td>
  </tr>
 </tbody>
</table>
