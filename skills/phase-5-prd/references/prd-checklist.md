# Rubrique de qualité du PRD (adaptée de BMAD)

Rubrique de jugement, pas de case à cocher. Lire tout le PRD (et l'addendum s'il existe)
avant d'écrire. Pour chaque dimension, poser un verdict (solide / correct / mince /
cassé) appuyé par des exemples précis (citer les sections, nommer ce qui manque).
Calibrer aux enjeux et à la forme du produit. La sévérité mesure l'impact sur l'utilité
du PRD, pas la facilité du correctif.

## Les 7 dimensions

1. Décidabilité : un décideur peut-il agir sur ce PRD ? Décisions posées comme des
   décisions (pas enfouies), arbitrages nommés avec ce qui a été abandonné, questions
   ouvertes réellement ouvertes. Drapeau rouge : tout « s'équilibre », chaque NFR est
   « important ».

2. Substance vs décor : contenu mérité ou meuble ? Repérer le théâtre de personas
   (personas qui ne pilotent aucune décision), le théâtre d'innovation, le théâtre de
   NFR (« doit être scalable / sécurisé » sans seuils produit), le théâtre de vision
   (vision interchangeable avec n'importe quel PRD).

3. Cohérence stratégique : le PRD a-t-il une thèse ? Les features servent-elles un arc
   unifié ou est-ce une liste de capacités ? Métriques qui valident la thèse, pas juste
   de l'activité. Contre-métriques présentes. Drapeau rouge : un backlog déguisé en
   sections.

4. Clarté du « fini » : un ingénieur sait-il à quoi ressemble « done » pour chaque FR ?
   Au moins une conséquence testable par FR. Traquer « gère X correctement »,
   « performance raisonnable », « user-friendly ». Des bornes, pas des adjectifs. Dimension
   la plus exigeante, car les stories descendantes s'appuient dessus.

5. Honnêteté du périmètre : les omissions sont-elles explicites ? Section non-goals où
   elle travaille, tags `[HYPOTHESE]` sur les inférences non confirmées et indexés,
   `[NOTE PM]` aux décisions différées. Densité d'items ouverts cohérente avec les
   enjeux (beaucoup d'ouverts sur un PRD prêt à builder = bloquant).

6. Utilisabilité descendante : UX / archi / création de stories peuvent-elles extraire
   proprement ? Glossaire présent, noms métier identiques partout, IDs FR/UJ/SM
   contigus et uniques, cross-références qui résolvent, chaque section autonome, chaque
   UJ avec un protagoniste nommé.

7. Adéquation de forme : le PRD a-t-il été forcé dans une forme inadaptée ? Produit
   orienté utilisateur → UJ à protagoniste nommé porteurs. Outil interne mono-rôle →
   spec de capacités, UJ parfois superflus. Domaine régulé → traçabilité des contraintes
   non négociable. Signaler sur-formalisation et sous-formalisation.

## Notes mécaniques (section de queue, ne pilotent pas le verdict)

Dérive de glossaire (casse, pluriel, synonymes), continuité des IDs (trous, doublons,
cross-refs cassées), aller-retour de l'index des hypothèses (chaque `[HYPOTHESE]` inline
est indexé et vice versa), protagoniste nommé par UJ, sections requises présentes pour
les enjeux et le type de produit.

## Restitution

Verdict global en 2-3 phrases, puis par dimension un verdict + findings au format :
`- [critique|haut|moyen|bas] Titre (§ localisation) - note. Correctif : ...`
Écrire des findings seulement là où ils ajoutent de l'information.
