---
name: phase-5-prd
description: >
  Phase 5 (finale, pour l'équipe de build) du workflow de discovery produit Mayday. À
  utiliser quand l'utilisateur veut "générer le PRD", "écrire le PRD", "rédiger les
  spécifications", "un document de requirements pour l'équipe", "créer / mettre à jour /
  valider un PRD", ou après avoir produit `solution.md` en Phase 4. Consolide contexte,
  problème, user stories et solution en un PRD structuré (features, FR testables,
  glossaire, métriques). Produit `prd.md`. Adapté du workflow PRD de BMAD.
metadata:
  version: "0.1.0"
  phase: "5"
---

# Phase 5 - Génération du PRD

Lire d'abord `${CLAUDE_PLUGIN_ROOT}/shared/conventions.md`. Utiliser
`${CLAUDE_PLUGIN_ROOT}/skills/phase-5-prd/references/prd-template.md` (structure du PRD)
et `${CLAUDE_PLUGIN_ROOT}/skills/phase-5-prd/references/prd-checklist.md` (rubrique de
validation).

> **Interaction (voir conventions).** Pose une question a la fois, puis ARRETE-TOI et attends la reponse de l'utilisateur. Ne reponds jamais a tes propres questions, ne suppose pas ses reponses, n'invente aucun fait sur ses clients ou son contexte. Exception : seulement s'il demande explicitement un mode rapide / autonome.

## Posture

Agir en facilitateur et coach qui aide à produire un PRD de qualité, calibré au niveau
de rigueur voulu. Ne pas penser à la place de l'utilisateur, sauf s'il choisit le mode
rapide. Le PRD décrit des capacités (le quoi), pas l'implémentation (le comment
technique va dans un addendum si besoin). C'est le document de handoff vers l'équipe de
build et l'étape finale du plugin ; le workflow s'arrête avant le développement.

Livrable : `discovery/<slug>/prd.md`.

## Le PRD est la source de vérité, il consolide sans réécrire

La discovery est déjà faite. Le PRD n'invente rien : il assemble et référence les
livrables amont, puis comble les manques. Charger depuis `discovery/<slug>/` :

- `context.md` (Phase 1) : discovery statements, personas, signaux analytics.
- `vision.md` (Phase 3b) : north star et outcomes visés, qui nourrissent la section
  Vision du PRD.
- `brainsta.md` (Phase 2) : problem statement, causes racines, hors scope.
- `user-stories.md` (Phase 3) : user stories de besoin, qui alimentent les user journeys.
- `solution.md` (Phase 4) : direction de solution retenue, parcours, périmètre, métriques.

Éviter la redondance : les user journeys du PRD dérivent des user stories de la Phase 3 ;
les features dérivent de la solution de la Phase 4 ; les métriques de succès sont
finalisées ici comme référence unique (la Phase 4 les a proposées, le PRD les fige et les
relie aux FR). Les user stories de la Phase 3 sont des besoins de discovery ; le découpage
en stories exécutables pour le dev se fait plus tard, à partir de ce PRD, hors plugin.

Si `solution.md` manque, proposer de lancer la Phase 4 d'abord.

## Intentions

- Créer : aucun `prd.md` n'existe. Assembler un nouveau PRD depuis les livrables.
- Mettre à jour : un `prd.md` existe. Réconcilier avec un signal de changement,
  surfacer les conflits avec les décisions prises avant d'appliquer.
- Valider : critiquer sans modifier. Dérouler la rubrique (voir plus bas).

Détecter l'intention ; si ambigu, demander.

## Discovery (courte, car les sources existent)

1. Brain dump ciblé : demander ce qui a bougé depuis la Phase 4 et tout input
   complémentaire (contraintes techniques, deadlines, exigences légales, dépendances).
2. Calibrage des enjeux : hobby / interne / lancement, pour calibrer la rigueur et la
   profondeur des sections.
3. Choix du mode de travail :
   - Mode rapide : regrouper les manques en une ou deux questions, puis rédiger tout le
     PRD avec des tags `[HYPOTHESE: ...]` là où c'est inféré. L'utilisateur relit, on
     itère.
   - Mode coaching : dérouler les sections ensemble, section par section.

## Discipline du PRD

Suivre `references/prd-template.md`. Points clés :

- Features regroupées ; FR numérotés globalement (FR-1, FR-2...) avec IDs stables.
- Chaque FR a au moins une conséquence testable. Bannir « gère X correctement »,
  « performant », « user-friendly » : mettre des bornes, pas des adjectifs.
- Glossaire : chaque nom métier défini une fois, utilisé partout à l'identique. Les FR
  renvoient aux user journeys (UJ-1..UJ-N).
- Capacités, pas implémentation. Métriques de succès reliées aux FR, avec contre-métriques.
- Non-goals explicites, périmètre MVP in/out, questions ouvertes, index des hypothèses.
- Colonne vertébrale essentielle par défaut ; piocher dans le menu adaptatif du template
  les sections que le produit exige (NFR transverses, contraintes, conformité...). Ne
  jamais inclure une section parce qu'elle existe, ni omettre un vrai enjeu faute de
  section prévue.
- La longueur suit les enjeux. Le détail qui ne mérite pas sa place dans le PRD va dans
  un `addendum.md` optionnel.

## Validation (gate)

Utilisée par l'intention Valider, et à la finalisation. Dérouler la rubrique de
`references/prd-checklist.md` (7 dimensions) sur `prd.md`. Restituer par paliers :
un verdict en une phrase, puis les findings critiques et hauts ; le reste en une ligne.
Par finding : corriger, discuter, différer en question ouverte, ou ignorer.

## Finalisation

Réconcilier les inputs et les hypothèses (chaque `[HYPOTHESE]` confirmé ou tranché),
passer la validation, trancher les questions ouvertes bloquantes, puis polir. Écrire
`discovery/<slug>/prd.md`. Si Notion est destination, proposer la page Notion.

## Handoff (fin de workflow)

Terminer par : le titre du PRD et le nombre de FR + « PRD prêt pour l'équipe de build.
C'est la dernière étape du plugin ; la suite (développement) est hors scope. Option
finale : la Phase 6 (one-pager CSM / Sales) peut être produite à partir de ce PRD. »
