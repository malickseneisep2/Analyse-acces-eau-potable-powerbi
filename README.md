---
title: "🌍 Analyse de l’accès à l’eau potable et aux services WASH"
subtitle: "Projet Power BI — Analyse multi-échelles (Monde, Continent, Pays)"
author: "Projet académique – Analyse de données"
date: "`r Sys.Date()`"
output:
  html_document:
    toc: true
    toc_depth: 3
    number_sections: true
    theme: flatly
---

# Contexte et objectifs du projet

L’accès à l’eau potable et aux services **WASH** (*Water, Sanitation and Hygiene*) constitue un enjeu central de santé publique et de développement durable.  
Ce projet vise à analyser, visualiser et comparer les niveaux d’accès à l’eau potable à l’échelle mondiale, continentale et nationale.

L’objectif est double :

- produire un **diagnostic global et comparatif** des niveaux d’accès à l’eau potable ;
- aller au-delà d’une simple description en mettant en relation l’accès à l’eau avec des variables démographiques et institutionnelles.

# Questions d’analyse

Les principales questions traitées dans ce projet sont :

- Comment se répartit la population mondiale selon le niveau d’accès à l’eau potable ?
- Quelles disparités observe-t-on entre continents ?
- Comment l’accès à l’eau diffère-t-il entre zones urbaines et rurales ?
- Existe-t-il un lien entre accès à l’eau, mortalité liée aux services WASH et stabilité politique ?
- Les pays politiquement instables présentent-ils des niveaux d’accès plus faibles ?

# Données utilisées

Les données proviennent de sources internationales (Banque mondiale, OMS) et sont organisées en tables de faits et de dimensions.

## Tables de faits

- **Population**  
  Population totale, urbaine et rurale par pays et par année.

- **ServicesEau_Base_Safe**  
  Taux d’accès à l’eau potable :
  - niveau de base,
  - services gérés en toute sécurité.

- **Taux de mortalité associé à l’eau**  
  Décès attribués à l’exposition à des services WASH non sûrs.

- **Stabilité politique**  
  Indicateur synthétique de stabilité politique par pays et par année.

## Tables de dimensions

- **Continent-pays** : correspondance pays ↔ continent.
- **DimDate** : dimension temporelle (année).
- **DimDécoupage** : Total / Urbain / Rural.
- **Tables de paramètres** : sélection dynamique des indicateurs dans les visuels.

# Préparation et traitement des données (Power Query)

Les traitements réalisés incluent :

- promotion des en-têtes ;
- nettoyage des variables textuelles (espaces, casse, harmonisation des noms) ;
- conversion des variables numériques importées en texte  
  (problème de séparateur décimal anglais/français) ;
- suppression des doublons ;
- harmonisation des catégories (TOTAL, URBAN, RURAL) ;
- création de variables catégorielles (catégories de performance d’accès à l’eau).

L’ensemble des transformations est traçable via les *Étapes appliquées* dans Power Query.

# Modélisation des données

Le modèle repose sur une **architecture en étoile** :

- les tables de faits (population, accès à l’eau, mortalité, stabilité politique) ;
- reliées à des dimensions communes (pays, continent, année, découpage).

Ce choix garantit :

- une lecture claire du modèle ;
- de bonnes performances ;
- la possibilité d’analyses hiérarchiques (*drill-down*).

# Mesures DAX principales

Plusieurs mesures DAX ont été développées :

- population mondiale et continentale ;
- taux d’accès à l’eau potable (base et gestion sûre) ;
- taux de population urbaine ;
- nombre de décès WASH ;
- indicateurs globaux pondérés ;
- mesures dynamiques via paramètres.

Des fonctions avancées ont été utilisées :

- `CALCULATE`, `FILTER`, `KEEPFILTERS` ;
- `TREATAS` pour gérer des relations analytiques complexes ;
- mesures temporelles basées sur `DimDate`.

# Structure du rapport Power BI

Le rapport est structuré en trois vues complémentaires.

## Vue Monde

- indicateurs globaux clés (cartes KPI) ;
- carte mondiale interactive avec sélection dynamique de l’indicateur ;
- analyses temporelles ;
- visualisation des relations entre accès à l’eau, mortalité WASH et stabilité politique.

## Vue Continent

- comparaison entre continents ;
- répartition de la population par catégories d’accès à l’eau ;
- analyse des disparités intra-continentales ;
- *drill-down* du continent vers les pays.

## Vue Pays

- analyse détaillée par pays ;
- filtres avancés (année, découpage, continent, stabilité politique) ;
- visualisations liées aux domaines d’analyse (ex. urbanisation, création de services) ;
- graphiques orientés aide à la décision.

# Fonctionnalités avancées

Le rapport intègre plusieurs fonctionnalités avancées :

- *drill-down* et *drill-up* hiérarchiques ;
- paramètres dynamiques pour changer l’indicateur affiché ;
- filtres intelligents (stabilité politique, découpage) ;
- contrôle fin des interactions entre visuels ;
- mise en forme cohérente et lisible.

# Rapport interactif déployé

Le rapport Power BI a été déployé en ligne.

**Lien d’accès :**  
👉 **[Rapport Power BI – Accès à l’eau et services WASH](À_REMPLACER_PAR_VOTRE_LIEN)**

# Outils utilisés

- Power BI Desktop  
- Power Query  
- DAX  
- Git et GitHub  

# Auteur

Projet réalisé dans un cadre académique, à des fins d’analyse de données, de visualisation et de montée en compétences sur Power BI.

# Licence

Projet à usage **académique et pédagogique**.
