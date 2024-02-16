[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6-yellow)](https://www.ecma-international.org/ecma-262/)
[![Node.js](https://img.shields.io/badge/Node.js-v14.0.0-green)](https://nodejs.org/)
[![Express](https://img.shields.io/badge/Express-v4.17.1-blue)](https://expressjs.com/)

# Api-project

Pour récupérer le projet : 
* Créer un dossier pour le projet
* Faire le commande : git clone git@github.com:ESGI2/Api-project.git
* Crée un fichier **.env** à la racine du projet (voir modèle en dessous)
* Pour lancer le serveur faire : npm start   -> localhost:8080

Modèle du fichier **.env** : 

```
DB_SERVER = 'localhost'
DB_USER = 'user'
DB_PASSWORD = 'mot-de-passe'
DB_NAME = 'nom-db'
JWT_SECRET = 'code-jwt'
```
```
Tables à crée : 
-- Création de la table des utilisateurs
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    pseudo VARCHAR(50) NOT NULL,
    password VARCHAR(255) NOT NULL ,
    role VARCHAR(255) NOT NULL,
    token varchar(255) NOT NULL,
    );

-- Création de la table des appartements
CREATE TABLE appartements (
    id INT PRIMARY KEY AUTO_INCREMENT,
    superficie FLOAT NOT NULL,
    capacite INT NOT NULL,
    adresse VARCHAR(255) NOT NULL,
    disponibilite BOOLEAN NOT NULL,
    prix_nuit DECIMAL(10, 2) NOT NULL
    client_id INT NOT NULL,
);

-- Création de la table des réservations
CREATE TABLE reservations (
    id INT PRIMARY KEY AUTO_INCREMENT,
    date_debut DATE NOT NULL,
    date_fin DATE NOT NULL,
    client_id INT NOT NULL,
    appartement_id INT NOT NULL,
    FOREIGN KEY (client_id) REFERENCES user(id),
    FOREIGN KEY (appartement_id) REFERENCES appartements(id)
);
```
