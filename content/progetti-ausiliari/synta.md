---
title: "Synta"
date: 2023-10-06T12:00:05+02:00
---

## Introduzione

Synta [^1] è uno strumento a linea di comando per svolgere svariate operazioni
sul formato di definizione regolare usato internamente a
[CSUnibo](https://github.com/csunibo) per vincolare le nomenclature dei file.
È disponibile presso [csunibo/synta](https://github.com/csunibo/synta). Con
Synta è possibile:

- verificare la validità di un file `.synta`;
- convertire un file `.synta` in una espressione regolare;
- convertire un file `.synta` in un file JSON che ne descrive i contenuti.

## Definizione del linguaggio

Il linguaggio Synta è definito dalla seguente BNF:

```bnf
<upperletter> ::= "A" | "B" | "C" | "D" | "E" | "F" | "G" | "H" | "I" | "J" |
                  "K" | "L" | "M" | "N" | "O" | "P" | "Q" | "R" | "S" | "T" |
                  "U" | "V" | "W" | "X" | "Y" | "Z"
<lowerletter> ::= "a" | "b" | "c" | "d" | "e" | "f" | "g" | "h" | "i" | "j" |
                  "k" | "l" | "m" | "n" | "o" | "p" | "q" | "r" | "s" | "t" |
                  "u" | "v" | "w" | "x" | "y" | "z"
<digit>       ::= "0" | "1" | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"
<alphanum>    ::= <lowerletter> | <upperletter> | <digit>
<char>        ::= <alphanum> | ":" | ";" | "," | "." | "-" | "_"
<word>        ::= <char> <word> | <char>
<text>        ::= <word> " " <text> | <word>

<comment>     ::= "; " <text> "\n" | ";" <text> "\n"
<id>          ::= <lowerletter> <id> | <lowerletter>
<def>         ::= <id> " = " <regexp> "\n"
<commdef>     ::= <comment> <commdef> | <comment> <def>
<commdefs>    ::= <commdef> <commdefs> | <commdef>

<segment>     ::= "-" <id> | "(-" <id> ")?"
<join>        ::= <segment> <join> | <segment>
<main>        ::= "> " <id> <join> "." <id> "\n"

<language>    ::= <commdefs> <main>
```

dove `<regexp>` è una valida sintassi che esprime una espressione regolare.
La sintassi regexp usata è quella di Go, ma per i nostri fini, dovrebbe essere
anche compatibile con quella di Javascript e Rust.

### Esempi

```
; La tipologia della prova
tipo = scritto|orale
; Una data del tipo yyyy-mm-dd
data = \d{4}-\d{2}-\d{2}
; La fila e' un numero
fila = \d
; Una qualunque parola alfanumerica
extra = (\w|\d)+
; Estensione del file. Possibili valori:
; - txt, tex, md, pdf, doc, docx
ext = txt|tex|md|pdf|doc|docx

> tipo-data(-fila)?-extra.ext
```

## Implementazione del parser

Per il parse dell'intero file, usiamo un parser semplicistico manipolando la
stringa, in quanto l'analisi delle definizioni e dei commenti è piuttosto facile.
Per il parse della linea finale, che contiene la concatenazione di tutte le
regole, usiamo invece un piccolo FSA con side-effect come segue:

![FSA per il riconoscimento del nome del
file](https://github.com/csunibo/synta/blob/main/automata.jpg?raw=true)

I side-effect sono:
- `concat`: concatena il simbolo letto ad `id`
- `list`: inserisce `id` nella lista degli identificatori, e imposta `id = ""`

### Sviluppo

Ecco una lista dei file nella repository e il loro scopo:

```
├── data.go        # Strutture dati per il parser
├── parser.go      # Logica di parsing e FSA
├── parser_test.go # Unit test per il parser
```

[^1]: **Origine del nome**: è uno dei top-10 nomi suggeriti da chat gpt. Abbiamo
usato il prompt: "suggest me a short name for a tiny parser command line
utility. the name must not be made up of two or more words"
