# Le SIH pour les développeurs

Vous arrivez sur un projet dans un hôpital. En réunion, on parle de GAM, d'UF,
de mouvements, de PMSI, de flux B2, de retours NOEMIE, d'INS, de Ségur. Tout le
monde a l'air de comprendre. Personne ne vous explique, et la documentation
qu'on vous transmet est soit un manuel d'éditeur, soit un texte réglementaire.

Ce guide explique le **système d'information hospitalier** (SIH) français du
point de vue de quelqu'un qui doit écrire du code qui s'y branche : quels sont
les logiciels, ce qu'ils s'échangent, quels identifiants et quelles
nomenclatures circulent, qui décide des règles, et ce que tout cela change
dans votre code.

## Pour qui

- Développeuses et développeurs qui rejoignent une DSI hospitalière, un
  éditeur de logiciel de santé, une start-up qui s'interface avec l'hôpital,
  une équipe data.
- Chefs de projet, product owners et étudiants qui veulent une carte avant
  d'ouvrir les spécifications.

Aucune connaissance médicale ni hospitalière n'est supposée. Une familiarité
avec les notions de base du développement (API, fichiers plats, bases de
données) suffit.

## Ce que ce guide n'est pas

- Pas un cours de gestion hospitalière : on explique le fonctionnement
  administratif et médical seulement quand il éclaire les systèmes.
- Pas une documentation d'éditeur : les logiciels sont décrits par fonction,
  pas par produit.
- Pas une source réglementaire : chaque chapitre renvoie vers les textes et
  les publications officielles (ANS, ATIH, Assurance Maladie, Légifrance), qui
  font foi. Les dates et les règles évoluent vite ; vérifiez toujours la
  version en vigueur.

## Comment lire

Commencez par [Un séjour vu par les systèmes](parcours.md) : on suit une
patiente de son arrivée aux urgences jusqu'au paiement de la facture, et l'on
nomme au passage chaque brique, chaque flux, chaque nomenclature. Les chapitres
suivants reprennent chaque sujet en profondeur, avec à chaque fois une section
**Ce que ça change dans votre code**.

Le [glossaire](glossaire.md) donne une définition courte de chaque sigle.

## Conventions

- Les sigles sont développés à leur première apparition dans chaque chapitre.
- Les schémas sont des diagrammes Mermaid : ils se lisent aussi dans le
  dépôt GitHub.
- Les exemples de données sont fictifs. Aucune donnée réelle de patient, de
  professionnel ou d'établissement identifiable n'apparaît ici, et les
  contributions doivent respecter cette règle.

## Contribuer

Une erreur, une imprécision, un sigle manquant, un retour d'expérience de
terrain : ouvrez un ticket ou une proposition de modification sur
[le dépôt GitHub](https://github.com/QuentinCazier/guide-sih). Le contenu est
publié sous licence [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/deed.fr) :
vous pouvez le reprendre, le modifier et le rediffuser en citant la source.
