---
title: "Aggiungere un nuovo insegnamento"
date: 2023-06-06T00:49:44+02:00
---

Aggiungere un nuovo insegnamento è facile, se sei già un membro di
CSUnibo:

1. su [template](https://github.com/csunibo/template), usa "Use this
   template"/"Create a new repository";
2. come nuovo nome, usa `la-convenzione-kebab-case`, e `ing-` come eventuale
   prefisso per un insegnamento legato a Ingegneria informatica;
3. come descrizione, usa una frase simile a "Una raccolta di risorse per
   l'insegnamento di Linguaggi di programmazione (04138) del Corso di Laurea in
   Informatica";
4. vai su "Create repository from template";
5. abilita GitHub Pages da "Settings" / "Pages" impostando "Source" come
   "GitHub Actions";
6. nella pagina principale del nuovo insegnamento su GitHub, clicca
   sull'ingranaggio a fianco di "About";
7. spunta "Use your GitHub Pages website" e togli le spunte da "Releases" e
   "Packages", poi aggiungi "Topics" a piacere e clicca su "Save changes";
8. aggiorna il README riempiendo ogni segnaposto;
9. aggiungi eventuali estensioni che vuoi compaiano sul sito risultante
   modificando `.github/workflows/build-and-deploy-yml`;
10. aggiorna [il profilo GitHub di CSUnibo](https://github.com/csunibo/.github)
    in modo appropriato;
11. aggiorna la [pagina principale di
    CSUnibo](https://github.com/csunibo/csunibo.github.io) in modo appropriato;
12. concedi i diritti "Mantain" ai gruppi interessati. Per esempio, per un
    insegnamento di Ingegneria informatica del secondo anno, andrebbero aggiunti
    i gruppo di Ingegneria informatica del secondo e terzo anno;
13. aggiungi il nuovo insegnamento a
    [`teachings.ts`](https://github.com/csunibo/dynamik/blob/main/src/lib/teachings.ts)
    affinché sia riconosciuto da Dynamik.
