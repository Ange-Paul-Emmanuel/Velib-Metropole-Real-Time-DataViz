# 🚴‍♂️ Vélib’ Métropole – Real-Time Data Visualization Dashboard (Power BI)

## Contexte du projet

Ce projet a pour objectif de **concevoir un tableau de bord interactif Power BI** à partir des données ouvertes du service **Vélib’ Métropole**.  
L’analyse repose sur la **visualisation en temps réel** des **stations de vélos**, de leur **capacité**, et du **taux d’occupation** à travers la métropole parisienne.

L’ensemble des données provient de l’API officielle :
[https://www.velib-metropole.fr/donnees-open-data-gbfs-du-service-velib-metropole](https://www.velib-metropole.fr/donnees-open-data-gbfs-du-service-velib-metropole)

---

## Objectifs du projet

- Visualiser la **disponibilité des vélos** et des **bornettes libres** par station.  
- Calculer le **taux d’occupation** en temps réel.  
- Distinguer les **vélos mécaniques** et **électriques** disponibles.  
- Fournir une **expérience interactive** : carte, filtres, indicateurs dynamiques.  
- Intégrer un **lien direct vers Google Maps** pour localiser chaque station.  
- Expérimenter une approche de **Real-Time Data Visualization** dans Power BI à partir d’une API externe.


---

   ## Visualisations dans Power BI

<img width="1487" height="839" alt="vélibs project" src="https://github.com/user-attachments/assets/cf5296d1-92ad-417d-9703-136e5b74191a" />


### Carte interactive
- Affiche la **localisation des stations** selon leur **taux d’occupation**.  
- **Code couleur** : du 🟢 vert (stations avec plus de vélos mécaniques disponibles) au 🔵 bleu (stations avec plus de vélos électriques disponibles).  
- **Interaction** : clic sur une station → ouverture directe de sa position sur **Google Maps**.  

---

### Indicateurs clés (KPI)
- **Taux d’occupation global et par station**  
- **Nombre total de vélos**  
- **Répartition des vélos mécaniques / électriques**   

---

### Filtres & segments
- **nom de station** et **type de vélo**.   
 

---

### Perspectives d’amélioration
- **Rafraîchissement automatique** via un **streaming dataset Power BI** pour un suivi en continu.  
- **Intégration de la météo** pour corréler la disponibilité avec les conditions climatiques.  
- **Visualisation temporelle** de l’évolution du taux d’occupation (par heure / jour).  
- **Déploiement public** du tableau de bord via **Power BI Service.**  

