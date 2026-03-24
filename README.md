# Génération Automatique de Légendes d'Images (Image Captioning) 📸📝

Ce projet, réalisé à l'INSEA, implémente un système capable de décrire le contenu d'une image en langage naturel.

## 🚀 Présentation du Modèle
Le travail suit la structure du modèle **Show and Tell** :
* **Encodeur (Vision) :** Utilisation d'un CNN pré-entraîné (**InceptionV3**). En retirant la couche de classification finale, on récupère un vecteur de caractéristiques représentant les motifs visuels.
* **Décodeur (Langage) :** Un réseau **LSTM** qui génère la phrase mot par mot en se basant sur l'image et les mots précédents.

## 📊 Dataset : Flickr8k
Le modèle est entraîné sur le **Flickr8k Dataset** :
* **8 000 images** représentant des scènes quotidiennes.
* **40 000 légendes** au total (5 par image) pour un apprentissage riche.
* **Prétraitement :** Nettoyage du texte et ajout des tokens `start` et `end` pour structurer la génération.

## 🏆 Résultats : Greedy vs Beam Search
Nous avons comparé deux méthodes de génération :
1. **Greedy Search :** Sélectionne le mot le plus probable. Résultat : *"a dog running in the snow"*.
2. **Beam Search (K=5) :** Explore plusieurs phrases en parallèle. Résultat : *"a tan dog is running in the snow"*.

## 👥 Équipe du Projet
* **Hajar Chaib**
* **Lamya Hajjou**
* **Sara Karim**
* **Elmardi Mouad**

**Année universitaire :** 2025-2026
