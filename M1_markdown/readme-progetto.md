# Convertitore binario/decimale a 8 bit (MAX 2 VARIABILI DICHIARATE)

Questo programma fatto al terzo anno è un programma capace di prendere numerì in binario, quindi 8 bit tra 0 & 1
E facendo dei calcoli specifici, trovare il numero corrispondente all'imput ricevuto, Es: 01001011 = 75
E lo trova facendo dei semplici calcoli matematici quando utilizzando le moltiplicazioni in modo progressivo

| Requisito | Versione minima | Note |
|-|-|-|
| Java(JKD) | 17 | Serve il JDK per compilare con javac |
| Sistema operativo | qualsiasi | Windows, Linux o macOS |
| Librerie esterne | nessuna | Si usa solo java.util.Scanner, già incluso nel JDK |
| input | tastiera | Otto cifre, di 0 e 1 |

## Installazione

1. Installa un JDK 17 o superiore e verifica che il terminale lo veda:

```bash
java -version
javac -version
```

2. Crea una cartella di lavoro e spostati al suo interno. Su Windows, in PowerShell:

```powershell
mkdir Convertitore8Bit
cd Convertitore8Bit
```

Su Linux o macOS:

```bash
mkdir Convertitore8Bit
cd Convertitore8Bit
```

3. Salva il sorgente nella cartella con il nome `Convertitore8Bit.java`. La classe deve chiamarsi `Convertitore8Bit`.
4. Compila:

```bash
javac Convertitore8Bit.java
```

Se il comando non stampa errori, nella stessa cartella compare il file `Convertitore8Bit.class`.

## Uso

Dalla cartella in cui hai compilato, avvia il programma:

```bash
java Convertitore8Bit
```

Il programma non riceve argomenti e non legge un file. Chiede otto numeri interi, uno per riga. Il primo ha peso 1, poi 2, 4, 8, 16, 32, 64 e 128. Sono ammessi solo 0 e 1.

Esempio di input (cifra per riga, bit meno significativo per primo). Il valore binario letto al contrario, dal bit più significativo, è `00000101`, cioè 5 in decimale:

```text
1
0
1
0
0
0
0
0
```

Output atteso:

```text
Inserisci un valore binario mettendo i numeri 1 alla volta (solo 0 e 1)
Inserisci il bit di peso 1:
Inserisci il bit di peso 2:
Inserisci il bit di peso 4:
Inserisci il bit di peso 8:
Inserisci il bit di peso 16:
Inserisci il bit di peso 32:
Inserisci il bit di peso 64:
Inserisci il bit di peso 128:
Il Valore finale è: 5
```

Un secondo controllo: le cifre `1 1 1 1 1 1 1 1` devono dare `255`. La cifra `0` ripetuta otto volte deve dare `0`.

## Struttura del progetto

- `Convertitore8Bit.java`: sorgente. Dichiara due variabili `int` (`valore` e `convertimento`) e lo `Scanner` per la tastiera.
- `Convertitore8Bit.class`: file generato da `javac`, necessario per l'esecuzione.
- Nessun file di dati: input e output sono solo da console.

Vincolo dell'esercizio originale: al massimo due variabili `int` dichiarate. `valore` contiene la cifra appena letta; `convertimento` accumula la somma pesata.

## Autore e licenza

Autore: studente 4BI. Sostituire con nome e cognome prima della consegna.
Licenza: uso scolastico. Il programma si può copiare e modificare solo per le attività di laboratorio.
