# Données publiques

> Dernière vérification des sources : 11 septembre 2026. Les règles et les
> tarifs cités évoluent chaque année ; les liens en fin de chapitre font foi.

Une grande partie des référentiels du SIH est publique. Savoir où les
trouver, sous quelle licence et dans quel format évite bien des heures.

## Les sources

| Source | Contenu | Format | Licence | Fréquence |
|---|---|---|---|---|
| [FINESS+](https://www.data.gouv.fr/datasets/finess-structures-1) (ANS, data.gouv.fr) | entités juridiques, établissements, groupements (dont les GHT), activités autorisées et capacités | JSON compressé, schéma publié sur GitHub | Licence Ouverte 2.0 | quotidienne |
| [Annuaire santé, extractions RPPS](https://www.data.gouv.fr/datasets/annuaire-sante-extractions-des-donnees-en-libre-acces-des-professionnels-intervenant-dans-le-systeme-de-sante-rpps) (ANS) | professionnels de santé en libre accès : identité professionnelle, exercice, structures | fichiers texte volumineux | Licence Ouverte 2.0, données personnelles à traiter comme telles | quotidienne |
| [NOS](https://mos.esante.gouv.fr/NOS/) (ANS) | toutes les tables de codes de l'interopérabilité | tabs, XML, FHIR | conditions de l'ANS | mensuelle |
| [Tarifs MCO et HAD](https://www.atih.sante.fr/tarifs-mco-et-had) (ATIH) | tarifs GHS, GHT, suppléments par campagne | CSV ISO-8859-1 dans des archives | contenu des arrêtés tarifaires | annuelle |
| [ScanSanté](https://www.scansante.fr/) (ATIH) | activité hospitalière agrégée, indicateurs | consultation en ligne, exports | conditions ATIH | annuelle et périodique |
| [Base de données publique des médicaments](https://base-donnees-publique.medicaments.gouv.fr/) (ANSM) | médicaments, présentations, CIP, prix | fichiers texte | réutilisation libre avec mention de la source et de la date | régulière |
| [data.ameli.fr](https://data.ameli.fr/) (Assurance Maladie) | dépenses, effectifs, indicateurs, référentiels | CSV, API | ODbL pour la plupart | variable |
| [SNDS](https://www.snds.gouv.fr/) (Health Data Hub, CNAM) | données individuelles pseudonymisées de l'Assurance Maladie et du PMSI | accès sur autorisation | accès encadré par la loi | |
| [Légifrance](https://www.legifrance.gouv.fr/) | arrêtés tarifaires, codes, décrets | HTML, API | Licence Ouverte 2.0 pour les textes | |
| [INSEE, code officiel géographique](https://www.insee.fr/fr/information/2560452) | communes, départements, régions | CSV | Licence Ouverte 2.0 | annuelle |

## Points de vigilance

- **Licence Ouverte ne veut pas dire sans obligations** : citez la source et
  la date, ne dénaturez pas les données.
- **Données personnelles** : les extractions RPPS contiennent des noms de
  professionnels. Leur réutilisation reste soumise au RGPD.
- **Formats hostiles** : JSON de plusieurs centaines de Mo, CSV en
  ISO-8859-1 avec virgule décimale, XML SVS, PDF. Prévoyez une étape de
  conversion avant tout usage.
- **Ce qui n'est pas ouvert** : la CIM-10 (droits de l'OMS), les cahiers des
  charges B2 et NOEMIE (Assurance Maladie), certaines publications de l'ATIH.
  Téléchargez à la source, ne redistribuez pas.

## Outils libres liés à ce guide

Deux projets publiés sous licence libre par l'auteur de ce guide illustrent
ce qu'on peut construire avec ces données et ces contraintes :

- **referentiels-sante** : convertit FINESS+, les tables NOS, la CCAM, la
  CIM-10 FR, la base publique des médicaments, la NABM, la LPP, les UCD et les
  tarifs GHS en CSV et JSON propres, en une commande, sans dépendance. Il lit
  le flux FINESS+ de 750 Mo en flux, décode les tables dBase en page de code
  DOS de l'Assurance Maladie, et produit aussi le format de l'ancienne
  extraction FINESS pour les chaînes de traitement existantes.
  [github.com/QuentinCazier/referentiels-sante](https://github.com/QuentinCazier/referentiels-sante)
- **Registris** : registre des habilitations et coffre à preuves
  d'audit pour les établissements de santé, pour répondre aux contrôles
  (commissaires aux comptes, PGSSI-S) matricule par matricule.
  [github.com/QuentinCazier/registris](https://github.com/QuentinCazier/registris)

## Ce que ça change dans votre code

- **Automatisez la récupération** des référentiels avec leur date : un script
  daté vaut mieux qu'un fichier copié à la main dans le dépôt.
- **Conservez la version source** à côté des données converties, pour pouvoir
  expliquer un écart.
- **Testez sur les échantillons officiels** quand ils existent (l'ANS en
  publie pour FINESS+).
