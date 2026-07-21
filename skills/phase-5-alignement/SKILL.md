---
name: phase-5-alignement
description: >
  Phase 5 (optionnelle, finale) du workflow de discovery produit Mayday. À utiliser
  quand l'utilisateur veut "produire le one-pager d'alignement", "un document pour les
  CSM et les sales", "aligner les équipes CSM / commerciales sur la fonctionnalité",
  "expliquer la feature aux CSM et au sales", ou après avoir produit `solution.md` en
  Phase 4. Génère un one-pager simple et extrêmement clair qui justifie la
  fonctionnalité et l'explique sans entrer dans les détails. Produit `alignement.md`.
metadata:
  version: "0.1.0"
  phase: "5"
---

# Phase 5 (optionnelle) — One-pager d'alignement CSM / Sales

Lire d'abord `${CLAUDE_PLUGIN_ROOT}/shared/conventions.md`. Voir
`${CLAUDE_PLUGIN_ROOT}/skills/phase-5-alignement/references/onepager-guide.md` pour le
gabarit et les règles de style.

## But de la phase

Produire un **one-pager d'alignement** destiné aux équipes CSM et Sales. Objectif :
qu'un CSM ou un commercial comprenne en une lecture pourquoi la fonctionnalité existe
et ce qu'elle apporte au client, pour pouvoir en parler avec assurance.

Contraintes clés :

- **Une page, pas plus.** Simple et extrêmement clair.
- Justifier la fonctionnalité (le problème client, la valeur) et l'expliquer
  simplement, **sans rentrer dans les détails** techniques ou de design.
- Zéro jargon produit interne. Langage orienté bénéfice client et argument commercial.

Livrable : `discovery/<slug>/alignement.md`.

## Pré-requis

Lire `discovery/<slug>/solution.md` (Phase 4), et pour le contexte `brainsta.md`
(problème) et `context.md` (preuves). Si `solution.md` manque, proposer de lancer la
Phase 4 d'abord. Ne pas inventer la solution.

## Déroulé

### 1. Extraire l'essentiel des phases précédentes

- Le problème client (depuis `brainsta.md`), reformulé en langage client.
- La solution retenue (depuis `solution.md`), en une description simple.
- 1 à 3 preuves ou signaux forts (depuis `context.md`) qui légitiment le sujet.

### 2. Traduire pour CSM et Sales

- Passer d'un vocabulaire produit à un vocabulaire de valeur client et de vente.
- Répondre implicitement aux questions d'un CSM / commercial : « C'est quoi ? »,
  « Pourquoi c'est utile pour mon client ? », « Qu'est-ce que je peux en dire ? ».
- Rester factuel : ne pas survendre, ne pas promettre de détails de roadmap non
  décidés.

### 3. Rédiger le one-pager

Suivre le gabarit du fichier de référence. Tenir sur une page. Écrire dans
`discovery/<slug>/alignement.md`.

### 4. Formats de sortie

- Toujours écrire le `.md`.
- Proposer de générer une version `.docx` propre (via la skill docx) si l'utilisateur
  veut un document partageable et mis en forme.
- Si Notion est destination, proposer d'en créer la page.

## Handoff (fin de workflow)

Terminer par : le pitch de la fonctionnalité en une phrase + « One-pager d'alignement
prêt. C'est la dernière étape du workflow de discovery. »
