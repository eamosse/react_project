# Projet – Gestion académique (React / Node)

## Objectif du projet
Ce projet a pour objectif de concevoir une application web de gestion académique permettant
la gestion des étudiants, cours, unités d’enseignement, diplômes, professeurs, notes et statistiques,
avec un système d’authentification sécurisé et une architecture moderne (React / Node).

---

## Module 1 – Enrichissement du modèle de données

### 1.1 Cours (Matières)
Compléter le modèle existant des matières en ajoutant :
- Une description
- Un syllabus
- Les pré-requis

### 1.2 Étudiants
Compléter le modèle des étudiants avec :
- Une photo
- Une adresse

### 1.3 Unités d’Enseignement (UE)
Introduire la notion d’Unité d’Enseignement (UE) avec les règles suivantes :
- Une UE regroupe plusieurs matières
- Une matière peut appartenir à plusieurs UE
- Une UE est enseignée dans une promotion
- Les matières d’une UE se compensent entre elles
- Une UE ne peut pas être validée si l’étudiant obtient une note éliminatoire dans l’une des matières

### 1.4 Diplômes (Classes / Formations)
Mettre en place la gestion des diplômes :
- Un diplôme est composé de plusieurs étudiants
- Un étudiant est inscrit à un seul diplôme  
  *(La gestion du double diplôme peut être traitée en bonus)*
- Un étudiant obtient son diplôme si et seulement s’il a validé toutes les UE
- Une UE ne peut pas être validée si l’étudiant obtient une note éliminatoire dans l’une des matières de l’UE

### 1.5 Professeurs
Ajouter la gestion des professeurs :
- Chaque UE possède un professeur référent
- Chaque matière est enseignée par un professeur
- Un professeur peut enseigner plusieurs matières

---

## Module 2 – Authentification et gestion des accès

### 2.1 Authentification OAuth 2
Mettre en place un module d’authentification basé sur OAuth 2, obligatoire pour accéder aux
fonctionnalités de l’application.

### 2.2 Gestion des rôles
Implémenter les rôles suivants :
- **ADMIN** : Administration complète des comptes et des données
- **SCOLARITÉ** : Gestion administrative des étudiants, cours et notes
- **STUDENT** : Consultation de ses propres données uniquement
- **TEACHER** : Gestion des UE et des matières enseignées

### 2.3 Droits d’accès par rôle
Une fois connecté :
- **Administrateur**
  - Accès complet en lecture et écriture à toutes les entités
- **Scolarité**
  - Accès aux étudiants, cours et notes
  - Saisie des notes
  - Édition des profils étudiants
  - Association étudiants ↔ cours
- **Étudiant**
  - Consultation de ses notes
  - Visualisation des statistiques liées à son dossier académique
- **Enseignant**
  - Gestion des UE et des matières qu’il enseigne

### 2.4 Authentification OTP
Renforcer la sécurité en intégrant une authentification OTP (One-Time Password).

### 2.5 Authentification SSO
Autoriser l’authentification via des fournisseurs SSO :
- Google
- Facebook
- X (Twitter)
- Autres au choix

---

## Module 3 – Design et expérience utilisateur

- Utilisation de Material UI Theming
  - Mode clair
  - Mode sombre
- Application responsive
  - Adaptation de l’affichage selon le type d’écran (desktop, tablette, mobile)

---

## Module 4 – Statistiques avancées

Développer des dashboards dynamiques adaptés au profil utilisateur :

- **Administrateur**
  - Vision globale sur toutes les entités (étudiants, cours, UE, diplômes, professeurs)
- **Scolarité**
  - Statistiques sur les étudiants, cours et notes
- **Étudiant**
  - Statistiques personnelles (moyennes, progression, validation des UE)

---

## Module 5 – Containerisation et déploiement

- Containerisation des applications React et Node.js avec Docker
- Mise en place d’une pipeline de déploiement dans le cloud :
  - AWS, Hostinger ou autre fournisseur
- Automatisation du build et du déploiement

---

## Bonus (optionnel)
- Gestion du double diplôme
- Notifications (email / SMS)
- Tests unitaires et tests d’intégration
- Lien de validation de comptes par email (eg. un étudiant/professeur recoit un mail avec un mot de passe temporaire qu'il doit changer à la première connexion) 
