---
title: "Controlli automatici"
date: 2023-04-05T12:21:04+02:00
---

Quando ci sono nuove modifiche su una PR o sulla _branch_ `main`, vengono
eseguiti alcuni controlli automatici.

È bene che tutti i controlli passino prima che la PR venga accettata. Le
moderatrici e i moderatori ti aiuteranno lungo tutto il percorso.

## Nomenclatura

In generale, è sufficiente usare il `kebab-case` (e cioè lettere minuscole e
trattini alti) sia per i nomi delle cartelle che dei file.

Seguono i casi dei controlli più stringenti. Se una sottocartella li passa, i
contenuti a essa appartenenti non vengono controllati: questo è utile per le
risorse distribuite "impacchettate" assieme dal corpo docente.

### `dispense/` e `lucidi/`

Le regole in
[enumerazione.synta](https://github.com/csunibo/config/blob/main/enumerazione.synta)
devono essere rispettate.

### `prove/`

Le regole in
[prove.synta](https://github.com/csunibo/config/blob/main/prove.synta)
devono essere rispettate.

## Compilazione

Eventuali file "sorgenti" `.tex`/`.md`/`.doc(x)`/`.odt(x)` e simili devono
compilare correttamente nei formati supportati da CSUnibo.
