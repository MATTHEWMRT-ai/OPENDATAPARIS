<p align="center">
  <img src="logo_pulse.png" alt="City Pulse Logo" width="150">
</p>

<h1 align="center">🌍 City Pulse</h1>

<p align="center">
  <strong>Le Tableau de Bord Intelligent des Villes (Open Data)</strong><br>
  Explorez, analysez et comprenez la dynamique de vos villes en temps réel.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Python-3.8+-blue.svg" alt="Python Version">
  <img src="https://img.shields.io/badge/Streamlit-1.x-FF4B4B.svg" alt="Streamlit">
  <img src="https://img.shields.io/badge/Folium-Maps-77B829.svg" alt="Folium">
  <img src="https://img.shields.io/badge/Data-Open%20Data-orange.svg" alt="Open Data">
</p>

---

## 📌 À propos du projet

**City Pulse** est une application web interactive développée en Python avec le framework Streamlit. Son but est de rendre les données ouvertes (Open Data) des grandes métropoles françaises (Paris, Nantes, Rennes) accessibles, lisibles et utiles à la prise de décision.

Que ce soit pour vérifier les places de parkings relais en temps réel, trouver des îlots de fraîcheur pendant une canicule, ou analyser la corrélation spatiale entre différents équipements urbains, City Pulse centralise tout au même endroit.

---

## ✨ Fonctionnalités Principales

* 🗺️ **Cartographie Interactive :** Visualisation des données sous forme de points (avec *Marker Clustering* pour la performance) ou de cartes de chaleur (*Heatmaps*). Fonds de plan personnalisables (Clair, Nuit, Satellite).
* 📊 **Analyse & KPIs :** Tableaux de bord dynamiques résumant les métriques clés de la recherche en cours.
* 🧪 **Labo de Corrélations Spatiales :** Outil d'analyse permettant de croiser deux jeux de données (ex: Parcs vs Toilettes) grâce à un algorithme de maillage GPS (Grid System) pour générer des nuages de points et calculer la corrélation.
* 🎤 **Recherche Vocale ("Magique") :** Intégration du *Speech-to-Text* natif navigateur pour requêter l'application à la voix.
* ⛅ **Météo & Qualité de l'Air :** Widgets météo en temps réel et courbes interactives de pollution (PM10, O3, NO2).
* 📥 **Exports :** Téléchargement des jeux de données nettoyés (CSV) et sauvegarde des cartes interactives (HTML cliquable).

---

## 📸 Aperçu (Screenshots)

*(💡 Conseil : Ajoute ici 2 ou 3 captures d'écran de ton application une fois sur GitHub. Remplace les liens ci-dessous par tes propres images)*

| Vue Carte (Satellite) | Labo de Corrélation |
|:---:|:---:|
| `<img src="lien_vers_ton_image_carte.png" width="400">` | `<img src="lien_vers_ton_image_graphe.png" width="400">` |

---

## 🏙️ Villes & API Supportées

L'application interroge les portails officiels via l'API ODS v2.1 :
* **Paris 🗼** : Sanisettes, Écoles, Espaces Verts, Chantiers, Défibrillateurs...
* **Rennes 🏁** : Parkings Citédia (Temps réel), Parcs Relais STAR (Temps réel), Vélos STAR, Fréquentation bus...
* **Nantes 🐘** : Parcs et Jardins, Toilettes Publiques, Îlots de Fraîcheur, Salles à louer, Bicloo...

---

## 🛠️ Stack Technique

* **Interface Web :** `Streamlit`
* **Cartographie :** `folium`, `streamlit-folium`
* **Traitement de Données :** `pandas`, `requests`
* **Visualisation Graphique :** `altair`
* **Audio & Reconnaissance :** `gTTS` (Text-to-Speech), `streamlit-mic-recorder` (Speech-to-Text)

---

## 🚀 Installation & Utilisation en Local

Pour faire tourner ce projet sur votre propre machine, suivez ces étapes :

### 1. Cloner le dépôt
git clone [https://github.com/VOTRE_NOM/city-pulse.git](https://github.com/VOTRE_NOM/city-pulse.git)
cd city-pulse

### 2. Créer un environnement virtuel (Recommandé)
Bash

python -m venv env
# Sur Windows :
env\Scripts\activate
# Sur Mac/Linux :
source env/bin/activate

### 3. Installer les dépendances
Bash

pip install -r requirements.txt

### 4. Lancer l'application
Bash

streamlit run app.py

L'application s'ouvrira automatiquement dans votre navigateur à l'adresse http://localhost:8501.
🧠 Défis Techniques Relevés (Pour les curieux)

    Parsing de Géométrie : L'Open Data est hétérogène. La fonction recuperer_coordonnees() a été conçue pour lire des formats multiples (geom_x_y, dictionnaires, listes) et est capable de calculer automatiquement le centroïde des zones complexes (Polygones GeoJSON) pour les afficher comme de simples points.

    Algorithme de Maillage : Pour calculer des corrélations hors de Paris (où l'arrondissement fait office de zone), le code génère dynamiquement une grille de regroupement GPS (Grid System) avec une précision ajustable via arrondissement mathématique (round()).

🤝 Contribution

Ce projet a été réalisé dans le cadre d'un projet d'étude à L'ECAM Louis de Broglie
