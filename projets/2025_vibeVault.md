## ✅ Intégration complète de Bootstrap 5.3 avec Importmap dans Rails

### 📅 Dates : juin 2025

### 🔧 Contexte
L'application VibeVault utilisait déjà les composants CSS de Bootstrap 5, mais les composants JavaScript comme les *dropdowns* ou les *collapses* ne fonctionnaient pas (notamment pour le bouton "Filtres & recherche").

---

### 🛠️ Étapes techniques effectuées

#### 1. Installation de Bootstrap et Popper.js via npm
```bash
npm install bootstrap@5.3.0 @popperjs/core
2. Pin des dépendances JS avec Importmap
./bin/importmap pin bootstrap @popperjs/core
Cela a ajouté dans config/importmap.rb :

pin "bootstrap", to: "bootstrap.js", preload: true
pin "@popperjs/core", to: "@popperjs/core.js"
3. Import dans app/javascript/application.js

import "@popperjs/core"
import "bootstrap"
4. Chargement du CSS dans app/assets/stylesheets/application.bootstrap.scss

@import "bootstrap";
Et vérification que ce fichier est bien lié dans le manifest.js :

//= link_tree ../builds
//= link application.bootstrap.scss
✅ Résultat obtenu
✅ Tous les composants JS de Bootstrap sont fonctionnels :

Dropdown

Collapse

Navbar toggler (icône hamburger)

✅ Les icônes Bootstrap (navbar-toggler-icon) s’affichent correctement

⚠️ Problèmes résolus
collapse ne fonctionnait pas → dû à l’absence d’import JS

Icône hamburger invisible → lié au CSS non chargé / oubli d’import ou de test

Le menu Filtres & recherche ne s’affichait pas → un d-none traînait dans le partial _search.html.erb


## 🛒 VibeVault – Site e-commerce (Projet en cours)  
📆 **Année** : 2024–2025  

### 📍 Description  
Plateforme de vente en ligne moderne, inspirée des standards UX/UI des plus grandes boutiques e-commerce. L’application permet la gestion automatisée des produits, un tunnel de commande sécurisé, un back-office fonctionnel, ainsi qu’une interface fluide et responsive. Le site est actuellement accessible à l’adresse suivante : [joupi.shop](https://joupi.shop)

### 🔧 Technologies utilisées  
- **Backend** : Ruby on Rails 7, PostgreSQL  
- **Frontend** : Stimulus.js, Hotwire Turbo  
- **Paiement** : Stripe (Checkout + Webhooks)  
- **Stockage** : Active Storage  
- **Déploiement** : Heroku  
- **Notifications** : Turbo Streams + Flash real-time  
- **Importation** : Rake Task avec parsing CSV via Ruby  

### 🚀 Fonctionnalités Implémentées  

#### 🗃️ Gestion de Produits
- ✅ **Import CSV** : import automatisé de produits depuis un fichier CSV avec vérification des doublons (ID unique)  
- ✅ **Création en base** : insertion dynamique des données produits (titre, description, prix, images, catégories)  
- ✅ **Gestion des catégories** : classement des produits par type, affichage conditionnel  

#### 🛒 Tunnel d’Achat
- ✅ **Panier d’achat** : ajout/suppression de produits, ajustement des quantités  
- ✅ **Checkout Stripe** : intégration du paiement Stripe avec redirection sécurisée  
- ✅ **Webhooks Stripe** : confirmation de paiement en temps réel et enregistrement des commandes  

#### 🔔 Notifications & UI  
- ✅ **Notifications instantanées** : confirmation de commande, erreurs de paiement  
- ✅ **Interface responsive** : navigation fluide sur mobile et desktop  
- ✅ **Affichage dynamique** : filtres produits, affichage conditionnel des boutons, messages flash  

#### 🛠️ Back-Office  
- ✅ **Espace admin simplifié** : ajout, édition et suppression de produits  
- ✅ **Suivi des stocks** : visualisation rapide des produits disponibles et rupture  

#### 🔎 Filtres & Recherche  
- ✅ **Barre de recherche** : recherche dynamique par titre ou catégorie  
- ✅ **Filtres combinés** : tri par prix, nouveautés, popularité (à étendre)  

### 🔜 Fonctionnalités prévues / en cours de développement
- 🔸 **Espace client** : authentification, tableau de bord, historique de commandes  
- 🔸 **Codes promo** : gestion des promotions, coupons de réduction  
- 🔸 **Suivi des livraisons** : statut des commandes, envoi d’e-mails de suivi  

### 🛠️ Compétences techniques mises en avant  
- ✔️ Automatisation du traitement de fichiers CSV en Ruby (Rake tasks)  
- ✔️ Intégration complète de Stripe avec gestion des webhooks  
- ✔️ UI dynamique avec Stimulus.js + Turbo pour interactions en temps réel  
- ✔️ Déploiement sur Heroku avec configuration des credentials & ENV vars  
- ✔️ Application MVC solide, stockage d’images avec Active Storage  
- ✔️ Gestion de sessions et navigation sécurisée  

