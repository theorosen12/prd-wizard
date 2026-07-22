# Template de PRD (adapté de BMAD)

Colonne vertébrale essentielle par défaut, puis menu adaptatif. Réutiliser au maximum
les livrables des phases 1 à 4 (context.md, brainsta.md, user-stories.md, solution.md).

## Colonne vertébrale essentielle (presque toujours présente)

```markdown
---
title: {Nom du produit / de la fonctionnalité}
created: {AAAA-MM-JJ}
updated: {AAAA-MM-JJ}
status: draft
---

# PRD : {Nom}
*Titre de travail, à confirmer.*

## 0. Objet du document
[1 paragraphe : pour qui ce PRD (PM, équipe de build, parties prenantes), comment il est
structuré, sur quels livrables amont il s'appuie (context.md, brainsta.md,
user-stories.md, solution.md) sans les dupliquer.]

## 1. Vision
[2-3 paragraphes : ce que c'est, ce que ça fait pour l'utilisateur, pourquoi ça compte.
Reprendre le problem statement de brainsta.md et la solution retenue de solution.md.]

## 2. Utilisateur cible
### 2.1 Jobs To Be Done
[Puces. Reprendre personas et besoins de context.md.]
### 2.2 Non-utilisateurs v1 *(si la frontière n'est pas évidente)*
### 2.3 User journeys clés (UJ-1 à UJ-N)
[Narratifs avec protagoniste nommé. Dériver des user stories de la Phase 3. Les FR y
renvoient (« réalise UJ-3 »). Forme : contexte persona, état d'entrée, parcours 3-5
étapes, climax où la valeur est délivrée, résolution, cas limite optionnel.]

## 3. Glossaire
[Chaque nom métier défini une fois. Aucun synonyme ailleurs dans le PRD. FR, UJ et
métriques emploient ces termes à l'identique.]

## 4. Features
*Chaque sous-section : description comportementale, puis FR imbriqués numérotés
globalement.*

### 4.1 {Nom de la feature}
**Description :** [Narratif comportemental. Réalise UJ-X. Termes du glossaire. Tags
`[HYPOTHESE: ...]` inline là où c'est inféré.]

**Exigences fonctionnelles :**

#### FR-1 : {Nom court de la capacité}
[Acteur] peut [capacité] [sous conditions]. Réalise UJ-X.
**Conséquences (testables) :**
- {Condition testable précise.}
**Hors scope :** *(optionnel)*

#### FR-2 : ...

**NFR spécifiques à la feature :** *(seulement si applicable)*
**Notes :** *(optionnel, `[NOTE PM]`)*

## 5. Non-goals (explicites)
[Puces. Ce que le produit n'est pas et ne fera pas en v1. Reprendre le hors scope de
brainsta.md et solution.md.]

## 6. Périmètre MVP
### 6.1 Dans le scope
### 6.2 Hors scope MVP
[Chaque item avec une raison si elle compte. Marquer les reports v2/v3.]

## 7. Métriques de succès
*Chaque métrique renvoie aux FR qu'elle valide. Contre-métriques pour éviter d'optimiser
la mauvaise chose.* Reprendre les métriques de solution.md.
**Primaires** : SM-1 - définition, cible. Valide FR-X.
**Secondaires** : SM-2 - ...
**Contre-métriques (à ne pas optimiser)** : SM-C1 - pourquoi. Contrebalance SM-1.

## 8. Questions ouvertes
[Numérotées. Inconnues qui deviennent des tickets ou de la recherche, pas des trous
silencieux. Reprendre les questions ouvertes des phases amont.]

## 9. Index des hypothèses
[Chaque `[HYPOTHESE]` du document, listé pour confirmation explicite.]
```

## Menu adaptatif (ajouter les clusters que le produit exige)

- Qualité transverse : NFR transverses (perf, sécurité, fiabilité, observabilité) ;
  contraintes et garde-fous (sécurité, privacy, coût) ; « pourquoi maintenant » si le
  timing est porteur.
- Produit orienté utilisateur : esthétique et ton ; architecture de l'information ;
  monétisation ; plateforme (web / mobile / desktop).
- Initiative interne / entreprise : parties prenantes et validations ; risques et
  mitigations ; ROI ; exigences opérationnelles (SLA, support) ; intégrations et
  dépendances (SSO, CRM, ticketing) ; rollout et conduite du changement ; gouvernance
  des données.
- Domaine régulé : conformité (RGPD, SOC 2, accessibilité WCAG...).
- Produit développeur : contrats d'API / surface publique ; versioning et dépréciation ;
  budgets de performance.

Quand le produit porte un enjeu que le menu ne nomme pas, inventer la section, la nommer
correctement, décider de son contenu, la placer là où elle sert le lecteur.
