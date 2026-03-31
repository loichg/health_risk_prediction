# Analyse de risques de santé & Prédiction de maladies 

## Présentation

Ce dépôt présente un projet de data science réalisé en stage, portant sur l’analyse de données de santé et la prédiction de maladies à partir de facteurs de risque.

L’objectif est de construire une approche complète permettant :

* d’analyser des données de santé,
* d’identifier des relations statistiques,
* et de développer des modèles de prédiction probabiliste de maladies.

---

## Contexte

Projet réalisé au sein d’une entreprise spécialisée dans :

* la prévention en santé,
* l’analyse des risques professionnels,
* la qualité de vie au travail.

Les données utilisées sont anonymisées et issues d’un diagnostic interne.

---

## Objectifs

* Analyse exploratoire de données de santé
* Identification des facteurs de risque majeurs
* Étude des corrélations entre variables
* Génération d’une base de données synthétique cohérente
* Développement de modèles de prédiction de maladies

---

## Données

### Variables étudiées

* Santé physique : douleur, TMS, IMC
* Santé mentale : stress, dépression, sommeil
* Habitudes de vie : tabac, alcool, sport, nutrition
* Travail : charge, ergonomie, soutien social

Certaines variables peuvent être à la fois :

* facteurs
* maladies

---

## Méthodologie

### 1. Analyse exploratoire

* Étude des distributions globales
* Identification des risques dominants (nutrition, stress, activité physique)
* Analyse des :

  * risques psychosociaux (RPS)
  * troubles musculo-squelettiques (TMS)

---

### 2. Analyse de corrélation

Utilisation du coefficient phi sur variables binaires :

* Tables de contingence (2×2)
* Test d’hypothèse :

  * H0 : indépendance
  * seuil α = 0.05

Identification des corrélations significatives

---

### 3. Quantification du risque

Calcul de :

* Risque relatif (RR)
* Fraction attribuable (FA)

Permet d’estimer l’impact d’un facteur sur une maladie

---

## Génération de la base de données

Objectif : créer une base respectant :

* prévalences
* odds ratios
* cohérence globale

---

### Méthode 1 — Génération + ajustement

#### Étapes

1. Génération des maladies (binaire, selon prévalence)

2. Conversion odds ratio → probabilités 

3. Génération des facteurs :

* matrice avec une maladie active par ligne
* combinaison via OR logique

4. Ajustement itératif :

* correction des prévalences
* correction des odds ratios
* opérations : ajout / suppression / permutation

---

#### Limites

* non déterministe
* cas peu réalistes possibles
* dépendances partielles

---

### ⚙️ Méthode 2 — Amélioration

Objectif : corriger les limites de la méthode 1

Améliorations :

* meilleure gestion des dépendances
* réduction des incohérences
* génération plus réaliste

Base plus exploitable pour la prédiction

---

## Passage en données continues

### Objectif

Transformer les variables :

* binaire → continue

---

### Méthode

1. Définition de distributions par variable

2. Transformation :

* 0 → valeurs faibles
* 1 → valeurs élevées

3. Conservation des relations statistiques

4. Réentraînement des modèles

---

### Avantages

* meilleure représentation des phénomènes
* exploitation plus fine par les modèles

---

## Modélisation

### Modèles testés

* Random Forest
* Régression logistique
* MLP (réseau de neurones)
* Gradient Boosting
* AdaBoost
* KNN
* CART
* Linear SVM

---

### Modèles retenus

* Random Forest
* Régression logistique
* MLP

Critères :

* prédiction de probabilités
* cohérence statistique

---

### Pipeline

1. Génération dataset (~100k lignes)
2. Split train/test
3. Entraînement
4. Prédiction :

   * classe
   * probabilité
5. Analyse des résultats

---

### Évaluation

* cohérence des probabilités
* comparaison avec distribution théorique
* analyse visuelle

---

## Résultats

* Corrélations significatives identifiées
* Facteurs clés mis en évidence (stress, tabac, autonomie…)
* Base synthétique exploitable
* Modèles capables de produire des probabilités cohérentes

---

## Limites

* dépendance aux données synthétiques
* simplification des dépendances
* sensibilité aux paramètres
 
## Outils utilisés 

Langage : Python
