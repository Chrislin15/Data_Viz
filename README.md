Projet Jeux Olympiques 

PRÉ-REQUIS : 

🧰 Bibliothèques utilisées : 

import pandas as pd
import json
import matplotlib.pyplot as plt
import seaborn as sns
import plotly.express as px

📦 Installation :

pip install pandas matplotlib seaborn plotly


INTRODUCTION : 

Ce projet a pour objectif l'extraction, le nettoyage, la transformation et la visualisation des données relatives aux Jeux Olympiques.
Les données ont été collectées à partir du site web Olympics Statistics et comprennent des informations sur les athlètes, les pays participants et les médailles obtenues par discipline sportive.

Le projet est structuré en plusieurs étapes successives :

- Collecte et extraction des données à l'aide de techniques de web scraping
- Nettoyage et transformation des données brutes
- Mise en forme des données dans un format structuré (JSON)
- Création de visualisations pour explorer les données


🕵️‍♂️ COLLECTE ET EXTRACTION DES DONNÉES :

Technologies utilisées :

🐍 Python : Langage de programmation principal
📚 BeautifulSoup4 : Parsing HTML pour extraire les données à partir des documents HTML
🌐 Requests : Envoi de requêtes HTTP pour récupérer les pages web

Processus d'extraction :

Le script collecte les informations des athlètes olympiques depuis le site olympics-statistics.com en suivant plusieurs étapes.

Structure du script :

📝 extract_basic_info()
Extraction des informations principales de chaque athlète, telles que prénom, nom, pays (identifié via les drapeaux), et sexe (déterminé par les icônes SVG).

🎖️ extract_medal_info()
Pour chaque athlète, récupération des détails sur les médailles (type et nombre) via des requêtes.

📄 get_athletes_from_page()
Coordonne l’extraction des athlètes sur une page donnée et gère la navigation entre les pages grâce à la pagination.

Processus global :

🔤 Itération alphabétique sur les noms des athlètes, incluant une catégorie spéciale pour les noms non alphabétiques.
🌍 Pour chaque lettre, visite des pages, extraction des données des athlètes, puis navigation entre les pages.
⏳ Application de délais entre les requêtes pour respecter la limitation du serveur.
📊 Enrichissement des données avec les médailles, puis sauvegarde finale au format JSON.


🧹 Nettoyage et Transformation des Données :

🌍 Normalisation des pays :

Un dictionnaire de correspondance (pays_dict) standardise les noms et codes ISO des pays afin de :

🔄 Harmoniser différentes appellations (ex. "Russia")
🏛️ Gérer les cas historiques ou spécifiques (ex. "Soviet Union")
🔍 Permettre une recherche bidirectionnelle entre noms et codes via un dictionnaire inversé (codes_pays_dict)

🔧 Transformation des données : 

🔢 Extraction des identifiants via expressions régulières à partir des URLs
🎨 Standardisation des médailles (conversion des codes numériques en noms explicites : or, argent, bronze
🌐 Uniformisation des URLs complètes pour garantir l’accès aux ressources

🗂️ Structure finale :

Les données nettoyées sont stockées sous un format JSON uniforme.


📊 Visualisation des Données

Les visualisations offrent une analyse complète des performances olympiques selon trois axes :

🏃 Athlètes : Analyse individuelle
🌎 Pays : Comparaison des médailles par pays
🏅 Sports : Analyse des disciplines et leurs résultats par pays


📷 Exemples de visualisations :



