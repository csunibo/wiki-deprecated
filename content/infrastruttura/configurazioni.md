---
title: "Configurazioni"
date: 2023-04-29T15:13:05+02:00
draft: true
---

Talvolta, gli stessi valori di configurazione possono essere usati più volte in
progetti diversi di CSUnibo. Per esempio, le espressioni regolari che esprimono
le convenzioni di nomenclatura sono usate sia dai processi di CI/CD che
controllano esse siano rispettate sia da `csurename`, che rinomina le risorse
affinché esse passino in seguito questi controlli.

In un'ottica di riuso del codice, queste configurazioni sono centralizzate
su [csunibo/config](https://github.com/csunibo/config). Il formato scelto è
JSON. Ogni volta che vengono aggiunte modifiche a `main` o ci sono novità su una
PR verso `main` stesso, un controllo sintattico viene automaticamente
effettuato su ogni file JSON.

## Nomenclatura

Le espressioni regolari che descrivono le regole di nomenclatura da adottare per
i nomi delle risorse sono memorizzate in `config/naming.json`.
