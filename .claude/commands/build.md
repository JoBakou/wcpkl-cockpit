---
description: Lit specs/projet.md et construit exactement ce qui est écrit, puis liste les besoins couverts
---

Tu es en mode **construction**. Tu implémentes ce qui a été spécifié dans `specs/projet.md` — **exactement ce qui est écrit, rien de plus**.

## Étape 1 — Lire le plan

Lis `specs/projet.md`.

- Si le fichier n'existe pas, **arrête-toi** : explique à l'utilisateur qu'il n'y a pas de plan et propose de lancer `/spec` d'abord. Ne construis rien.
- Lis l'intégralité du fichier : Objectif, Besoins exacts, Hors périmètre, Cas limites, Définition de « terminé ».
- Si une partie du plan est ambiguë ou contradictoire au point de bloquer l'implémentation, pose une question avant de coder plutôt que de deviner. Pour les détails mineurs, choisis l'option la plus simple et la plus conforme à l'esprit du plan, et signale-le.

## Étape 2 — Construire

Implémente le plan fidèlement.

- Construis **uniquement** ce que demandent les « Besoins exacts ». Ne rajoute pas de fonctionnalités, d'options, d'abstractions ou de « tant qu'on y est » qui ne sont pas dans le plan.
- Respecte explicitement la section **Hors périmètre** : n'y touche pas.
- Traite chaque **Cas limite** listé comme le plan le décrit.
- Vise la **Définition de « terminé »** : ton travail n'est terminé que lorsque tous ces critères sont vrais et vérifiables.
- Suis les conventions du code existant (style, nommage, structure, outils). Quand des tests ou un linter existent, fais-les passer.

## Étape 3 — Couverture des besoins

À la fin, liste les **Besoins exacts** du plan et, pour chacun, son état de couverture. Reprends la numérotation du plan :

```
## Couverture du plan
1. <besoin> — ✅ couvert (où / comment)
2. <besoin> — ✅ couvert (où / comment)
3. <besoin> — ⚠️ partiel / ❌ non couvert (raison)
```

- Sois honnête : si un besoin n'est pas couvert, ou seulement en partie, dis-le clairement avec la raison, sans le présenter comme fait.
- Indique aussi où chaque besoin a été traité (fichiers / fonctions clés) pour que l'utilisateur puisse vérifier.
- Termine en rappelant l'état vis-à-vis de la **Définition de « terminé »** : tout est-il satisfait, ou reste-t-il des points ouverts ?
