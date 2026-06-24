---
description: Compare ce qui a été construit à specs/projet.md, point par point, et ne valide que si tout est couvert
---

Tu es en mode **revue**. Tu vérifies que ce qui a été construit correspond **exactement** à `specs/projet.md`, besoin par besoin. Tu ne valides que lorsque le plan entier est couvert.

## Étape 1 — Lire le plan et le code

- Lis `specs/projet.md` en entier.
  - Si le fichier n'existe pas, **arrête-toi** : il n'y a pas de référence à comparer. Renvoie l'utilisateur vers `/spec`.
- Lis ce qui a été effectivement construit (le code, les fichiers concernés, les tests).
- Quand c'est possible, vérifie le comportement réel — exécute les tests ou le code — au lieu de te fier à la seule lecture.

## Étape 2 — Comparer point par point

Passe en revue chaque **Besoin exact** du plan, dans l'ordre, et confronte-le à ce qui existe :

- Le besoin est-il implémenté, et **comme le plan le décrit** (pas une variante approximative) ?
- Chaque **Cas limite** listé est-il géré ?
- Le **Hors périmètre** a-t-il été respecté (rien construit en trop) ?
- La **Définition de « terminé »** est-elle satisfaite, critère par critère ?

Pour chaque problème trouvé, écris une entrée qui **nomme le besoin concerné** (sa numérotation dans le plan) :

```
## Écarts au plan
- Besoin 2 « <intitulé> » — ❌ MANQUE : <ce qui n'est pas fait>
- Besoin 4 « <intitulé> » — 🐞 BUG : <comportement observé vs attendu> (fichier:ligne)
- Cas limite « <intitulé> » — ❌ non géré : <détail>
```

Sois précis et vérifiable : pointe le fichier/la ligne et explique l'écart entre l'attendu (le plan) et le constaté.

## Étape 3 — Corriger et renvoyer à /build

- Pour chaque écart, **écris la correction**.
- Ne corrige que ce qui sert le plan — pas d'ajout hors périmètre, même tentant.
- Les corrections doivent passer par le même processus de construction que `/build` : applique-les en suivant les conventions du code, fais passer tests et linter, et garde la traçabilité besoin → correction.
- Après correction, **recommence la comparaison** (étape 2) pour confirmer que l'écart est résorbé et qu'aucun nouveau n'est apparu. Itère `revue → corrige → re-revue` jusqu'à ce qu'il ne reste aucun écart.

## Étape 4 — Verdict

Conclus par un verdict explicite, jamais complaisant :

- **✅ VALIDÉ** — uniquement si **tous** les besoins, cas limites et critères de « terminé » sont couverts et vérifiés. Liste-les pour le prouver.
- **❌ NON VALIDÉ** — s'il reste le moindre écart. Liste ce qui manque, en nommant chaque besoin concerné, et indique l'étape suivante.

Ne valide jamais un plan partiellement couvert. En cas de doute sur un besoin, considère-le non couvert et signale-le.
