# Guide — Phase 4 Brainsto solution

## Posture

- C'est la seule phase où le « comment » est autorisé.
- On conçoit au niveau concept : parcours, principes, périmètre. Pas de maquette pixel,
  pas de code, pas de spec technique détaillée.
- Toujours relier la solution aux user stories cœur de la Phase 3 : une solution qui ne
  sert aucune story est hors sujet.

## Idéation : diverger avant de converger

- Produire au moins 2 à 3 directions distinctes, pas une seule.
- Techniques : crazy 8 mental (variantes rapides), analogies (comment d'autres outils
  résolvent un problème proche), inversion (et si on faisait l'inverse ?), niveaux
  d'ambition (quick win / médian / idéal).
- Rester ancré dans la réalité Mayday : plateforme de connaissance, agents support,
  intégrations existantes.

## Comparaison des directions

| Critère | Question |
|---|---|
| Impact | À quel point ça résout le problème de la Phase 2 ? |
| Effort | Coût grossier de mise en oeuvre ? |
| Risque | Techniques, adoption, dépendances ? |
| Cohérence | S'intègre-t-elle bien au produit Mayday ? |

Recommander une direction et garder une alternative visible.

## Gabarit de `solution.md`

```markdown
# Solution — <Titre du problème>

_Phase 4 (Brainsto solution). Généré le <date>. Slug : <slug>._
_Sources : user-stories.md, brainsta.md, context.md._

## Rappel
- Problème : une phrase (Phase 2).
- Story cœur : une phrase (Phase 3).

## Directions explorées
### Direction A — <nom>
Idée, comment elle adresse la story cœur, impact / effort / risque.
### Direction B — <nom>
...
### Direction C — <nom>
...

## Direction recommandée
Laquelle et pourquoi. Alternative gardée en réserve.

## Concept de la solution retenue
- Principe central.
- Parcours utilisateur clé (étapes, niveau concept).
- Périmètre du premier incrément (ce qui est dedans / dehors).

## Réponse aux user stories
- Story cœur → comment la solution y répond.
- Autres stories couvertes.

## Metrics de succès
- Comment on saura que le problème est résolu.

## Questions ouvertes
- Pour le design détaillé.
- Pour l'engineering (sans entrer dans l'implémentation).

## Étapes suivantes (hors plugin)
- Design détaillé / Figma.
- Développement.
```
