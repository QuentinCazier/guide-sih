# Contribuer

Ce guide vit de retours de terrain. Trois façons d'aider :

- **Signaler une erreur ou une imprécision** : ouvrez un ticket en citant la
  page, le passage, et si possible la source officielle qui vous donne raison.
- **Proposer un complément** : un sigle absent du glossaire, un flux non
  décrit, une règle qui a changé. Une proposition de modification directe sur
  le fichier Markdown est bienvenue.
- **Relire** : les chapitres sont écrits pour être compris sans connaissance
  préalable ; si un passage vous a perdu, dites-le.

## Règles éditoriales

- **Sources officielles.** Une affirmation réglementaire ou tarifaire renvoie
  à l'ANS, l'ATIH, l'Assurance Maladie, Légifrance ou un texte publié. Les
  dates et les versions sont précisées ; quand une règle est en cours de
  changement, on le dit.
- **Aucune donnée réelle.** Identités, numéros, établissements et messages
  d'exemple sont fictifs. Aucune capture d'écran de logiciel en production.
- **Pas de documentation d'éditeur.** On décrit les fonctions et les normes,
  pas les produits. Un nom de produit peut être cité pour orienter, sans
  jugement.
- **Point de vue du développeur.** Chaque chapitre se termine par ce que le
  sujet change dans le code.
- **Style.** Français, sigles développés à la première occurrence de chaque
  chapitre, phrases courtes, pas de tiret cadratin ; utiliser « : », une
  virgule ou des parenthèses.
- **Schémas** en Mermaid, dans le Markdown, pour rester lisibles sur GitHub.

## Prévisualiser

```bash
python -m venv .venv
.venv/bin/pip install -r requirements.txt
.venv/bin/mkdocs serve
```

## Licence

En contribuant, vous acceptez que votre contribution soit publiée sous la
licence du guide (CC BY 4.0).
