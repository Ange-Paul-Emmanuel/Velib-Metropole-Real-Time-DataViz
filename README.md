# 🚴‍♂️ Vélib’ Métropole – Real-Time Data Visualization Dashboard (Power BI)

## 🧭 Contexte du projet

Ce projet a pour objectif de **concevoir un tableau de bord interactif Power BI** à partir des données ouvertes du service **Vélib’ Métropole**.  
L’analyse repose sur la **visualisation en temps réel** des **stations de vélos**, de leur **capacité**, et du **taux d’occupation** à travers la métropole parisienne.

L’ensemble des données provient de l’API officielle :
👉 [https://www.velib-metropole.fr/donnees-open-data-gbfs-du-service-velib-metropole](https://www.velib-metropole.fr/donnees-open-data-gbfs-du-service-velib-metropole)

---

## 🎯 Objectifs du projet

- Visualiser la **disponibilité des vélos** et des **bornettes libres** par station.  
- Calculer le **taux d’occupation** en temps réel.  
- Distinguer les **vélos mécaniques** et **électriques** disponibles.  
- Fournir une **expérience interactive** : carte, filtres, indicateurs dynamiques.  
- Intégrer un **lien direct vers Google Maps** pour localiser chaque station.  
- Expérimenter une approche de **Real-Time Data Visualization** dans Power BI à partir d’une API externe.

---

## 🧾 Données utilisées

Les données sont issues du **flux GBFS (General Bikeshare Feed Specification)**, un standard open data des systèmes de vélos partagés.  
Deux tables principales sont utilisées :

### 1. `station_information.json`
Contient les **informations statiques** des stations :
- `station_id` : identifiant unique  
- `name` : nom de la station  
- `lat`, `lon` : coordonnées géographiques  
- `capacity` : capacité totale (nombre d’emplacements)

### 2. `station_status.json`
Contient les **données dynamiques (temps réel)** :
- `station_id` : identifiant de la station  
- `numBikesAvailable` : vélos disponibles  
- `numDocksAvailable` : bornettes libres  
- `num_bikes_available_types` : distinction entre vélos mécaniques et électriques  
- `is_renting`, `is_returning` : statut opérationnel  
- `last_reported` : date de dernière mise à jour

---

## ⚙️ Traitements & Transformations (Power Query / M)

### 🔹 Étapes principales
1. **Connexion à l’API Vélib’** et import des fichiers `station_information.json` et `station_status.json`.  
2. **Fusion des deux tables** via `station_id` pour obtenir un modèle unique.  
3. **Nettoyage des données** (types, champs inutiles, renommage).  
4. **Création d’un lien Google Maps dynamique** :
   ```DAX
   Lien_Google_Maps =
   "https://www.google.com/maps?q=" &
   'station_information'[lat] & "," & 'station_information'[lon]
