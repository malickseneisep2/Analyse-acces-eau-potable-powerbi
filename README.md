# 🌍 Analyse de l’accès à l’eau potable et aux services WASH  
**Projet Power BI — Analyse multi-échelles (Monde, Continent, Pays)**

🔗 **Lien vers le rapport Power BI déployé**  
👉 **[Accéder au rapport interactif](https://app.powerbi.com/view?r=eyJrIjoiOGQ0YjFjZDgtNzBiMy00NjAwLWI3MmUtNGE4YWE5MjM2MTk3IiwidCI6ImY3MGEwYTg4LTJhMzctNGYxYS04OGYyLWFiZGIxNzMwM2MwZiIsImMiOjN9)**

---

## 📌 Contexte du projet

Ce projet a été réalisé dans le cadre du **cours de Big Data et Cloud Computing**.  
Il vise à analyser l’accès à l’eau potable et aux services **WASH** (*Water, Sanitation and Hygiene*) à différentes échelles géographiques, en mobilisant des outils de traitement de données, de modélisation et de visualisation sous **Power BI**.

L’accès à l’eau potable constitue un enjeu majeur de santé publique et de développement durable. Ce travail met en évidence les disparités territoriales et les liens entre accès à l’eau, démographie, mortalité liée aux services WASH et stabilité politique.

---

## 🎯 Objectifs

Les principaux objectifs du projet sont :

- analyser la répartition de la population selon le niveau d’accès à l’eau potable ;
- comparer les situations entre continents et entre pays ;
- étudier les différences entre zones urbaines et rurales ;
- explorer les relations entre accès à l’eau, mortalité WASH et stabilité politique ;
- proposer un tableau de bord interactif permettant une analyse multi-niveaux.

---

## ❓ Questions d’analyse

- Comment se répartit la population mondiale selon le niveau d’accès à l’eau potable ?
- Quelles disparités observe-t-on entre continents ?
- Les zones urbaines bénéficient-elles systématiquement d’un meilleur accès ?
- Existe-t-il un lien entre instabilité politique et faiblesse de l’accès à l’eau ?
- Comment la mortalité liée aux services WASH varie-t-elle selon les territoires ? ...

---

## 🧾 Données utilisées

Les données proviennent de sources internationales (FAO, OMS) et sont organisées selon une logique décisionnelle.

### Tables de faits
- **Population** : population totale, urbaine et rurale par pays et par année  
- **ServicesEau_Base_Safe** :  
  - accès à l’eau potable de base  
  - accès à des services gérés en toute sécurité  
- **Taux de mortalité associé à l’eau (WASH)**  
- **Stabilité politique**

### Tables de dimensions
- **Continent–Pays** : correspondance pays ↔ continent  
- **DimDate** : dimension temporelle (année)  
- **DimDécoupage** : Total / Urbain / Rural  
- **Tables de paramètres** : sélection dynamique des indicateurs dans les visuels

---

## 🧹 Préparation et traitement des données

Les transformations ont été réalisées dans **Power Query** et incluent :

- promotion des en-têtes ;
- nettoyage des textes (espaces, casse, harmonisation des noms) ;
- conversion des variables numériques importées en texte  
  (problème de séparateur décimal anglais/français) ;
- remplacement des séparateurs décimaux avant conversion en numérique ;
- suppression des doublons ;
- harmonisation des catégories (TOTAL, URBAN, RURAL) ;
- création de variables catégorielles (catégories de performance d’accès à l’eau).

Toutes les transformations sont documentées via les *Étapes appliquées* de Power Query.

---

## 🧠 Modélisation des données

Le modèle repose sur une **architecture en constellation** :

- tables de faits au centre (population, accès à l’eau, mortalité, stabilité politique) ;
- tables de dimensions partagées (pays, continent, année, découpage).

Ce choix permet :
- une meilleure lisibilité du modèle ;
- de bonnes performances ;
- la mise en place d’analyses hiérarchiques (*drill-down*).

---

## 📐 Mesures et calculs (DAX)

Des mesures DAX ont été développées pour :

- population mondiale, continentale et nationale ;
- taux d’accès à l’eau potable (base et gestion sûre) ;
- taux de population urbaine ;
- nombre de décès liés aux services WASH ;
- indicateurs globaux ;
- analyses temporelles basées sur `DimDate`.

Des fonctions ont été mobilisées comme :
`CALCULATE`, `FILTER`, `KEEPFILTERS`, `TREATAS`, paramètres dynamiques.

---

## 📊 Structure du rapport Power BI

### 🌐 Vue Monde
- indicateurs globaux clés (KPI) ;
- carte mondiale interactive avec choix dynamique de l’indicateur ;
- évolution temporelle des indicateurs ;
- relation entre accès à l’eau, mortalité WASH et stabilité politique.

### 🌍 Vue Continent
- comparaison entre continents ;
- répartition de la population par catégories d’accès à l’eau ;
- analyses intra-continentales ;
- *drill-down* vers le niveau pays.

### 🏳️ Vue Pays
- analyse détaillée par pays ;
- filtres (année, découpage, continent, stabilité politique) ;
- graphiques thématiques répondant aux domaines d’analyse du TDR.

---

## 🚀 Fonctionnalités avancées

- drill-down et drill-up hiérarchiques ;
- paramètres dynamiques pour changer l’indicateur affiché ;
- filtres conditionnels numérique (ex. stabilité politique) ;
- gestion fine des interactions entre visuels ;
- tableau de bord interactif et exploratoire.

---

## 🧑‍🤝‍🧑 Équipe

Projet réalisé par une équipe de **quatre étudiants** :

- Mamady I BERETE
- Jacques ILLY 
- Malick SENE  
- NGUEMFOUO NGOUMTSA Célina
- Dior MBENGUE

---

## 🛠️ Outils utilisés

- Power BI Desktop et Service  
- Power Query  
- DAX  
- Git & GitHub  

---

## 📄 Licence

Projet réalisé à des fins **académiques et pédagogiques**, dans le cadre du cours **Big Data et Cloud Computing**.
