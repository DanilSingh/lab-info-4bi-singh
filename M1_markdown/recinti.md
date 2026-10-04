# Guida ai recinti annidati

Questa guida mostra come far vedere a un compagno un blocco di codice *dentro* un altro blocco di codice. In Markdown un recinto si apre e si chiude con una riga di backtick (`` ` ``) oppure di tilde (`~`). La regola che conta è una sola: il recinto esterno deve usare **più** caratteri di qualunque riga di recinto che compare al suo interno. Se il recinto esterno è troppo corto, il parser lo chiude in anticipo e tutto il resto del documento viene letto come codice.

## Primo esempio: un blocco Java normale

Qui sotto il lettore vede un blocco di codice Java vero e proprio. Il recinto è di tre backtick, con l'etichetta `java`. Nell'anteprima (e nell'HTML di Pandoc) compare il sorgente formattato come codice, non le righe di recinto.

```java
public class Ciao {
    public static void main(String[] args) {
        System.out.println("Ciao");
    }
}
```

## Secondo esempio: lo stesso blocco mostrato come sorgente

Qui il lettore non vede il programma eseguito come blocco Java, ma il *testo Markdown* dell'esempio precedente, recinti compresi. Per ottenerlo il recinto esterno usa quattro backtick e l'etichetta `markdown`. Dentro ci sono ancora tre backtick: siccome quattro è maggiore di tre, quei tre backtick restano testo e non chiudono il recinto esterno.

````markdown
```java
public class Ciao {
    public static void main(String[] args) {
        System.out.println("Ciao");
    }
}
```
````

## Terzo esempio: un livello in più

Qui il lettore vede il sorgente del secondo esempio, quindi anche il recinto da quattro backtick. Il recinto più esterno ne usa cinque: è più lungo sia dei quattro sia dei tre che stanno dentro, e per questo nessuno dei due lo chiude prima del tempo. Il contenuto è marcato come `text`, così si legge come testo sorgente e non viene reinterpretato.

`````text
````markdown
```java
public class Ciao {
    public static void main(String[] args) {
        System.out.println("Ciao");
    }
}
```
````
`````

Questo ultimo paragrafo è testo normale. Se i tre recinti sopra sono chiusi con la stessa lunghezza con cui sono stati aperti, l'anteprima lo mostra come prosa e non come codice. La stessa struttura si ottiene convertendo il file con Pandoc: tre blocchi di codice distinti e, dopo l'ultimo, un paragrafo.
