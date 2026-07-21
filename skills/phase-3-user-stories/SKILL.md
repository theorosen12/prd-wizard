---
name: phase-3-user-stories
description: >
  Phase 3 du workflow de discovery produit Mayday. À utiliser quand l'utilisateur veut
  "lancer la phase 3", "écrire les user stories", "décliner le problème en besoins
  utilisateurs", ou après avoir produit `brainsta.md` en Phase 2. Traduit le problem
  statement en user stories priorisées (avec critères d'acceptation), sans encore
  concevoir la solution. Produit `user-stories.md` et peut pousser les stories dans
  Linear.
metadata:
  version: "0.1.0"
  phase: "3"
---

# Phase 3 — User stories

Lire d'abord `${CLAUDE_PLUGIN_ROOT}/shared/conventions.md`. Voir
`${CLAUDE_PLUGIN_ROOT}/skills/phase-3-user-stories/references/stories-guide.md` pour
le format des stories, les critères d'acceptation et le gabarit de `user-stories.md`.

## But de la phase

Traduire le problem statement en **user stories** : des besoins utilisateurs formulés
du point de vue de l'utilisateur, priorisés, avec critères d'acceptation. On décrit ce
que l'utilisateur doit pouvoir faire et pourquoi, **pas encore comment l'interface le
fait** (ça, c'est la Phase 4).

Livrable : `discovery/<slug>/user-stories.md`. Option : création des issues dans Linear.

## Pré-requis

Lire `discovery/<slug>/brainsta.md` (Phase 2) et, pour le contexte,
`discovery/<slug>/context.md` (Phase 1). Si `brainsta.md` manque, proposer de lancer la
Phase 2 d'abord.

## Déroulé

### 1. Dériver les stories du problème

- Partir du problem statement et des personas.
- Identifier les capacités dont l'utilisateur a besoin pour que le problème soit résolu.
- Écrire chaque story au format : « En tant que [persona], je veux [capacité] afin de
  [bénéfice]. »
- Rester orienté besoin / résultat, pas solution technique ni écran précis.

### 2. Prioriser

- Classer les stories (ex : MoSCoW, ou simplement must / should / could).
- Identifier la ou les stories cœur qui adressent directement le problem statement.
- Marquer les stories secondaires ou hors scope.

### 3. Ajouter les critères d'acceptation

Pour chaque story retenue, écrire des critères d'acceptation vérifiables (format
Given / When / Then ou liste de conditions). Ils décrivent le résultat attendu du point
de vue utilisateur, pas l'implémentation.

### 4. Écrire `user-stories.md`

Suivre le gabarit du fichier de référence. Écrire dans
`discovery/<slug>/user-stories.md`.

### 5. Option Linear

Proposer de créer les stories comme issues Linear (une issue par story, avec titre,
description, critères d'acceptation, label). Demander l'équipe / projet cible avant de
créer. Ne créer les issues qu'après validation explicite. Si Linear n'est pas
autorisé, le signaler et rester sur le fichier `.md`. Si Notion est destination,
proposer aussi la page Notion.

## Handoff

Terminer par : le nombre de stories et la story cœur + « User stories prêtes. Prochaine
étape : Phase 4 (Brainsto solution), où on ouvre enfin le "comment" et le design. On y
va ? »
