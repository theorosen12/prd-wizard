# Guide - Phase 2 Problem statement

## Rappels de posture

- Problème, pas solution. Si une idée de solution surgit, la noter dans un parking lot
  et revenir au problème.
- Pas d'UX : aucun écran, wireframe, parcours ou composant. C'est la Phase 4 qui
  ouvrira le « comment ».
- Distinguer symptôme et cause. Un bon problem statement vise une cause actionnable.

## Techniques utiles

- 5 pourquoi : remonter d'un symptôme à la cause racine.
- Job to be done : quel progrès l'utilisateur cherche-t-il à faire ?
- Reformulation multiple : écrire 3 à 5 versions du problème et comparer.
- Test du « et alors ? » : si on ne résout pas ce problème, quelle est la conséquence
  réelle ? Si la réponse est faible, le problème n'est peut-être pas prioritaire.

## Critères de sélection du problème principal

| Critère | Question |
|---|---|
| Ampleur | Combien d'utilisateurs / clients Mayday touchés ? |
| Intensité | À quel point c'est douloureux / bloquant ? |
| Preuve | Est-ce appuyé par les discovery statements ? |
| Stratégie | Est-ce aligné avec la direction produit Mayday ? |
| Actionnable | Peut-on raisonnablement s'y attaquer ? |

## Gabarit de `brainsta.md`

```markdown
# Problem statement - <Titre>

_Phase 2 (Brainstorming problème). Généré le <date>. Slug : <slug>._
_Source : context.md (Phase 1)._

## Problem statement principal
Aujourd'hui, [persona] doit [objectif] mais [obstacle], ce qui entraîne [conséquence
mesurable]. C'est important parce que [enjeu utilisateur + enjeu Mayday].

## Pourquoi ce problème (preuves)
- Appui dans les discovery statements : ... (renvoi vers context.md).
- Ampleur / intensité : ...

## Candidats explorés (brainstorming)
- Candidat A : ... (retenu / écarté, pourquoi).
- Candidat B : ...

## Causes racines
- ... (résultat des 5 pourquoi le cas échéant).

## Hypothèses sous-jacentes
- On suppose que ...

## Hors scope
- Problèmes adjacents volontairement écartés pour l'instant.

## À quoi ressemble « résolu »
- Signaux qui indiqueraient que le problème est réglé (côté utilisateur / business).
```
