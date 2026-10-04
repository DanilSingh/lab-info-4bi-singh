# Architettura del programma Biblioteca

Il programma documentato è una gestione minima di prestiti, nel package `biblioteca`. Le classi sono `Biblioteca`, `Scaffale` e `Libro`. Non c'è ereditarietà: le classi sono indipendenti e si conoscono solo per composizione e associazione. I sorgenti corrispondenti sono `M1_java/biblioteca/Biblioteca.java`, `M1_java/biblioteca/Scaffale.java` e `M1_java/biblioteca/Libro.java`.

## Diagramma delle classi

```mermaid
classDiagram
    class Biblioteca {
        -String nome
        -Scaffale scaffale
        +Biblioteca(String nome)
        +getNome() String
        +acquisisci(Libro libro) void
        +presta(String isbn) String
    }
    class Scaffale {
        -String codice
        -ArrayList~Libro~ libri
        +Scaffale(String codice)
        +getCodice() String
        +aggiungi(Libro libro) void
        +cerca(String isbn) Libro
        +numeroLibri() int
    }
    class Libro {
        -String titolo
        -String isbn
        -boolean disponibile
        +Libro(String titolo, String isbn)
        +getTitolo() String
        +getIsbn() String
        +isDisponibile() boolean
        +setDisponibile(boolean disponibile) void
    }
    Biblioteca "1" *-- "1" Scaffale : possiede
    Scaffale "1" o-- "0..*" Libro : contiene
```

Il diagramma si legge partendo dai rettangoli: ogni classe elenca prima gli attributi, con `-` per la visibilità privata, poi i metodi pubblici, con `+`. `Biblioteca` tiene un solo `Scaffale`, creato nel costruttore: il rombo pieno e la molteplicità `1` a `1` indicano una composizione. `Scaffale` raccoglie da zero a molti `Libro`: il rombo vuoto e la molteplicità `0..*` indicano un'aggregazione. Non ci sono frecce di generalizzazione, perché nessuna classe estende un'altra.

## Diagramma di sequenza del prestito

L'operazione tipica è `Biblioteca.presta`. Lo scaffale cerca il libro confrontando l'ISBN; la biblioteca poi chiede se il libro è disponibile e decide il risultato.

```mermaid
sequenceDiagram
    participant B as Biblioteca
    participant S as Scaffale
    participant L as Libro
    B->>S: cerca(isbn)
    S->>L: getIsbn()
    L-->>S: isbn
    S-->>B: libro
    B->>L: isDisponibile()
    alt libro presente e disponibile
        B->>L: setDisponibile(false)
        B-->>B: restituisci prestito registrato
    else libro assente oppure gia in prestito
        B-->>B: restituisci prestito rifiutato
    end
```

Si legge dall'alto verso il basso, nel tempo. La freccia continua è una chiamata, la freccia tratteggiata è una risposta. I cinque scambi prima del blocco sono la ricerca e il controllo di disponibilità. Il blocco `alt` / `else` è la decisione già presente in `presta`: se `cerca` ha restituito un libro e `isDisponibile` è vero, la biblioteca lo segna come non disponibile e restituisce `prestito registrato`; altrimenti non modifica nulla e restituisce `prestito rifiutato`.
