---
name: phase-3b-vision
description: >
  Phase 3b du workflow de discovery produit Mayday, juste avant la solution. À utiliser
  quand l'utilisateur veut "écrire la vision produit", "poser la vision", "définir le
  north star", "un document de vision", "cadrer où on veut aller avant d'idéer la
  solution", ou après avoir produit `user-stories.md` en Phase 3. Synthétise problème et
  besoins en une vision produit qui cadre l'idéation de la solution. Produit `vision.md`.
  Adapté du workflow product-brief de BMAD.
metadata:
  version: "0.1.0"
  phase: "3b"
---

# Phase 3b - Vision produit

Lire d'abord `${CLAUDE_PLUGIN_ROOT}/shared/conventions.md`. Utiliser
`${CLAUDE_PLUGIN_ROOT}/skills/phase-3b-vision/references/vision-template.md` (structure
du document de vision).

> **Interaction (voir conventions).** Pose une question a la fois, puis ARRETE-TOI et attends la reponse de l'utilisateur. Ne reponds jamais a tes propres questions, ne suppose pas ses reponses, n'invente aucun fait sur ses clients ou son contexte. Exception : seulement s'il demande explicitement un mode rapide / autonome.

## But de la phase

Poser la vision produit : le north star, l'état futur désiré, le changement qu'on veut
créer pour l'utilisateur et pour Mayday. Elle vient après le problème (Phase 2) et les
besoins (Phase 3), et cadre l'idéation de la solution (Phase 4) : on dit OÙ on veut
aller et POURQUOI, avant de décider COMMENT.

La vision reste au niveau outcome / aspiration, pas au niveau features. Ne pas concevoir
la solution ici (c'est la Phase 4), ne pas rejouer le problème (Phase 2).

Livrable : `discovery/<slug>/vision.md`.

## Posture (coach, adaptée de BMAD)

Agir en coach analyste produit : ne pas penser à la place de l'utilisateur, faire
émerger sa vision, pousser là où les hypothèses sont molles, alléger quand la vision se
précise ou qu'il fatigue. La vision doit être honnête et ambitieuse mais crédible : ne
pas fabriquer de faux avantages concurrentiels, distinguer ce qui est su de ce qui est
pari.

## Pré-requis

Lire `discovery/<slug>/brainsta.md` (problème), `user-stories.md` (besoins) et pour le
contexte `context.md`. Si `user-stories.md` manque, proposer de lancer la Phase 3
d'abord. Réutiliser ces sources : ne pas réinventer le problème ni les personas.

## Déroulé

1. Brain dump : inviter l'utilisateur à exprimer où il veut emmener le produit sur ce
   sujet, et récupérer tout matériel existant (stratégie, north star metric, OKR).
2. Choix du mode : mode rapide (rédiger la vision avec des tags `[HYPOTHESE]` là où
   c'est inféré, l'utilisateur corrige) ou mode coaching (dérouler ensemble, pousser sur
   les hypothèses molles).
3. Construire la vision en s'appuyant sur le template : résumé / north star, à qui ça
   s'adresse, le changement visé, ce à quoi ressemble le succès (outcomes, pas metrics
   de solution), ce qui différencie l'approche de Mayday, la vision à 1-2 ans, et le
   cadrage haut niveau (ce que la vision inclut / exclut).
4. Rester right-sized : 1 à 2 pages. Le détail va dans le PRD (Phase 5) ou de côté.

## Écrire `vision.md`

Suivre le template de référence. Écrire dans `discovery/<slug>/vision.md`. Si Notion est
destination, proposer d'en créer la page.

## Handoff

Terminer par : la vision en une phrase (north star) + « Vision posée. Prochaine étape :
Phase 4 (Brainsto solution), pour idéer le comment au service de cette vision. On y va ? »
