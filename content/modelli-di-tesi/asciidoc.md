---
title: "AsciiDoc"
date: 2023-03-18T13:13:34+01:00
---

> "Quando la tipografia è curata, le parole diventano immagini."
> Shawn Lukas

## Introduzione

[Questo modello per tesi](https://github.com/csunibo/asciidoc-thesis) fa suo di
[AsciiDoc](https://asciidoc.org), un formato di documenti più semplice e conciso
rispetto a LaTeX, ma che genera comunque contenuto ricco e accattivante. È
spesso usato per la documentazione tecnica. Scrivere la tua tesi in questo
formato ti permette di semplificarti la vita.

Puoi usare questo progetto come modello per una nuova _repository_ sul tuo
profilo: basta cliccare su "Use this template" in alto a destra.

## Prerequisiti

- [Ruby](https://www.ruby-lang.org/en/) `v2.7` o superiore;
- [Asciidoctor
  PDF](https://docs.asciidoctor.org/pdf-converter/latest/install/).

Si consiglia l'installazione di un'estensione code editor che supporti
**Asciidoc**.

## Come Iniziare?

Per compilare il file di esempio `tesi.adoc` utilizzare il comando:

```bash
asciidoctor-pdf --theme unibo.yml -a pdf-fontsdir=fonts tesi.adoc
```

## CI/CD

Cliccando su **Actions** in alto, potrai abilitare l'automatizzazione del
progetto:

- Per ogni **push** su una PR diretta verso `main`, verrà controllato
  che la tua tesi compili correttamente;
- Se avrai impostato **Github Actions** come
  `Settings` → `Pages` → `Build and depolyment` → `Source`, a ogni modifica su
  `main` la tua tesi verrà pubblicata su
  `https://<nome-utente>.github.io/<nome-repository>/tesi.pdf`.

Ricorda che se modifichi nome e percorso di `tesi.adoc` o `unibo.yml`, dovrai
modificare le tue **Actions** di conseguenza. Le estensioni non possono
essere modificate altrimenti _Asciidoctor_ non riconosce più i file.

## Personalizzazione

**Asciidoc** è il linguaggio che dovrai utilizzare, e puoi trovare qui la
[documentazione](https://docs.asciidoctor.org/asciidoc/latest/).

**Asciidoctor PDF** è il software che produrrà il `.pdf`, e puoi trovare qui la
[documentazione](https://docs.asciidoctor.org/pdf-converter/latest/) per
l'impaginazione.

> 🚸 Fai attenzione a modificare il file `unibo.yml`.
>
> L'indentazione è importantissima (2 spazi).
>
> **È vietato modificare l'estensione del file `unibo.yml`.**

### Files

### Sezioni

### Decoratori

### Liste

### Immagini

### Tabelle

### Math Mode

### Grafici

### Syntax Highlighting

### Bibliografia

### Numeri di Pagina

La sezione `footer` nel file `unibo.yml` controlla i [numeri di
pagina](https://docs.asciidoctor.org/pdf-converter/latest/theme/page-numbers/)
che sono pre-impostati al centro. Per impostarli sul lato esterno alla
rilegatura, sostituisci tutta la sezione `footer` con questa:

```yaml
footer:
height: 100
recto:
right:
content: "{page-number}"
verso:
left:
content: "{page-number}"
```

## Risorse Esterne

Il font `Computer Modern` è rilasciato in licenza SIL Open Font License.
