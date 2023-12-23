# Simulation de K-means en Mode Distribué pour Big Data

## Objectif
Ce mini-projet vise à simuler l'exécution de l'algorithme K-means en mode distribué, adapté aux contraintes du Big Data, notamment la décentralisation des données. L'approche interdit le rapatriement de toutes les données en mémoire, une contrainte essentielle dans le contexte du Big Data.

## Description
Le projet implique l'utilisation de l'algorithme K-means simple, qui est ensuite adapté pour fonctionner de manière distribuée. Le processus commence par remplir trois tables dans Cassandra, chacune avec 100,000 éléments comportant quatre colonnes : ID_pref (Partition key), Id_company, age, weight, et shoulder circumference. Les valeurs sont générées en suivant des distributions normales et aléatoires spécifiques.

## Environnement et Outils
- Python avec des bibliothèques telles que `sklearn`, `numpy`, `scipy`.
- Cassandra pour la gestion de la base de données.
- Docker pour créer un cluster Cassandra à trois nœuds.

## Fonctionnement
1. **Initialisation de Cassandra**: Configuration d'un cluster Cassandra à trois nœuds avec Docker-compose. Création des tables avec des données générées suivant des règles spécifiques.
2. **Adaptation de K-means**: Le K-means classique est adapté pour fonctionner sur des données réparties sur plusieurs serveurs, simulant un environnement distribué.
3. **Calcul de Centroides**: Les moyennes des centroides sont calculées pour chaque serveur, puis une moyenne globale est générée à partir de ces moyennes.
4. **Comparaison des Résultats**: Les résultats du K-means distribué sont comparés avec ceux du K-means standard pour valider l'approche.

## Installation et Exécution
Des instructions détaillées pour l'installation des dépendances, la configuration de l'environnement et l'exécution du projet sont fournies dans les fichiers annexes (`docker-compose.yaml`, scripts Python, etc.).

## NB
Le projet commence par une implémentation utilisant un dictionnaire en mémoire (simulant Cassandra), puis évolue vers une implémentation réelle avec Cassandra.
