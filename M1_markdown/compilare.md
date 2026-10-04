# Compilare ed eseguire un programma Java

Dopo aver clonato il repository, segui questi passi per compilare i sorgenti in `src/` nella cartella `bin/` ed eseguire la classe `MediaVoti`.

1. Apri un terminale e spostati nella cartella del progetto appena clonato con il comando `cd`.
2. Controlla che il JDK sia installato, verificando i comandi `java` e `javac`.
   - Esegui `java -version` per controllare il runtime.
   - Esegui `javac -version` per controllare il compilatore.
3. Crea la cartella di output `bin/` se non esiste già, usando l'opzione `-p` di `mkdir`.
4. Compila i file `.java` presenti in `src/` e scrivi i file `.class` in `bin/` con l'opzione `-d`.

```bash
mkdir -p bin
javac -d bin src/*.java