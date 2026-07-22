---
name: phase-1b-entretiens
description: >
  Phase 1b (conditionnelle) du workflow de discovery produit Mayday. À utiliser quand
  l'hypothèse de problème n'est pas encore validée et qu'il manque de matière
  utilisateur / client, ou quand l'utilisateur veut "préparer des entretiens de
  discovery", "écrire un guide d'entretien", "faire des interviews pour tester
  l'hypothèse du problème", "un screener / une grille d'analyse d'interviews". Produit un
  kit d'entretien (screener, guide, grille de prise de notes, grille d'analyse) dans
  `guide-entretiens.md`, à mener avant de revenir en Phase 1 pour l'analyse.
metadata:
  version: "0.1.0"
  phase: "1b"
---

# Phase 1b (conditionnelle) — Entretiens de discovery

Lire d'abord `${CLAUDE_PLUGIN_ROOT}/shared/conventions.md`.

## Quand cette phase sert

Quand on arrive avec une idée floue du problème et pas assez d'insights utilisateurs /
clients : l'hypothèse de problème n'est pas validée. Avant de produire des discovery
statements solides (Phase 1) ou de trancher le problème (Phase 2), il faut aller
chercher de la matière terrain. Cette phase prépare des entretiens de discovery dont le
but est de **tester l'hypothèse de problème**, pas de valider une solution.

Elle est conditionnelle : si `context.md` (Phase 1) contient déjà assez d'entretiens et
de signaux, la sauter. Sinon, la lancer avant / à la place de l'analyse de Phase 1.

Livrable : `discovery/<slug>/guide-entretiens.md` (le kit complet). Une fois les
entretiens menés, revenir en Phase 1 pour coder et synthétiser en discovery statements.

## Toujours demander la durée d'entretien en premier

Avant de rédiger quoi que ce soit, demander la durée de chaque entretien (30, 45, 60,
90 min). Ne pas supposer. La durée pilote le nombre de questions, la profondeur des
deep-dives et le rythme. Si elle n'est pas donnée, la demander ; si elle l'est, la
confirmer et avancer.

## Ancrer sur l'hypothèse à tester

Partir du cadrage de la Phase 0 et de tout `brainsta.md` provisoire : formuler
explicitement l'hypothèse de problème à tester (« on pense que [persona] galère à
[situation] à cause de [cause supposée] »). Le guide doit chercher à infirmer autant
qu'à confirmer cette hypothèse. Si le sujet touche une fonctionnalité existante,
rechercher son contexte dans Notion (specs, PRD, docs de discovery) avant d'écrire les
questions, et confirmer sa compréhension avant de rédiger.

## Méthode (adaptée du kit d'entretien UX)

1. Clarifier la question de recherche et la décision qu'elle éclaire. Toute question qui
   ne nourrit pas cette décision est coupée.
2. Définir le segment cible et écrire un screener de 4 à 6 questions (bons profils
   inclus, purs donneurs d'avis exclus). Repère : 5 à 8 entretiens par segment.
3. Structurer le guide en entonnoir : warm-up (2 questions perso), contexte
   (comportement actuel), cœur (épisodes passés précis), deep-dives (banque de
   relances), clôture.
4. Réécrire chaque question en forme comportementale : « Raconte-moi la dernière fois où
   tu as fait X » plutôt que « Utiliserais-tu X ? ». Couper les hypothétiques.
5. Passer un test anti-question orientée : retirer adjectifs chargés et hypothèses
   cachées, ne pas souffler la réponse attendue.
6. Calibrer le guide à la durée donnée. Réserver warm-up et clôture, répartir le reste
   entre questions cœur et deep-dives. Repères : 30 min ≈ 5-6 questions cœur, 45 min ≈ 8,
   60 min ≈ 10-12, 90 min = deep-dives étendus. Guide sur une page, temps par bloc,
   relances marquées optionnelles.
7. Préparer la grille d'analyse en amont : codes de départ dérivés de la question de
   recherche ; séparer observation, verbatim et interprétation.
8. Rappeler la règle de synthèse (utilisée en Phase 1) : un pattern devient un insight
   après 3 mentions indépendantes ; signaler les voix uniques ; documenter les
   contradictions.

## Règles de qualité

- Aucune question cœur ne se répond par oui / non ; les questions fermées ne vont que
  dans le screener.
- Les questions visent le comportement passé, jamais les opinions ni l'usage
  hypothétique.
- Pas de questions de solution / fonctionnalité en discovery : le feedback solution
  relève des tests d'usabilité, pas d'ici.
- Le guide fonctionne même si l'ordre des questions change.
- Tout est en français, sans tiret cadratin.

## Format de sortie

Un document Markdown `discovery/<slug>/guide-entretiens.md` en quatre sections :
1) screener avec logique de sélection ; 2) guide d'entretien (une page, temps par bloc
calé sur la durée, banque de relances) ; 3) grille de prise de notes (timestamp,
observation, verbatim, interprétation) ; 4) grille d'analyse avec codes de départ et
gabarit d'insight (insight, verbatims, segment, implication).

Si Notion est destination, proposer d'en créer la page.

## Handoff

Terminer par : « Kit d'entretien prêt. Va mener les entretiens, puis reviens en Phase 1
(Discovery) pour coder les notes et sortir les discovery statements dans `context.md`. »
