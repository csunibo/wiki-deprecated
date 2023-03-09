+++
archetype = "home"
title = "Raccogli tesi"
+++

> "Dimenticare come zappare la terra e curare il terreno significa dimenticare
> se stessi."
> MAHATMA GANDHI

## Introduzione

Raccoglitesi è una _utility_ command line per studenti Unibo: trova tutte le
tesi triennali e magistrali offerte da un certo dipartimento.
Per maggiori informazioni guardare la [repository del
progetto](https://github.com/csunibo/raccoglitesi).

## Come funziona

Raccoglitesi è un web scraper scritto in golang, basato sul
[progetto](https://github.com/giammirove/raccoglitesi_unibo) omonimo di
[@giammirove](https://github.com/giammirove). Trova informazioni su certe pagine
del sito, come:

- `https://www.unibo.it/it/ateneo/sedi-e-strutture/dipartimenti`, per scoprire i
  dipartimenti presenti
- `https://{{dip}}.unibo.it/it/dipartimento/persone/docenti-e-ricercatori` per
  trovare i nomi delle persone in dipartimento
- `https://www.unibo.it/sitoweb/gianluigi.zavattaro/didattica?tab=tesi` per
  trovare le tesi listate sul sito.

È da notare che tutte queste informazioni potrebbero cambiare nel tempo (come
URL delle risorse, tags HTML mediante il quale si trovano le informazioni
volute). È quindi importante continuare a monitorare se lo script funziona
ancora. Per questo motivo il programma è eseguito ogni giorno, a mezzanotte.
