---
name: phase-6-alignement
description: >
  Phase 6 (optionnelle, finale) du workflow de discovery produit Mayday. À utiliser
  quand l'utilisateur veut "produire le one-pager d'alignement", "un document pour les
  CSM et les sales", "aligner les équipes CSM / commerciales sur la fonctionnalité",
  "expliquer la feature aux CSM et au sales", ou après avoir produit `prd.md` en
  Phase 5. Génère un one-pager simple et extrêmement clair qui justifie la fonctionnalité
  et l'explique sans entrer dans les détails. Produit `alignement.md`.
metadata:
  version: "0.1.0"
  phase: "6"
---

# Phase 6 (optionnelle) — One-pager d'alignement CSM / Sales

Lire d'abord `${CLAUDE_PLUGIN_ROOT}/shared/conventions.md`. Voir
`${CLAUDE_PLUGIN_ROOT}/skills/phase-6-alignement/references/onepager-guide.md` pour le
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

Source principale : `discovery/<slug>/prd.md` (Phase 5), qui contient déjà la vision, les
bénéfices, les métriques et le périmètre tranchés. À défaut de PRD, se rabattre sur
`solution.md` (Phase 4) et `brainsta.md` (Phase 2). Ne pas inventer la fonctionnalité.

## Déroulé

### 1. Extraire l'essentiel du PRD

- Le problème client (vision et problem statement du PRD), reformulé en langage client.
- Ce qu'apporte la fonctionnalité (features et bénéfices du PRD), en une description
  simple.
- 1 à 3 preuves ou signaux forts qui légitiment le sujet.
- Le périmètre MVP et les non-goals, pour cadrer ce qu'il ne faut pas (encore) promettre.

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
prêt. C'est le dernier livrable optionnel du workflow. »
