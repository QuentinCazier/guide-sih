# Panorama du SIH

## Ce qu'on appelle SIH

Le système d'information hospitalier est l'ensemble des logiciels, des flux et
des données qui font fonctionner un établissement de santé. Dans un centre
hospitalier de taille moyenne, on compte couramment entre 100 et 300
applications, dont une dizaine structurantes, reliées par des centaines
d'interfaces. Un CHU dépasse souvent le millier d'applications.

Ce n'est pas un produit : c'est un assemblage, construit sur vingt ou trente
ans, de logiciels d'éditeurs différents, de développements internes et de
services nationaux, qui doit fonctionner 24 heures sur 24.

## Les grands domaines

| Domaine | Ce qu'il couvre | Logiciels typiques |
|---|---|---|
| Gestion administrative du patient | identité, séjours, mouvements, droits, facturation, recouvrement | GAM, gestion des droits AMO et AMC, facturation |
| Production de soins | dossier médical et de soins, prescription, plan de soins, blocs, urgences, réanimation | DPI, logiciels spécialisés par service |
| Plateaux médico-techniques | laboratoire, imagerie, anatomopathologie, pharmacie, stérilisation | SIL, RIS et PACS, logiciel de pharmacie |
| Information médicale et pilotage | codage PMSI, groupage, contrôle de gestion, tableaux de bord, entrepôt de données | outils DIM, groupeur, décisionnel |
| Gestion économique, financière et logistique | comptabilité, achats, stocks, biomédical, restauration | GEF, GMAO, logistique |
| Ressources humaines | paie, carrières, temps de travail, formation | SIRH, gestion du temps |
| Infrastructure et sécurité | annuaire, postes, réseau, identités, habilitations, sauvegardes, supervision | Active Directory, SSO, EAI, supervision |
| Services nationaux et régionaux | identité nationale, DMP, messagerie sécurisée, répertoires, plateformes régionales | INSi, DMP, MSSanté, RPPS, ROR, e-parcours |

## Les acteurs qui fixent les règles

Comprendre qui publie quoi évite de chercher une norme au mauvais endroit.

| Acteur | Rôle pour le SIH | Ce qu'il publie |
|---|---|---|
| **ANS** (Agence du Numérique en Santé) | référentiels d'interopérabilité et de sécurité, services socles | CI-SIS, MOS et NOS, référentiel INS, PGSSI-S, Pro Santé Connect, MSSanté, FINESS, RPPS, annuaire santé, Ségur numérique |
| **ATIH** (Agence technique de l'information sur l'hospitalisation) | information médicale, financement à l'activité | formats PMSI, CIM-10 FR à usage PMSI, fonction groupage, tarifs GHS, DRUIDES, ScanSanté |
| **CNAM** (Assurance Maladie) | droits, remboursement, nomenclatures tarifaires | CCAM, NGAP, NABM, LPP, normes B2 et NOEMIE, téléservices INSi et CDRi, ameli |
| **Ministère de la Santé** (DGOS, DREES, DNS) | politique publique, financement, statistiques, stratégie numérique | arrêtés tarifaires, programmes (Ségur, HOP'EN, SIMPHONIE), SAE, FINESS historiquement |
| **HAS** (Haute Autorité de santé) | qualité et certification des établissements | référentiel de certification, dont des exigences sur le SIH et l'identitovigilance |
| **CNIL** | protection des données personnelles | référentiels et recommandations pour les traitements de données de santé |
| **ANSM** | médicaments et dispositifs | base de données publique des médicaments |
| **ARS** (agences régionales de santé) | autorisations, financement régional, GRADeS | autorisations d'activité (visibles dans FINESS), programmes régionaux |
| **DGFiP** | comptabilité publique | protocole PES, application Hélios, Chorus Pro |

## Les programmes nationaux qui structurent les projets

- **Ségur du numérique en santé** (depuis 2021) : financement de la mise à
  niveau des logiciels par « couloirs » (hôpital, médecine de ville, biologie,
  radiologie, médico-social, officine), sur des exigences précises :
  INS, DMP, MSSanté, Pro Santé Connect, formats CI-SIS. Les éditeurs font
  « référencer » leurs logiciels ; les établissements commandent les
  mises à jour via le dispositif SONS (système ouvert et non sélectif).
- **HOP'EN** (2019 à 2023) puis les feuilles de route successives : objectifs
  d'usage (DPI, prescription, dossier de spécialité, échanges avec la ville).
- **SIMPHONIE** : simplification du parcours administratif et de la
  facturation (dont ROC, FIDES, dématérialisation du paiement).
- **CaRE** (cybersécurité accélération et résilience des établissements,
  depuis 2023) : financement de la sécurité, exercices de crise, audits.
- **Mon espace santé** (2022) : espace numérique de chaque assuré, qui
  contient le DMP et une messagerie ; les établissements l'alimentent.

## Le territoire : GHT et convergence

Depuis 2016, les établissements publics sont regroupés en **GHT**
(groupements hospitaliers de territoire), avec un établissement support qui
porte le SIH pour le groupement. La « convergence » des SIH, c'est-à-dire le
passage à des logiciels communs (au moins la GAM et le DPI), est l'un des
grands chantiers de la décennie. Concrètement : des projets de migration, des
reprises de données, des identités de patients à rapprocher entre
établissements, des structures (UF, pôles) à harmoniser.

Les 135 GHT et leurs membres sont visibles dans les données FINESS (voir
[Données publiques](donnees-publiques.md)).

## Pourquoi c'est compliqué

- **Le poids de l'existant.** Des flux conçus dans les années 1990 (fichiers
  plats, formats à longueur fixe) coexistent avec des API REST récentes.
- **La réglementation change chaque année.** Tarifs, formats PMSI,
  nomenclatures, règles de facturation : une partie du code d'un hôpital doit
  être mise à jour chaque premier mars ou premier janvier.
- **La continuité de service.** On ne coupe pas les urgences pour une mise en
  production. Les fenêtres de maintenance sont rares et négociées.
- **La donnée est sensible.** Données de santé au sens du RGPD, secret
  médical, exigences d'hébergement (HDS) et de traçabilité.
- **Beaucoup d'acteurs.** Éditeurs, DSI, DIM, direction des finances, bureau
  des entrées, soignants, ARS, caisses : chaque flux a plusieurs propriétaires.

## Ce que ça change dans votre code

- Cherchez toujours **qui est la source de vérité** d'une donnée avant de la
  stocker : l'identité vient de la GAM, la structure du référentiel de
  structure, les codes des nomenclatures officielles.
- Prévoyez que **les règles et les tables changent à date fixe** : versions,
  dates d'effet, rechargement sans redéploiement.
- Écrivez pour une **exploitation 24 heures sur 24** : reprise après incident,
  rejeu des messages, journalisation utile.
- Ne travaillez jamais avec des **données réelles** hors des environnements
  prévus pour cela. Fabriquez des jeux de test.

## Pour aller plus loin

- ANS, [Cadre d'interopérabilité des systèmes d'information de santé](https://esante.gouv.fr/interoperabilite/ci-sis)
- ATIH, [site institutionnel](https://www.atih.sante.fr/)
- Ministère de la Santé, [Ségur du numérique en santé](https://esante.gouv.fr/segur)
