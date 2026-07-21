# Connecteurs

Le plugin est conçu pour un usage interne Mayday : les outils sont nommés en dur. Ce
document récapitule les connecteurs utilisés, à quelle phase, et s'ils sont requis.

| Usage | Connecteur | Phase(s) | Requis ? |
|---|---|---|---|
| Base des entretiens de discovery | Notion (base dédiée) | 0, 1 | Recommandé (source principale des interviews) |
| Transcripts de meetings | Granola | 0, 1 | Optionnel |
| Analytics produit | Amplitude EU | 1 | Optionnel (pour quantifier les signaux) |
| Restitution des livrables | Fichiers `.md` locaux + Notion | 1 à 5 | Fichiers toujours ; Notion si voulu |
| User stories vers issues | Linear | 3 | Optionnel |
| Version mise en forme du one-pager | docx (skill) | 5 | Optionnel |

## Autorisation

Pour que ces connecteurs fonctionnent, ils doivent être autorisés côté réglages de
connecteurs claude.ai. Si un connecteur n'est pas autorisé, le plugin le signale et
continue avec les notes / contenus fournis manuellement. Il ne bloque jamais un
workflow sur un connecteur manquant.

## Réutilisation hors Mayday

Ce plugin est calibré pour Mayday (contexte produit et outils nommés). Pour le réutiliser
dans une autre équipe, remplacer les outils de ce tableau par leurs équivalents
(par exemple une autre base documentaire à la place de Notion, un autre outil
d'analytics à la place d'Amplitude EU, un autre tracker à la place de Linear) et adapter
la section « Contexte Mayday » de `shared/conventions.md`.
