# CryptoKage

## Application de Cryptographie - Implémentation Pure en Python

---

## Description

CryptoKage est une application web complète dédiée à la cryptographie.  
Chaque algorithme est implémenté manuellement en Python pur, sans utiliser de bibliothèques cryptographiques externes.

L'application permet de :
- Chiffrer et déchiffrer des messages avec une vingtaine d'algorithmes
- Générer des clés asymétriques (RSA, ElGamal, EC-ElGamal)
- Calculer des empreintes numériques (SHA-1, SHA-256)
- Administrer les utilisateurs avec une interface dédiée

---

## Algorithmes implémentés

### Cryptographie symétrique

| Algorithme | Description |
|------------|-------------|
| Code César | Décalage alphabétique de 1 à 25 positions |
| Vigenère | Chiffrement polyalphabétique par mot-clé |
| Vernam (OTP) | Masque jetable basé sur le XOR |
| RC4 | Chiffrement par flot de Rivest |
| DES | Standard historique en modes ECB, CBC, CFB |
| AES-128 | Standard actuel (10 rondes, SubBytes, ShiftRows, MixColumns) |

### Cryptographie asymétrique

| Algorithme | Principe mathématique |
|------------|----------------------|
| RSA | Factorisation de grands nombres |
| ElGamal | Logarithme discret |
| EC-ElGamal | Courbe elliptique (secp256k1) |

### Fonctions de hachage

| Algorithme | Taille de sortie |
|------------|------------------|
| SHA-1 | 160 bits |
| SHA-256 | 256 bits |

---

## Architecture technique
CryptoKage/
├── app.py # Application Flask (routes, sessions, auth)
├── crypto_algorithms.py # Coeur des algorithmes (implémentation pure)
├── templates/
│ ├── login.html # Authentification
│ ├── register.html # Inscription
│ ├── dashboard.html # Interface principale
│ └── admin_dashboard.html # Administration
└── cryptoapp.db # Base de données SQLite


---

## Installation et lancement

### Prérequis

- Python 3.9 ou supérieur
- Flask

### Étapes

```bash
# 1. Cloner le dépôt
git clone https://github.com/Aboubakar235/CryptoKage.git
cd CryptoKage

# 2. Installer Flask
pip install flask

# 3. Lancer l'application
python app.py

# 4. Accéder à l'application
# Ouvrir http://127.0.0.1:5000


Accès par défaut

Rôle	Identifiant	Mot de passe
Administrateur	admin	Admin@1234
Utilisateur	(à créer)	(à définir)
Fonctionnalités détaillées

Pour tous les utilisateurs

Connexion et inscription
Chiffrement et déchiffrement pour chaque algorithme
Génération de clés asymétriques
Copie des résultats dans le presse-papiers
Changement de mot de passe
Pour l'administrateur

Consultation de tous les utilisateurs
Création, modification et suppression de comptes
Visualisation des hashs SHA-256 des mots de passe
Recherche d'utilisateurs
Particularités techniques

Aucune bibliothèque crypto externe (tout est codé à la main)
Hachage des mots de passe avec SHA-256 pur
Sessions Flask gérées manuellement
Interface responsive avec Bootstrap 5
Police JetBrains Mono pour l'affichage des clés et hashs
Limites pédagogiques

Ce projet est destiné à l'apprentissage. Certains algorithmes ne doivent pas être utilisés en production :

DES est obsolète depuis 2000
RC4 est vulnérable
RSA en 512 bits est faible
SHA-1 est cassé cryptographiquement
En production, privilégier AES-256, RSA-2048 et SHA-256.

Évolutions possibles

Ajouter HTTPS (certificat Let's Encrypt)
Remplacer SHA-256 par bcrypt pour les mots de passe
Augmenter la taille des clés RSA à 2048 bits
Ajouter l'authentification à deux facteurs (2FA)
Dockeriser l'application
Ajouter des tests unitaires (pytest)
Auteur

Aboubakar Abdelaziz
École Mohammadia d'Ingénieurs (EMI) - Rabat
Master Génie Informatique
