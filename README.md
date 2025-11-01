# 🌿🚲 Visualisation Power BI – Arbres plantés à Paris & Taux d’occupation Vélib’ Métropole

## 🧭 Contexte du projet

Ce projet de visualisation a pour objectif de **croiser et analyser deux jeux de données open data parisiens** :  
1. Les **arbres plantés par projet** dans Paris, disponibles sur [opendata.paris.fr](https://opendata.paris.fr/explore/dataset/arbres-plantes-par-projet/information/).  
2. Les **stations du service Vélib’ Métropole**, via l’API [Vélib’ Open Data](https://www.velib-metropole.fr/donnees-open-data-gbfs-du-service-velib-metropole).  

L’objectif global est de **valoriser la donnée urbaine** en combinant des informations **environnementales et de mobilité douce**, grâce à un **tableau de bord interactif Power BI**.

---

## 🎯 Objectifs

- Visualiser la **répartition des arbres plantés** à Paris selon les projets, arrondissements et années.  
- Analyser la **disponibilité et le taux d’occupation** des stations Vélib’ par zone géographique.  
- Fournir des **indicateurs de performance (KPI)** en temps réel sur la mobilité verte.  
- Intégrer des **liens géographiques dynamiques** (Google Maps) pour naviguer directement vers les stations et localisations.

---

## 📊 Tableau de bord Power BI

Le tableau de bord est conçu autour de deux volets :

### 🌳 Volet 1 : Arbres plantés à Paris
- Nombre total d’arbres plantés par **projet**, **arrondissement**, **année**.  
- Répartition par **espèce** et **type de plantation**.  
- Visualisation géographique sur carte (coordonnées GPS).  

### 🚴 Volet 2 : Stations Vélib’ Métropole
- **Nombre de vélos disponibles**, **bornettes libres** et **taux d’occupation** par station.  
- Distinction entre **vélos mécaniques et électriques**.  
- **Carte interactive** des stations avec lien direct vers **Google Maps**.  
- Analyse de la **capacité totale du réseau** et de la **disponibilité moyenne par zone**.

---

## 🧮 Calculs clés (KPI & DAX)

### 🟩 Taux d’occupation Vélib’
Mesure la part des bornettes actuellement occupées par des vélos :

```DAX
Taux_occupation (%) =
DIVIDE(
    SUM('station_status'[numBikesAvailable]),
    SUM('station_information'[capacity])
)
