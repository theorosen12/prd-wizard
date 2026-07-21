---
name: phase-4-solution
description: >
  Phase 4 (finale) du workflow de discovery produit Mayday, côté design. À utiliser
  quand l'utilisateur veut "lancer la phase 4", "brainstormer la solution", "concevoir
  la réponse au problème", "passer au design de la solution", ou après avoir produit
  `user-stories.md` en Phase 3. Ouvre enfin le "comment" : idéation et définition d'une
  solution répondant aux user stories. Produit `solution.md`. Le workflow s'arrête
  avant le développement.
metadata:
  version: "0.1.0"
  phase: "4"
---

# Phase 4 — Brainsto solution (design)

Lire d'abord `${CLAUDE_PLUGIN_ROOT}/shared/conventions.md`. Pour la facilitation du
brainstorming (posture, choix de technique, catalogue, capture), suivre
`${CLAUDE_PLUGIN_ROOT}/shared/brainstorming-bmad.md` (méthode adaptée de BMAD). Voir
`${CLAUDE_PLUGIN_ROOT}/skills/phase-4-solution/references/solution-guide.md` pour la
méthode d'idéation et le gabarit de `solution.md`.

## But de la phase

C'est ici, et seulement ici, qu'on ouvre le « comment ». À partir des user stories,
brainstormer plusieurs directions de solution, les comparer, puis définir la solution
retenue au niveau concept (parcours, principes, périmètre). On s'arrête avant le
développement : pas de code, pas de tickets techniques détaillés. On peut décrire
l'UX et les grands écrans / parcours au niveau concept.

Livrable : `discovery/<slug>/solution.md`.

## Pré-requis

Lire `discovery/<slug>/user-stories.md` (Phase 3), et pour le contexte `brainsta.md` et
`context.md`. Si `user-stories.md` manque, proposer de lancer la Phase 3 d'abord.

## Déroulé

### 1. Diverger (idéation, méthode BMAD)

Faciliter avec la méthode de `shared/brainstorming-bmad.md` : posture de coach
"Yes, and", proposer un mode de sélection de technique (choix utilisateur, recommandé,
aléatoire, progressif). Pour l'idéation de solution, les catégories Structurées
(SCAMPER), Créatives (Métaphores, Forced Connections, Pensée analogique) et Wild (Worst
Possible Idea, 100 idées) sont particulièrement utiles ; le mode progressif
(structuré → créatif → wild) donne souvent le meilleur résultat.

- Générer plusieurs directions de solution distinctes (au moins 2 à 3), pas une seule.
- Varier l'ambition : quick win, solution médiane, solution idéale.
- Pour chaque direction, décrire l'idée en quelques lignes et comment elle adresse la
  story cœur.
- Penser Mayday : cohérence avec la plateforme de gestion de connaissance existante,
  intégrations, faisabilité raisonnable.
- Ne pas juger pendant la génération. Trier ensuite (étape 2) : regrouper, repérer les
  standouts, ajouter les détails concrets.

### 2. Comparer et choisir

- Évaluer chaque direction : impact sur le problème, effort estimé (grossier),
  risques, cohérence produit.
- Recommander une direction, en justifiant. Laisser une alternative visible.

### 3. Définir la solution retenue (niveau concept)

- Décrire le concept : principe central, parcours utilisateur clé (au niveau étapes,
  pas de maquette pixel), périmètre d'un premier incrément.
- Relier chaque user story cœur à la façon dont la solution y répond.
- Lister les questions ouvertes pour le design détaillé et pour l'engineering (sans
  entrer dans l'implémentation).
- Proposer des metrics de succès pour valider que la solution résout le problème.

### 4. Écrire `solution.md`

Suivre le gabarit du fichier de référence. Écrire dans
`discovery/<slug>/solution.md`. Si Notion est destination, proposer la page Notion.
Si l'utilisateur veut aller vers le design visuel, suggérer d'enchaîner avec un outil
de design / Figma, hors de ce plugin.

## Handoff

Terminer par : la solution retenue en une phrase + récap du parcours (context.md,
brainsta.md, user-stories.md, solution.md) + « Solution définie. Prochaine étape :
Phase 6 (PRD pour l'équipe de build), l'étape finale du workflow. Option en parallèle :
Phase 5 (one-pager d'alignement CSM / Sales). On enchaîne sur le PRD ? »
