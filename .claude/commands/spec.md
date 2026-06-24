---
description: Interview pas à pas pour clarifier un besoin, puis écrit un plan précis dans specs/projet.md
---

Tu es en mode **spécification**. Ton but est de comprendre exactement ce que veut l'utilisateur **avant** d'écrire la moindre ligne de code, puis de consigner cette compréhension dans un plan écrit.

## Règle d'or

**Ne construis rien, ne modifie aucun fichier de code, ne propose aucune implémentation tant que le besoin n'est pas clair et confirmé.** La seule chose que tu écris au terme de cette commande est le fichier `specs/projet.md`.

## Étape 1 — Interview, une question à la fois

Interviewe l'utilisateur pour cerner son besoin réel.

- Pose **une seule question à la fois**. Attends la réponse avant la suivante.
- Chaque question doit être courte, concrète et découler des réponses précédentes (pas un questionnaire générique récité d'un bloc).
- Creuse jusqu'à comprendre vraiment : l'objectif sous-jacent (le « pourquoi »), les utilisateurs, les contraintes, les données, les cas limites, ce qui est explicitement hors périmètre.
- Reformule au fil de l'eau pour vérifier ta compréhension : « Si je comprends bien… ».
- Si l'utilisateur dit « je ne sais pas » ou reste vague, propose des options concrètes ou des valeurs par défaut raisonnables pour l'aider à trancher.
- Continue jusqu'à ce que tu puisses décrire le besoin sans trou ni ambiguïté. Ne t'arrête pas trop tôt : mieux vaut une question de plus qu'une hypothèse non vérifiée.

Quand tu estimes avoir assez d'informations, **annonce-le** et fais une dernière synthèse orale que l'utilisateur peut corriger avant que tu n'écrives le fichier.

Si l'argument `$ARGUMENTS` contient déjà une description, sers-t'en comme point de départ de l'interview — mais interviewe quand même pour combler les trous.

## Étape 2 — Écrire le plan

Une fois le besoin confirmé par l'utilisateur, crée (ou mets à jour) le fichier `specs/projet.md`. Crée le dossier `specs/` s'il n'existe pas.

Le fichier doit contenir, dans cet ordre et avec ces titres :

```markdown
# <Titre du projet / de la fonctionnalité>

## Objectif
Pourquoi on fait ça, en une à trois phrases. Le problème résolu et pour qui.

## Besoins exacts
Liste précise et numérotée de ce qui doit être fait. Chaque point est concret
et vérifiable — pas de « le système doit être robuste », mais « X fait Y quand Z ».

## Hors périmètre
Ce qu'on ne fait **pas** dans ce travail, pour éviter les malentendus.

## Cas limites
Les situations délicates et la manière de les traiter : entrées vides ou
invalides, erreurs, concurrence, limites de volume, états inattendus, etc.

## Définition de « terminé »
Critères d'acceptation observables. Le travail est terminé quand tous ces
points sont vrais et vérifiables (tests, comportement attendu, etc.).

## Questions ouvertes
Points restés en suspens, le cas échéant. Vide si tout est tranché.
```

Adapte le contenu au besoin réel : sois précis, concret et honnête sur ce qui reste incertain. N'invente pas de détails que l'utilisateur n'a pas confirmés — mets-les plutôt en « Questions ouvertes ».

## Étape 3 — Clôturer

Après avoir écrit `specs/projet.md` :

- Indique à l'utilisateur que le plan est prêt et où il se trouve.
- Rappelle que **rien n'a été construit** et propose de passer à l'implémentation dans un prochain temps, une fois qu'il a relu et validé le plan.
