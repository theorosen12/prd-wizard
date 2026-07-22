---
name: phase-2-problem
description: >
  Phase 2 du workflow de discovery produit Mayday. À utiliser quand l'utilisateur veut
  "lancer la phase 2", "faire le brainstorming du problème", "définir le problem
  statement", "trancher le problème à résoudre", ou après avoir produit `context.md`
  en Phase 1. Brainstorming pour formuler LE problem statement (sans passer par l'UX
  ni la solution). Produit `brainsta.md`.
metadata:
  version: "0.1.0"
  phase: "2"
---

# Phase 2 - Brainstorming Problem statement (pas d'UX)

Lire d'abord `${CLAUDE_PLUGIN_ROOT}/shared/conventions.md`. Pour la facilitation du
brainstorming (posture, choix de technique, catalogue, capture), suivre
`${CLAUDE_PLUGIN_ROOT}/shared/brainstorming-bmad.md` (méthode adaptée de BMAD). Voir
`${CLAUDE_PLUGIN_ROOT}/skills/phase-2-problem/references/problem-guide.md` pour la
méthode et le gabarit de `brainsta.md`.

> **Interaction (voir conventions).** Pose une question a la fois, puis ARRETE-TOI et attends la reponse de l'utilisateur. Ne reponds jamais a tes propres questions, ne suppose pas ses reponses, n'invente aucun fait sur ses clients ou son contexte. Exception : seulement s'il demande explicitement un mode rapide / autonome.

## But de la phase

À partir des discovery statements, brainstormer puis **trancher LE problème à
résoudre**. On raisonne problème, pas solution, et **pas d'UX** : aucune maquette,
aucun écran, aucun parcours à ce stade. On ne parle pas encore de « comment », on
verrouille le « quoi » et le « pourquoi ».

Livrable : `discovery/<slug>/brainsta.md`.

## Pré-requis

Lire `discovery/<slug>/context.md` (Phase 1). S'il n'existe pas, proposer de lancer la
Phase 1 d'abord. Ne pas inventer les discovery statements.

## Déroulé

### 1. Diverger (brainstorming, méthode BMAD)

Faciliter cette divergence avec la méthode de `shared/brainstorming-bmad.md` : adopter
la posture de coach "Yes, and", proposer un mode de sélection de technique (choix
utilisateur, recommandé, aléatoire, progressif), puis dérouler la ou les techniques
choisies. Pour un problème, les catégories Profondes (5 Pourquoi, Laddering, Assumption
Surfacing, Problem Reversal) et Structurées (Reverse Brainstorming) sont souvent les
plus utiles ; proposer aussi les Théâtrales (Role Storming, Pre-mortem) pour changer
d'angle.

À partir des discovery statements, générer plusieurs formulations candidates du
problème. Pour chacune, expliciter : qui, quoi, quand, impact. Chercher plusieurs
angles (problème vécu par l'agent, par le knowledge manager, par le business Mayday).
Rester sur le problème : toute idée de solution part dans un parking lot. Jouer le
sparring partner : poser des questions qui piquent, éviter la complaisance, révéler les
hypothèses cachées.

### 2. Converger

- Regrouper les candidats, éliminer les doublons et les symptômes.
- Évaluer chaque candidat sur : ampleur (combien d'utilisateurs), intensité de la
  douleur, alignement stratégique Mayday, preuve (appui dans `context.md`).
- Trancher : choisir UN problem statement principal. Le reste devient « problèmes
  adjacents / hors scope ».

### 3. Formaliser le problem statement

Format recommandé :
« Aujourd'hui, [persona] doit [objectif] mais [obstacle], ce qui entraîne [conséquence
mesurable]. Nous pensons que c'est important parce que [enjeu utilisateur + enjeu
Mayday]. »

Ajouter : hypothèses sous-jacentes, ce qui est explicitement hors scope, et les
critères qui feront dire que le problème est résolu (signaux de succès, pas encore des
metrics de solution).

### 4. Écrire `brainsta.md`

Suivre le gabarit du fichier de référence. Écrire dans `discovery/<slug>/brainsta.md`.
Si Notion est destination, proposer d'y créer la page correspondante.

## Handoff

Terminer par : le problem statement en une phrase + « Problème verrouillé. Prochaine
étape : Phase 3 (User stories) pour décliner ce problème en besoins utilisateurs. On
continue ? »
