---
name: prd-wizard
description: >
  Orchestrateur du workflow de discovery produit Mayday. À utiliser quand l'utilisateur
  veut "démarrer une discovery", "lancer le prd wizard", "lancer le discovery wizard", "où j'en suis dans ma
  discovery", "reprendre une discovery en cours", "c'est quoi les étapes", ou quand il
  décrit un problème client Mayday sans préciser de phase. Donne la carte des 6 phases,
  détecte l'avancement à partir des livrables déjà produits, et route vers la bonne
  phase.
metadata:
  version: "0.4.0"
  role: "orchestrateur"
---

# PRD Wizard - Orchestrateur

Lire `${CLAUDE_PLUGIN_ROOT}/shared/conventions.md` (langue française, pas de tiret
cadratin, dossier de travail, chaînage des phases).

## Rôle

Servir de point d'entrée et de boussole du workflow. Ne produit pas de livrable
lui-même : il oriente vers la phase adaptée et lance la skill de phase correspondante.

## Le workflow

| Phase | Skill | Livrable |
|---|---|---|
| 0 | `phase-0-contexte` | aucun (contexte en mémoire) |
| 1b (option) | `phase-1b-entretiens` | `guide-entretiens.md` |
| 1 | `phase-1-discovery` | `context.md` |
| 2 | `phase-2-problem` | `brainsta.md` |
| 3 | `phase-3-user-stories` | `user-stories.md` |
| 4 | `phase-4-solution` | `solution.md` |
| 5 | `phase-5-prd` | `prd.md` |
| 6 (option) | `phase-6-alignement` | `alignement.md` |

Chaque phase consomme le livrable de la précédente. La Phase 1b (entretiens de
discovery) est une boucle conditionnelle avant la Phase 1, à lancer quand l'hypothèse de
problème n'est pas validée et qu'il manque de matière terrain. La Phase 5 (PRD pour
l'équipe de build) est l'étape finale standard après la Phase 4. La Phase 6 (one-pager
CSM / Sales) est un livrable optionnel, dérivé du PRD, qui vient en dernier.

## Détecter l'avancement

Identifier le projet de discovery concerné (demander le sujet ou le slug si besoin),
puis regarder les fichiers présents dans `discovery/<slug>/` :

- Aucun dossier / aucun fichier : commencer en Phase 0.
- Pas de `context.md` et matière terrain insuffisante (hypothèse non validée, peu ou pas
  d'entretiens) : proposer la Phase 1b (préparer des entretiens) avant la Phase 1.
- `guide-entretiens.md` présent mais pas `context.md` : entretiens en cours ; une fois
  menés, lancer la Phase 1 pour analyser.
- `context.md` présent, pas `brainsta.md` : prochaine étape Phase 2.
- `brainsta.md` présent, pas `user-stories.md` : prochaine étape Phase 3.
- `user-stories.md` présent, pas `solution.md` : prochaine étape Phase 4.
- `solution.md` présent, pas `prd.md` : prochaine étape Phase 5 (PRD).
- `prd.md` présent : workflow bouclé ; proposer la Phase 6 (one-pager CSM / Sales) si
  pas encore produite.

Toujours confirmer l'état déduit avec l'utilisateur avant de router, et lui laisser la
possibilité de reprendre une phase antérieure ou de sauter la Phase 6.

## Router

Une fois la phase cible connue, lancer la skill de phase correspondante. Si plusieurs
projets de discovery coexistent, demander lequel avant de router.

Si l'utilisateur sait déjà quelle phase il veut, ne pas imposer le passage par
l'orchestrateur : router directement.
