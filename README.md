## Weekly Automatisation

## 🚀 Introduction

Ce projet est une solution d'automatisation complète pour le traitement hebdomadaire de fichiers CSV récupérés depuis un compte Gmail et leur transformation en différents fichiers Excel sur Google Drive. L'objectif principal est d'extraire automatiquement les fichiers Weekly reçus par mail, classer les données extraites en plusieurs catégories (CB, Hyper, Carma, IG, IRI) en fonction des règles métiers et de générer des fichiers comptables prêts à l'emploi. Ainsi les comptables n'auront plus qu'à se connecter sur le drive chaque matin et récupérer les fichiers déjà traités. Cette automatisation fais gagner aux comptables 4h par semaines ce qui est un gros gain de temps en entreprise. Ceci leur permet de se concentrer sur d'autres tâches.

## ✨ Fonctionnalités

Connexion aux API Google Drive et Gmail pour télécharger et manipuler les fichiers.

Normalisation des noms de sociétés pour une meilleure comparaison.

Téléchargement des fichiers Excel nécessaires depuis Google Drive.

Filtrage, nettoyage et transformation des données.

Classification des commandes en différentes catégories (CB, Hyper, Carma, IG, IRI).

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

Chargement de l'état : Lecture de l'historique des fichiers déjà traités. Cette partie est très importante pour éviter de traiter les fichiers déjà traités.

Recherche des nouveaux CSVs Gmail : Récupération des nouveaux fichiers CSV de commandes.

Filtrage et nettoyage : Tri des commandes par type (CB, Hyper, Orange, Rouge, Noir).

Génération des fichiers Excel : Export des données triées et nettoyées vers Drive.

Mise à jour de l'état : Sauvegarde de l'historique de traitement. Pour éviter de les retraiter à la prochaine éxécution du code.


## 🐞 Débogage et Logs

Un fichier de log (extraction.log) est généré à chaque exécution. Ce fichier contient :

Les étapes de traitement effectuées

Les erreurs rencontrées

Les fichiers créés et mis à jour


## Gaetan DJAMBISSIE
## gaetan.djambissie@gmail.com
## gaetan-portfolio.netlify.app
