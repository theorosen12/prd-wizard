# Conventions partagées — Mayday Product Discovery

Ce fichier est référencé par toutes les phases. Le respecter à chaque phase.

## Objectif du plugin

Accompagner un PM de Mayday depuis la découverte d'un problème client jusqu'à la
définition d'une solution. On ne conçoit pas un produit entier : on répond à UN
problème précis rencontré par les clients de Mayday. Le workflow s'arrête avant le
développement (inspiration BMAD, mais on ne code pas ici).

## Langue et style

- Toujours écrire en français (livrables, questions, restitutions).
- Ne jamais utiliser de tiret cadratin (em dash). Utiliser une virgule, deux points,
  ou des parenthèses.
- Ton : direct, concret, orienté produit. Pas de blabla.

## Dossier de travail et fichiers

Toute la discovery d'un problème vit dans un dossier dédié :

```
discovery/<slug-du-projet>/
├── context.md          (Phase 1)
├── brainsta.md         (Phase 2)
├── user-stories.md     (Phase 3)
├── solution.md         (Phase 4)
├── alignement.md       (Phase 5, optionnelle)
└── prd.md              (Phase 6, optionnelle)
```

- `<slug-du-projet>` : nom court en kebab-case dérivé du problème
  (ex : `recherche-connaissance-agents`).
- La Phase 0 ne produit pas de fichier. Elle établit le slug, crée le dossier, et
  charge le contexte en mémoire pour la suite.
- Créer le dossier `discovery/<slug>/` dans le dossier de travail courant si aucun
  dossier utilisateur n'est connecté, sinon dans le dossier sélectionné par l'utilisateur.

## Chaînage des phases (handoff type BMAD)

Chaque phase est autonome mais consomme le livrable de la précédente :

- Phase 0 → contexte en tête (pas d'output).
- Phase 1 lit le contexte de Phase 0 → écrit `context.md`.
- Phase 2 lit `context.md` → écrit `brainsta.md`.
- Phase 3 lit `brainsta.md` (+ `context.md`) → écrit `user-stories.md`.
- Phase 4 lit `user-stories.md` (+ `brainsta.md`) → écrit `solution.md`.
- Phase 5 (optionnelle) lit `solution.md` (+ `brainsta.md`, `context.md`) → écrit
  `alignement.md` (one-pager CSM / Sales).
- Phase 6 (optionnelle) lit `solution.md`, `user-stories.md`, `brainsta.md`,
  `context.md` → écrit `prd.md` (PRD pour l'équipe de build).

Les Phases 5 et 6 sont deux livrables terminaux optionnels après la Phase 4 :
la Phase 5 est orientée CSM / Sales, la Phase 6 orientée équipe de build. Elles sont
indépendantes l'une de l'autre.

Au début de chaque phase (sauf 0), vérifier que le livrable amont existe. S'il
manque, proposer de lancer la phase manquante d'abord. Ne jamais inventer le contenu
d'une phase amont.

À la fin de chaque phase, terminer par un bloc « Handoff » : résumé en 3 lignes de ce
qui a été produit + proposition explicite de lancer la phase suivante.

## Sources de données (connecteurs)

- Interviews de discovery : base Notion dédiée où sont stockés tous les entretiens
  (source principale), complétée par Granola (transcripts de meetings) et par des
  notes collées directement par l'utilisateur.
- Analytics produit : Amplitude EU (optionnel, si l'utilisateur veut quantifier).
- Restitution : fichiers `.md` locaux ET, si demandé, une page Notion.
- User stories : peuvent être poussées dans Linear (optionnel, Phase 3).

Si un connecteur n'est pas autorisé, le dire clairement et continuer avec les notes
collées / le contenu fourni manuellement. Ne jamais bloquer le workflow sur un
connecteur manquant.

## Contexte Mayday

Mayday est une plateforme de gestion de la connaissance pour les équipes support et
service client. Les utilisateurs typiques : agents de support (retrouver la bonne
réponse vite), knowledge managers (maintenir la base à jour), managers support.
Les problèmes clients tournent souvent autour de : vitesse et pertinence de la
recherche, fraîcheur de la connaissance, adoption par les agents, intégration aux
outils métier (CRM, ticketing), déflexion / self-service.

## Principe directeur

Rester au niveau du PROBLÈME le plus longtemps possible. Ne pas sauter vers la
solution (Phases 0 à 3). La solution ne se travaille qu'en Phase 4. Distinguer
toujours le problème (ce qui coince pour l'utilisateur) de la solution (ce qu'on
construit).
