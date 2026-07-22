# Guide d'analyse - Phase 1 Discovery

## Comment interroger la base Notion des entretiens

1. Rechercher la base / data source des entretiens de discovery (notion-search puis
   notion-query-data-sources).
2. Filtrer par mots-clés du problème et par persona quand la base a ces propriétés.
3. Pour chaque entretien retenu, lire le contenu (notion-fetch) et extraire :
   - Rôle / persona de l'interviewé, entreprise, date.
   - Verbatims marquants (citations exactes, entre guillemets).
   - Pains, workarounds, attentes exprimées.
4. Toujours garder le lien Notion de l'entretien pour la traçabilité (à citer dans
   `context.md`).

## Règles de qualité des discovery statements

- Factuel : un statement décrit ce qui EST observé, pas une hypothèse de solution.
- Sourcé : au moins un verbatim ou une donnée par statement.
- Spécifique : éviter les généralités (« les users veulent que ce soit mieux »).
- Format : « [Persona] rencontre [situation] quand [contexte], ce qui provoque
  [conséquence]. »
- Séparer les faits (ce qui est dit / mesuré) des interprétations (clairement notées
  comme telles).

## Utiliser l'analytics Amplitude EU (optionnel)

- Formuler la question business avant de toucher aux données.
- Vérifier les noms d'événements réels avant de filtrer (get_events), ne jamais
  deviner.
- Chercher à confirmer ou infirmer un signal qualitatif : fréquence d'un
  comportement, ampleur d'un abandon, temps passé, taux d'échec.
- Reporter le chiffre avec sa définition et la période. Ne pas surinterpréter.

## Gabarit de `context.md`

```markdown
# Context - <Titre du problème>

_Phase 1 (Discovery statements). Généré le <date>. Slug : <slug>._

## Résumé
3 à 5 lignes : de quoi parle ce problème, pour qui, à quel point c'est fort.

## Personas concernés
- <Persona 1> : rôle, contexte d'usage de Mayday.
- <Persona 2> : ...

## Sources analysées
- Entretiens Notion : N entretiens (liens).
- Granola : N réunions.
- Notes / docs fournis : ...
- Analytics Amplitude EU : oui / non, quelles métriques.

## Discovery statements
Triés du plus fort au plus faible (fréquence x intensité).

1. **[Titre court]** - [Persona] rencontre [situation] quand [contexte], ce qui
   provoque [conséquence].
   - Fréquence : X / N entretiens.
   - Verbatim : « ... » (source, lien).
   - Donnée : ... (si dispo).
2. ...

## Signaux analytics
- Métrique : valeur, période, ce qu'elle suggère.

## Questions ouvertes
- Ce qui reste à creuser, hypothèses non tranchées.
```
