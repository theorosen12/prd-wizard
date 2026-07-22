---
name: phase-1-discovery
description: >
  Phase 1 du workflow de discovery produit Mayday. À utiliser quand l'utilisateur veut
  "lancer la phase 1", "faire la discovery", "analyser les entretiens", "sortir les
  discovery statements", "creuser le problème avec les interviews et l'analytics", ou
  après avoir terminé la Phase 0. Analyse les entretiens (base Notion + Granola + notes)
  et l'analytics Amplitude EU pour produire des discovery statements factuels dans
  `context.md`.
metadata:
  version: "0.1.0"
  phase: "1"
---

# Phase 1 — Discovery statements

Lire d'abord `${CLAUDE_PLUGIN_ROOT}/shared/conventions.md`. Voir aussi
`${CLAUDE_PLUGIN_ROOT}/skills/phase-1-discovery/references/discovery-guide.md`
pour la méthode d'analyse détaillée et le gabarit de `context.md`.

## But de la phase

Transformer la matière brute (entretiens, analytics) en **discovery statements** :
des constats factuels, sourcés, sur ce que vivent les utilisateurs. On reste au niveau
des faits et des signaux, pas encore de la définition du problème (Phase 2) ni de la
solution (Phase 4).

Livrable : `discovery/<slug>/context.md`.

## Pré-requis

Vérifier que la Phase 0 a été faite (slug + dossier + cadrage). Sinon, proposer de la
lancer d'abord.

Vérifier qu'il y a assez de matière à analyser (entretiens, notes, analytics). S'il n'y
a pas ou trop peu d'entretiens exploitables et que l'hypothèse de problème n'est pas
validée, proposer de passer d'abord par la Phase 1b (préparer et mener des entretiens de
discovery), puis revenir ici pour l'analyse.

## Déroulé

### 1. Collecter la matière

- **Entretiens (source principale)** : interroger la base Notion des entretiens de
  discovery. Récupérer les entretiens pertinents pour le sujet, lire leur contenu.
  Noter pour chaque entretien : qui (rôle / persona), quand, verbatims marquants.
- **Granola** : récupérer les transcripts de meetings liés au sujet.
- **Notes collées** : intégrer tout texte fourni directement par l'utilisateur.
- **Analytics Amplitude EU (optionnel)** : si l'utilisateur veut quantifier, formuler
  1 à 3 questions data (ex : taux d'usage de la recherche, temps passé, taux d'échec de
  recherche) et aller chercher les chiffres. Ne pas surcharger : l'analytics illustre
  et quantifie les signaux qualitatifs, elle ne les remplace pas.

Si un connecteur manque ou n'est pas autorisé, le signaler et continuer avec le reste.

### 2. Analyser et regrouper

- Extraire les verbatims et signaux, les regrouper par thème (pain points, workarounds,
  attentes, contexte d'usage).
- Pour chaque thème, compter la fréquence (combien d'entretiens le mentionnent) et noter
  l'intensité (à quel point c'est bloquant).
- Croiser avec l'analytics quand c'est disponible.

### 3. Formuler les discovery statements

Un discovery statement est un constat factuel, sourcé, du type :
« [Persona] rencontre [situation] quand [contexte], ce qui provoque [conséquence]. »
Chaque statement doit être appuyé par au moins un verbatim ou une donnée. Ne pas
formuler de solution. Ne pas encore trancher le problème central.

### 4. Écrire `context.md`

Suivre le gabarit du fichier de référence. Sections : résumé, personas, sources
analysées, discovery statements (triés par fréquence / intensité), signaux analytics,
questions ouvertes. Écrire le fichier dans `discovery/<slug>/context.md`.

Si l'utilisateur a demandé Notion en destination, proposer aussi de créer une page
Notion reprenant `context.md`.

## Handoff

Terminer par : 3 lignes de synthèse (top 3 des statements les plus forts) + « `context.md`
est prêt. Prochaine étape : Phase 2 (Problem statement) pour trancher LE problème à
résoudre à partir de ces constats. On enchaîne ? »
