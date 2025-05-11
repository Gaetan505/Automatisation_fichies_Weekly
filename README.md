## Weekly Automation

## 🚀 Introduction

Ce projet est une solution d'automatisation complète pour le traitement hebdomadaire de fichiers CSV récupérés depuis un compte Gmail et leur transformation en différents fichiers Excel sur Google Drive. L'objectif principal est de classer les données extraites en plusieurs catégories (CB, Hyper, Carma, IG, IRI) et de générer des fichiers comptables prêts à l'emploi.

## ✨ Fonctionnalités

Connexion aux API Google Drive et Gmail pour télécharger et manipuler les fichiers (extraire les fichiers automatiquement par mail et les envoyer sur le drive).

Normalisation des noms de sociétés pour une meilleure comparaison.

Téléchargement des fichiers Excel nécessaires depuis Google Drive.

Filtrage, nettoyage et transformation des données.

Classification des commandes en différentes catégories ((CB, Hyper, Carma, IG, IRI).

Génération de fichiers Excel sur Google Drive organisés par semaine.

Mise à jour de l'état d'avancement via un fichier JSON stocké sur Google Drive.

Gestion des logs pour le suivi des erreurs et des étapes du traitement.

## 🔧 Pré-requis

Python 3.8+

Accès à Google Drive et Gmail

Clés d'API Google Drive et Gmail

## ⚙️ Configuration

Configurer l'accès aux Secrets Manager sur Google Cloud Platform.

Récupérer les identifiants :

o2c-ca-token

sa_o2c_relance_client_private_key

Placer ces identifiants dans le Secret Manager avec les permissions adéquates.

Modifier les variables suivantes dans le script :

TARGET_DRIVE_FOLDER_ID

FOLDER_NAME

FILENAME


## 🔍 Explication des principales parties du code

Authentification Google API : Connexion sécurisée aux services Drive et Gmail.

Téléchargement des fichiers depuis Google Drive : Chargement des fichiers Excel nécessaires.

Chargement de l'état : Lecture de l'historique des fichiers déjà traités.

Recherche des nouveaux CSVs Gmail : Récupération des nouveaux fichiers CSV de commandes.

Filtrage et nettoyage : Tri des commandes par type (CB, Hyper, Orange, Rouge, Noir).

Génération des fichiers Excel : Export des données triées et nettoyées vers Drive.

Mise à jour de l'état : Sauvegarde de l'historique de traitement.


## 🐞 Débogage et Logs

Un fichier de log (extraction.log) est généré à chaque exécution. Ce fichier contient :

Les étapes de traitement effectuées

Les erreurs rencontrées

Les fichiers créés et mis à jour

## 🚀 Améliorations futures

Ajouter des tests unitaires pour chaque module

Optimiser le traitement des fichiers volumineux

Ajouter un système de notifications (par email ou Slack) lors de l'exécution


## Gaetan DJAMBISSIE
## gaetan.djambissie@gmail.com
## gaetan-portfolio.netlify.app
