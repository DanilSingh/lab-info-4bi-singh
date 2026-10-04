| Costrutto | Markdown originale | CommonMark | GitHub Flavored Markdown |
| :--- | :---: | :---: | :---: |
| Blocchi di codice recintati | No: solo codice indentato di 4 spazi | Sì, con tripli apici | Sì, anche con il nome del linguaggio |
| Tabelle | No | No, non fanno parte della specifica base | Sì |
| Caselle di spunta | No | No | Sì, con `- [ ]` e `- [x]` |
| Testo barrato | No | No | Sì, con `~~testo~~` |
| Collegamenti automatici | Solo fra parentesi angolari | Solo fra parentesi angolari | Sì, anche un URL scritto per esteso |
| Note a piè di pagina | No | No | Sì |

## Esempi di GitHub Flavored Markdown

- [x] Creare il file `varianti.md`
- [x] Inserire la tabella con l’allineamento richiesto
- [ ] Controllare l’anteprima in Visual Studio Code
- [ ] Fare il push sul repository
- [ ] Verificare il rendering su GitHub
- [ ] Annotare le differenze nel paragrafo finale

La sintassi delle tabelle della versione 2018 è ~~superata~~ e non va usata per le consegne.

Indirizzo scritto per esteso: https://github.github.com/gfm/

## Quale variante usare per le consegne

Per le consegne del corso conviene usare GitHub Flavored Markdown, perché i file vengono letti sia nell’anteprima di Visual Studio Code sia nella pagina resa da GitHub, e questa variante include tabelle, caselle di spunta, testo barrato e collegamenti automatici.
CommonMark è più rigoroso e portabile, ma non definisce da solo le estensioni usate in questo file, quindi una parte del documento perderebbe il formato previsto.
Se questo stesso file viene aperto con uno strumento che implementa solo CommonMark, la tabella resta testo con pipe, le caselle non diventano quadratini, il testo barrato resta con le tilde e l’URL scritto per esteso può non diventare cliccabile.
Nell’anteprima di Visual Studio Code, invece, tabelle, caselle e testo barrato di solito compaiono già formattati, in modo molto vicino a GitHub; eventuali differenze vanno scritte qui dopo il confronto.
Le tabelle nell'anteprima di VSCode sono solo delle linee che dividono le informazionioni senza alcuna linea che divide le colonne mentre GitHub Flavored Markdown creadelle proprie tabelle con divisione a blocchi.
I quadrati di spunta su VSCode preview, i primi 2 contengono le 2 X e sono ad'elenco puntato mentre su GitHub sono solo cubi di spunta con i primi 2 anch'essi vuoti come
il resto