---
name: phase-0-contexte
description: >
  Phase 0 du workflow de discovery produit Mayday. À utiliser quand l'utilisateur
  veut "démarrer une discovery", "lancer la phase 0", "récupérer le contexte d'un
  problème", "cadrer un nouveau sujet produit" ou dit vouloir travailler sur un
  problème client Mayday sans encore savoir par où commencer. Récupère et structure
  le contexte du problème. Ne produit aucun fichier de livrable, prépare le terrain
  pour la Phase 1.
metadata:
  version: "0.1.0"
  phase: "0"
---

# Phase 0 - Récupération du contexte

Lire d'abord `${CLAUDE_PLUGIN_ROOT}/shared/conventions.md` et s'y conformer
(langue française, pas de tiret cadratin, dossier de travail, chaînage des phases).

> **Interaction (voir conventions).** Pose une question a la fois, puis ARRETE-TOI et attends la reponse de l'utilisateur. Ne reponds jamais a tes propres questions, ne suppose pas ses reponses, n'invente aucun fait sur ses clients ou son contexte. Exception : seulement s'il demande explicitement un mode rapide / autonome.

## But de la phase

Comprendre le sujet avant toute analyse. Charger en mémoire tout ce qui est déjà connu
sur le problème client visé. **Cette phase ne produit aucun fichier de livrable.** Elle
sert à cadrer et à créer l'espace de travail pour la suite.

## Déroulé

### 1. Cadrer le sujet avec l'utilisateur

Poser (via AskUserQuestion si le contexte est flou) les questions de cadrage minimales :

- Quel problème client, en une phrase ? (ex : « Les agents de support ne trouvent pas
  la connaissance assez vite dans Mayday »)
- Quel segment / persona est concerné en priorité ? (agent support, knowledge manager,
  manager, admin)
- Qu'est-ce qui a déclenché ce sujet maintenant ? (plaintes clients, churn, demande
  commerciale, intuition, données)
- Y a-t-il déjà des documents, tickets, ou entretiens existants sur le sujet ?

Ne pas chercher à résoudre le problème. Ne pas proposer de solution. Rester en écoute.

### 2. Rassembler le contexte existant

Selon ce qui est disponible et autorisé :

- Chercher dans la base Notion des entretiens de discovery les entretiens déjà liés au
  sujet (mots-clés du problème). Lister ce qui existe, sans encore l'analyser en
  profondeur (l'analyse fine est en Phase 1).
- Regarder les notes Granola de réunions récentes liées au sujet.
- Prendre en compte tout document ou lien fourni par l'utilisateur.
- Rappeler le contexte produit Mayday pertinent (voir conventions).

Si un connecteur n'est pas autorisé, le signaler et continuer avec ce que
l'utilisateur fournit manuellement.

### 3. Établir l'espace de travail

- Proposer un `slug` de projet en kebab-case dérivé du problème
  (ex : `recherche-connaissance-agents`). Le faire valider.
- Créer le dossier `discovery/<slug>/` (voir conventions pour l'emplacement).

## Restitution (à l'écran, pas de fichier)

Terminer par une synthèse orale structurée :

1. **Problème pressenti** : reformulation en une phrase.
2. **Persona(s) concerné(s)**.
3. **Ce qu'on sait déjà** : sources de contexte identifiées (nb d'entretiens Notion
   trouvés, notes, docs).
4. **Zones d'ombre** : ce qu'il faudra creuser.
5. **Suffisance de la matière** : évaluer si l'on a assez d'insights pour tester
   l'hypothèse de problème. Si l'hypothèse n'est pas validée et qu'il manque de matière
   (peu ou pas d'entretiens exploitables), recommander la Phase 1b (préparer des
   entretiens de discovery) avant la Phase 1.
6. **Handoff** : selon le point 5, proposer soit « Il manque de matière terrain pour
   valider l'hypothèse. On passe par la Phase 1b pour préparer des entretiens ? », soit
   « Contexte chargé et assez de matière. Prêt à lancer la Phase 1 (Discovery statements)
   pour produire `context.md`. On y va ? »

Ne jamais écrire de fichier dans cette phase.
