# Guide — Phase 3 User stories

## Format d'une user story

« En tant que [persona], je veux [capacité] afin de [bénéfice]. »

Bonnes pratiques (INVEST) :
- Independent : autonome autant que possible.
- Negotiable : décrit un besoin, pas une spec figée.
- Valuable : porte une valeur claire pour l'utilisateur.
- Estimable : assez précise pour être évaluée.
- Small : découpée finement.
- Testable : vérifiable via critères d'acceptation.

Rester au niveau du besoin. Ne pas décrire l'écran, le bouton ou le composant.
Exemple correct : « En tant qu'agent support, je veux retrouver la bonne réponse en
moins de X secondes afin de ne pas faire attendre le client. »
Exemple à éviter (trop solution / UX) : « Je veux une barre de recherche avec
autocomplétion en haut à droite. »

## Critères d'acceptation

Format Given / When / Then :
- Étant donné [contexte], quand [action], alors [résultat attendu].

Ou liste de conditions vérifiables. Ils portent sur le résultat vécu par
l'utilisateur, pas sur l'implémentation.

## Priorisation

MoSCoW : Must have / Should have / Could have / Won't have (pour l'instant).
Toujours identifier la ou les stories cœur qui adressent directement le problem
statement de la Phase 2.

## Pousser dans Linear (optionnel)

- Demander l'équipe et le projet cible avant toute création.
- Une issue par story : titre = story, description = bénéfice + critères
  d'acceptation, label = slug du projet de discovery.
- Ne créer qu'après validation explicite de l'utilisateur.

## Gabarit de `user-stories.md`

```markdown
# User stories — <Titre du problème>

_Phase 3. Généré le <date>. Slug : <slug>._
_Sources : brainsta.md (Phase 2), context.md (Phase 1)._

## Rappel du problème
Une phrase (repris de brainsta.md).

## Stories (priorisées)

### Must have
1. **[Titre court]**
   En tant que [persona], je veux [capacité] afin de [bénéfice].
   - Critères d'acceptation :
     - Étant donné ..., quand ..., alors ...
   - Lien discovery : renvoi vers les statements concernés.

### Should have
- ...

### Could have
- ...

### Hors scope (Won't, pour l'instant)
- ...

## Story cœur
Laquelle adresse le plus directement le problem statement, et pourquoi.
```
