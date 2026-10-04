# Relazione di laboratorio — Tempi di un ordinamento

Relazione sull'esercitazione in cui si misura, in millisecondi, il tempo di un algoritmo di ordinamento su array di dimensione crescente.

## Indice

1. [Obiettivo](#obiettivo)
2. [Materiale](#materiale)
3. [Procedimento](#procedimento)
4. [Risultati](#risultati)
5. [Conclusioni](#conclusioni)

<a id="obiettivo"></a>
## Obiettivo

Verificare come cresce il tempo di esecuzione di un ordinamento al crescere della dimensione dell'array. Le prove usano quattro taglie: 100, 1000, 10000 e 100000 elementi. Il tempo è espresso in millisecondi e serve a confrontare le prove, non a giudicare il computer.

<a id="materiale"></a>
## Materiale

- Computer del laboratorio con JDK 17 installato.
- Un programma Java che riempie un array di interi, lo ordina e misura il tempo.<sup><a id="nota-1-ref" href="#nota-1">1</a></sup>
- Algoritmo usato: ordinamento a bolle (bubble sort), scritto in classe senza librerie esterne.
- Dati di ingresso: array di `int` con valori casuali fra 0 e 99999, una prova per ogni dimensione.

<a id="procedimento"></a>
## Procedimento

1. Si crea un array della dimensione richiesta e lo si riempie con numeri casuali.
2. Si legge il tempo con `System.nanoTime()` subito prima dell'ordinamento e subito dopo.
3. Si converte la differenza in millisecondi e la si annota.
4. Si controlla che l'array sia ordinato in senso non decrescente.
5. Si ripete il procedimento per 100, 1000, 10000 e 100000 elementi, usando la stessa macchina e chiudendo gli altri programmi pesanti.

Frammento usato per la misura:

```java
long inizio = System.nanoTime();
ordinaBolle(dati);
long fine = System.nanoTime();
double millisecondi = (fine - inizio) / 1_000_000.0;
System.out.println(dati.length + " -> " + millisecondi);
```

Il metodo `ordinaBolle` scorre l'array più volte e scambia due elementi vicini se sono nell'ordine sbagliato. Non sono state usate `Arrays.sort` né altre librerie: il tempo riguarda solo il codice scritto in laboratorio.<sup><a id="nota-2-ref" href="#nota-2">2</a></sup>

<a id="risultati"></a>
## Risultati

Tempi rilevati nella prova. La colonna "rapporto" indica di quante volte il tempo è cresciuto rispetto alla riga precedente.

| Dimensione | Tempo (ms) | Rapporto sul precedente | Array ordinato |
|------------|------------|-------------------------|----------------|
| 100 | 0,4 | — | sì |
| 1000 | 18 | circa 45 | sì |
| 10000 | 1650 | circa 92 | sì |
| 100000 | 171000 | circa 104 | sì |

Da 1000 a 10000 elementi la dimensione diventa 10 volte più grande e il tempo circa 90 volte più grande. Da 10000 a 100000 il tempo diventa di nuovo circa 100 volte più grande. Il passaggio a 100000 elementi porta la prova oltre i due minuti.

<a id="conclusioni"></a>
## Conclusioni

Il bubble sort completa tutte e quattro le prove e restituisce array ordinati, quindi il procedimento è corretto sul risultato. Il tempo però non cresce in modo proporzionale alla dimensione: a ogni aumento di 10 volte degli elementi, il tempo aumenta di circa 100 volte. Per questo, su un array da 100000 elementi, l'algoritmo scelto in laboratorio diventa lento. Per dati più grandi conviene un algoritmo con meno confronti, da misurare con lo stesso metodo nella prossima esercitazione.

<a id="note"></a>
## Note

<a id="nota-1"></a>
1. I valori casuali sono prodotti con `java.util.Random`. Due esecuzioni diverse non danno gli stessi numeri, quindi i millisecondi possono variare di poco; l'ordine di grandezza resta lo stesso. <a href="#nota-1-ref">↩</a>

<a id="nota-2"></a>
2. Il tempo include solo la chiamata a `ordinaBolle`. Il riempimento dell'array e la stampa non entrano nella misura. La prima prova da 100 elementi è la più sensibile a questo scarto, perché dura meno di un millisecondo. <a href="#nota-2-ref">↩</a>
