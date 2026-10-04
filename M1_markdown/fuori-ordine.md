# Esercizio 11 — Che cosa stampa un notebook eseguito fuori ordine

### In quale ordine sono state realmente eseguite le quattro celle, e da che cosa si deduce?
1 - 2 - 3 - 4, dal fatto che la tre fa il calcolo di posti - iscritti e risulta 2 quindi i posti erano acnora 24 prima che il il 4 dicesse che erano 22

### Perché la cella [4] mostra 22 mentre la cella [3], eseguita prima di essa, ha calcolato con posti uguale a 24?
perchè la cella 2 ha creato la variabile posti con 24 allora la cella 3 ha fatto il calcolo 24 - 22, poi la cella
4 ha fatto il calcolo di 24 - 2

```text
Cella 2: nulla
Cella 4: Posti disponibili: 22
Cella 3 da errore
NameError                                 Traceback (most recent call last)
Cell In[3], line 1
----> 1 print(aula, "-", "liberi:", posti - iscritti)

NameError: name 'iscritti' is not defined
Cella 1 non viene eseguita
```

### Quale delle quattro celle produrrebbe un errore se il notebook venisse eseguito dall'alto in basso da un kernel appena avviato, e con quale messaggio esatto

- Sempre la cella 3: NameError: name 'aula' is not defined

