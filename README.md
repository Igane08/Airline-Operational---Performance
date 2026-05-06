# ✈️ Analyse de la Performance Opérationnelle des Routes Aériennes (USA - Janvier 2016)

## 📌 Présentation du Projet
Ce projet propose une approche hybride combinant **l'Analyse Statistique & le Machine Learning (Python)** et la **Business Intelligence (Power BI)** pour évaluer la ponctualité du trafic aérien américain (données du Bureau of Transportation Statistics - BTS).

L'objectif est d'identifier les routes aériennes "à risque", d'automatiser leur classification opérationnelle et de fournir un outil d'aide à la décision pour les planificateurs de réseau (*Network Planners*).

---

## 📊 Aperçu du Dashboard Power BI
*Une analyse visuelle interactive pour piloter la performance globale.*

![Dashboard Screenshot](images/dashboard_screenshot.png)

---

## 🛠️ Architecture des Données (Modèle à 8 Tables)
L'analyse repose sur un modèle de données structuré en étoile (Star Schema) combinant :
* **Table de Faits :** `On_Time_On_Time_Performance_2016_1` (échantillonnée à 100 000 lignes pour des performances fluides).
* **Tables de Dimensions (7) :** `L_AIRPORT_ID`, `L_AIRLINE_ID`, `L_WEEKDAYS`, `L_MONTHS`, `L_DISTANCE_GROUP_250`, `L_STATE_ABR_AVIATION`, `L_CITY_MARKET_ID`.

---

## 🐍 Partie 1 : Analyse Scientifique (Python)
L'analyse sous Python (`notebooks/Airline_Analysis.ipynb`) répond aux questions clés de la performance :
* **Calcul d'un Route Risk Score :** Indice combinant le taux de retard, la durée des retards et le taux d'annulation par liaison.
* **Clustering K-Means (Apprentissage non supervisé) :** Segmentation automatique de toutes les routes en 3 catégories de performance :
  1. **High Performance** (Routes fluides et fiables)
  2. **Medium Performance** (Routes moyennement perturbées)
  3. **At-Risk** (Routes hautement prioritaires nécessitant une réoptimisation des créneaux)
* **Analyses de corrélations :** Impact de la distance sur les retards au départ et à l'arrivée.

---

## 📈 Partie 2 : Business Intelligence (Power BI)
Le rapport interactif (`dashboard/Airline_Performance.pbix`) permet de :
* Suivre en temps réel les indicateurs clés de performance (KPIs) : taux de retard moyen, taux d'annulation, volume de vols.
* Cartographier les flux de retards à travers les États-Unis.
* Comparer la compétitivité et la ponctualité de différentes compagnies aériennes sur les mêmes liaisons critiques.
