# Discovery Wizard

Plugin produit qui accompagne un PM de Mayday depuis la découverte d'un problème client
jusqu'à la définition d'une solution, phase par phase. Inspiré des frameworks type BMAD,
mais arrêté avant le développement. On ne conçoit pas un produit entier : on répond à UN
problème client précis.

## Installation (via cette marketplace)

Ce dépôt est à la fois le plugin et sa marketplace. Pour l'installer, un collègue ajoute
la marketplace une fois puis installe le plugin, depuis Cowork ou Claude Code :

```
/plugin marketplace add THEO_GITHUB_USER/discovery-wizard
/plugin install discovery-wizard@mayday-product
```

Remplacer `THEO_GITHUB_USER` par le compte (ou l'organisation) GitHub qui héberge le
dépôt. Les mises à jour poussées ici se propagent via `/plugin marketplace update`.

## Point d'entrée

La skill `discovery-wizard` est l'orchestrateur : elle donne la carte des phases, déduit
où tu en es à partir des livrables déjà produits, et route vers la bonne phase. Idéale
pour démarrer ou reprendre une discovery en cours (« où j'en suis ? »). Tu peux aussi
lancer directement une phase si tu sais laquelle.

## Les phases

| Phase | Skill | Ce qu'elle fait | Livrable |
|---|---|---|---|
| 0 | `phase-0-contexte` | Récupère et cadre le contexte du problème | aucun (contexte en mémoire) |
| 1 | `phase-1-discovery` | Analyse entretiens + analytics, sort les discovery statements | `context.md` |
| 2 | `phase-2-problem` | Brainstorming et choix du problem statement (pas d'UX) | `brainsta.md` |
| 3 | `phase-3-user-stories` | Décline le problème en user stories priorisées | `user-stories.md` |
| 4 | `phase-4-solution` | Idéation et définition de la solution (design) | `solution.md` |
| 5 | `phase-5-alignement` | One-pager d'alignement CSM / Sales (optionnel) | `alignement.md` |

Chaque phase consomme le livrable de la précédente (chaînage type BMAD). La Phase 5 est
optionnelle. Les fichiers vivent dans `discovery/<slug-du-projet>/`.

## Comment l'utiliser

Passer par l'orchestrateur, ou lancer les phases dans l'ordre. Exemples de déclencheurs :

- « Lance le discovery wizard » / « où j'en suis dans ma discovery ? » → orchestrateur
- « Je démarre une discovery sur la recherche de connaissance des agents » → Phase 0
- « Lance la phase 1 » / « analyse les entretiens » → Phase 1
- « Définis le problem statement » → Phase 2
- « Écris les user stories » → Phase 3
- « Brainstorme la solution » → Phase 4
- « Produis le one-pager pour les CSM et le sales » → Phase 5 (optionnelle)

Chaque phase se termine par un « handoff » qui propose de lancer la suivante.

## Connecteurs utilisés

| Usage | Connecteur | Requis ? |
|---|---|---|
| Entretiens de discovery | Notion (base dédiée) | Recommandé (source principale) |
| Transcripts de meetings | Granola | Optionnel |
| Analytics produit | Amplitude EU | Optionnel (Phase 1) |
| Restitution des livrables | Fichiers `.md` + Notion | Fichiers toujours, Notion si voulu |
| User stories → issues | Linear | Optionnel (Phase 3) |

Si un connecteur n'est pas autorisé côté réglages de connecteurs, le plugin le signale
et continue avec les notes / contenus fournis manuellement. Il ne bloque jamais sur un
connecteur manquant. Détail et réutilisation hors Mayday : voir `CONNECTORS.md`.

## Brainstorming (adapté de BMAD)

Les phases de brainstorming (Phase 2 problème et Phase 4 solution) s'appuient sur la
méthode du module BMAD "Creative Intelligence Suite" (coach "Carson") : posture "Yes,
and", catalogue de techniques par catégorie, 4 modes de sélection (choix utilisateur,
recommandé, aléatoire, progressif) et une étape de capture / tri. Détail dans
`shared/brainstorming-bmad.md`.

## Conventions

- Tout en français, sans tiret cadratin (em dash).
- On reste au niveau du problème jusqu'en Phase 3. La solution ne se travaille qu'en
  Phase 4. Le workflow s'arrête avant le développement.
- Règles détaillées : `shared/conventions.md`.

## Structure

```
discovery-wizard/
├── .claude-plugin/plugin.json
├── README.md
├── CONNECTORS.md
├── shared/conventions.md
├── shared/brainstorming-bmad.md
└── skills/
    ├── discovery-wizard/SKILL.md (orchestrateur)
    ├── phase-0-contexte/SKILL.md
    ├── phase-1-discovery/SKILL.md (+ references/discovery-guide.md)
    ├── phase-2-problem/SKILL.md (+ references/problem-guide.md)
    ├── phase-3-user-stories/SKILL.md (+ references/stories-guide.md)
    ├── phase-4-solution/SKILL.md (+ references/solution-guide.md)
    └── phase-5-alignement/SKILL.md (+ references/onepager-guide.md)
```
