# Génération Automatique de Légendes d'Images (Image Captioning) 📸📝

[cite_start]Ce projet, réalisé dans le cadre du cursus **Économie Appliquée, Statistique et Big Data à l'INSEA** [cite: 5][cite_start], implémente un système capable de décrire le contenu d'une image en langage naturel[cite: 17]. [cite_start]L'objectif est de produire automatiquement une phrase qui capture l'essence d'une scène visuelle[cite: 17, 37].

## 🚀 Présentation du Modèle
[cite_start]Le travail suit la structure du modèle **Show and Tell**[cite: 11]:
* [cite_start]**Encodeur (Vision) :** Utilisation d'un CNN pré-entraîné (**InceptionV3**)[cite: 66, 139]. [cite_start]En retirant la couche de classification finale, on récupère un vecteur de caractéristiques de dimension 2048 représentant les motifs visuels[cite: 140].
* [cite_start]**Décodeur (Langage) :** Un réseau **LSTM** qui génère la phrase mot par mot[cite: 11, 22]. [cite_start]À chaque pas de temps, il prédit le mot suivant en se basant sur l'image et les mots précédents[cite: 22, 150].

* ## 📊 Dataset : Flickr8k
[cite_start]Le modèle est entraîné sur le **Flickr8k Dataset**[cite: 25, 27]:
* [cite_start]**8 000 images** représentant une grande variété de scènes quotidiennes[cite: 27, 29].
* [cite_start]**40 000 légendes** au total (5 par image), ce qui favorise l'apprentissage d'un langage varié[cite: 28, 32].
* [cite_start]**Prétraitement :** Nettoyage du texte (minuscules, retrait de la ponctuation) [cite: 90, 99] [cite_start]et ajout des tokens `start` et `end` pour structurer la génération de séquences[cite: 102, 103].

* ## 🛠️ Détails de l'Entraînement
* [cite_start]**Vocabulaire :** Le modèle gère un dictionnaire de **8 586 mots**[cite: 38, 130].
* [cite_start]**Optimiseur :** Utilisation d'**Adam** avec un *learning rate* adaptatif et un *clipnorm* de 1.0 pour stabiliser les gradients[cite: 161, 166].
* [cite_start]**Régularisation :** Mise en place de l'**EarlyStopping** pour éviter le surapprentissage et d'un **LearningRateScheduler** pour affiner la convergence[cite: 168, 169].

* ## 🏆 Résultats : Greedy Search vs Beam Search
[cite_start]Nous avons comparé deux stratégies de décodage sur des images de test[cite: 195]:
1. **Greedy Search :** Choisit le mot le plus probable à chaque étape. [cite_start]Résultat : *"a dog running in the snow"*[cite: 188, 197].
2. **Beam Search (K=5) :** Explore plusieurs phrases candidates en parallèle. [cite_start]Résultat : *"a tan dog is running in the snow"*, offrant une description plus riche et naturelle[cite: 191, 207].

3. ## 👥 Équipe du Projet
* [cite_start]**Hajar Chaib** [cite: 4]
* [cite_start]**Lamya Hajjou** [cite: 2]
* [cite_start]**Sara Karim** [cite: 2]
* [cite_start]**Elmardi Mouad** [cite: 3]

[cite_start]**Année universitaire :** 2025-2026 [cite: 6]
