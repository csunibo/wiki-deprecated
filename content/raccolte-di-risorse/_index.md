+++
archetype = "chapter"
title = "Raccolte di risorse"
weight = 2
+++

Per ciascun insegnamento, raccogliamo in modo organizzato appunti, testi e
soluzioni di esercizi e prove di esame, libri, dispense, lucidi e molto altro.

Quando contribuisci con le tue risorse, ricorda che:

- i tuoi file devono rispettare le convenzioni di nomenclatura in `README.md`,
  o i controlli automatici falliranno;
- eventuali tuoi file `.tex` o `.md` devono compilare correttamente nei formati
  supportati da CSUnibo;
- se hai i sorgenti `.tex`, `.md`, `.doc(x)` o `.ppt(x)`, dovresti preferirli a
  caricare i loro corrispettivi in PDF, cosicchè tutti possano lavorarvi più
  facilmente;
- se stai aggiungendo un file con una estensione nuova, e vuoi che tale file non
  venga nascosto sul sito autogenerato, dovresti aggiungerla a `REGEX_INCLUDE`
  in `.github/workflows/build-and-deploy.yml`.
