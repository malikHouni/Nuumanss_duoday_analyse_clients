# DuoDay 2026 — Analyse des données clients Nuumanss

## Présentation du projet

Ce projet a été réalisé le **19 novembre 2026**, dans le cadre du **DuoDay**, par **Thao Pham et Malik Houni**.

L'objectif de cette demi-journée était de découvrir les différentes étapes d'un projet de Data Analysis, depuis la récupération des données via une API jusqu'à leur exploration et leur interprétation.

L'étude repose sur les données de **Nuumanss**, une entreprise fictive évoluant dans le domaine de l'expertise comptable.

> **Important :** toutes les données utilisées sont fictives. Cette analyse ne représente ni les pratiques ni les processus réels d'une entreprise ou d'un cabinet comptable.

## Objectifs

- Découvrir le fonctionnement d'une API et récupérer des données.
- Manipuler des fichiers JSON et CSV.
- Explorer les données avec SQL et DuckDB.
- Étudier la répartition géographique du portefeuille clients.
- Identifier les anomalies et problèmes de qualité des données.
- Formuler des recommandations à partir des résultats obtenus.

## Technologies et outils

| Technologie | Utilisation |
|---|---|
| Python | Téléchargement et préparation des données |
| API REST Nuumanss | Récupération des données fictives |
| JSON / CSV | Formats des données |
| DuckDB / SQL | Exploration et analyse |
| DataKonsul | Présentation et génération du rapport d'analyse |

## Sources des données

Les données ont été récupérées depuis l'API Nuumanss :

`http://nuumanssapi.me.ht/api/v1/`

Plusieurs ressources ont été identifiées :

- Référentiel des clients.
- Données comptables.
- Factures mensuelles, notamment celles de janvier 2024.
- Données externes complémentaires.

L'analyse présentée dans le rapport s'est principalement concentrée sur le **référentiel clients, la qualité des identifiants et la répartition géographique**.

## Résultats de l'analyse

### 1. Des problèmes de duplication dans le référentiel clients

L'exploration des données a révélé un premier problème important.

| Indicateur | Résultat |
|---|---:|
| Nombre de lignes clients | 8 122 |
| Nombre de clients uniques identifiés | 4 367 |
| Écart constaté | 3 755 |
| Part de lignes excédentaires | 46,2 % |

Le nombre de lignes dépasse fortement celui des clients uniques.

**Constat :** des identifiants clients apparaissent plusieurs fois dans le référentiel.

Il est nécessaire de vérifier la cause de ces duplications avant d'effectuer des analyses commerciales ou financières.

### 2. Répartition géographique des clients

L'analyse a également porté sur les villes présentes dans le référentiel.

Quelques résultats observés :

| Ville | Nombre d'occurrences |
|---|---:|
| Lyon | 3 533 |
| Villeurbanne | 294 |
| LYON | 262 |
| Montluel | 207 |
| Oullins | 193 |

Ces résultats montrent une forte présence apparente à Lyon, mais révèlent également des incohérences de saisie.

Par exemple, **« Lyon » et « LYON » sont comptabilisés séparément**, alors qu'ils désignent la même ville.

Une normalisation des libellés est donc indispensable pour mesurer correctement la répartition géographique du portefeuille.

### 3. Identifier les zones moins représentées

L'étude a également identifié plusieurs communes présentant un faible nombre d'occurrences :

| Ville | Nombre d'occurrences |
|---|---:|
| Saint-Priest | 9 |
| Villefranche-sur-Saône | 13 |
| Décines | 15 |
| Caluire | 16 |
| Decines | 17 |

Ces données constituent une première piste de réflexion pour identifier des zones de prospection commerciale.

Toutefois, les différences d'orthographe et les doublons doivent être corrigés avant de pouvoir établir un classement fiable.

### 4. Incohérences sur les raisons sociales

Certaines raisons sociales apparaissent de nombreuses fois dans les données :

- Du Parc : 113 occurrences.
- Bellevue : 98 occurrences.
- Les Tilleuls : 95 occurrences.
- Les Acacias : 93 occurrences.
- Les Cèdres : 83 occurrences.

On retrouve également des différences de casse, comme « Bellevue » et « BELLEVUE ».

Ces répétitions nécessitent des contrôles complémentaires : une raison sociale identique ne suffit pas à démontrer qu'il s'agit du même client.

## Recommandations

À l'issue de l'analyse, plusieurs recommandations ont été formulées :

**1. Améliorer la qualité du référentiel**

Vérifier les identifiants clients, comprendre l'origine des duplications et mettre en place des contrôles d'unicité adaptés.

**2. Sécuriser les analyses de facturation**

Vérifier les correspondances entre les factures et les identifiants clients afin de détecter d'éventuelles anomalies ou situations de double facturation.

**3. Normaliser les informations géographiques**

Uniformiser les noms des villes afin de produire des statistiques territoriales fiables.

**4. Identifier les opportunités commerciales**

Après fiabilisation des données, étudier les zones géographiques moins représentées pour évaluer leur potentiel de développement commercial.

## Conclusion

Cette demi-journée a permis de mettre en évidence un enseignement essentiel en Data Analysis :

**La qualité des données est une condition préalable à la fiabilité des analyses et des recommandations métier.**

Avant de produire des indicateurs ou de proposer des actions commerciales, il est nécessaire de vérifier la cohérence des données, l'unicité des identifiants et la fiabilité des sources.

Ce projet constitue une première approche concrète des différentes étapes du métier de Data Analyst : collecte, exploration, contrôle qualité, interprétation et recommandations.

---

**Projet réalisé par Thao Pham et Malik Houni — DuoDay, 19 novembre 2026.**

*Analyse réalisée sur des données entièrement fictives.*
