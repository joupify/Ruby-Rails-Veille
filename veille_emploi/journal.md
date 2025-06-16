# 🛠️ Veille Technique RoR - Juin 2025

- ##  Veille Technique RoR - Juin 2025- Suivi Hebdo


### ✅ 18 juin 2025 (prévisionnel)
- 🌐 Reprise de [Hotrails.dev](https://www.hotrails.dev/) pour une veille axée sur Turbo & Hotwire.  
  → Objectif : mettre à jour mes connaissances pratiques pour des projets full Hotwire.

---


### ✅ 17 juin 2025
- 📚 Lecture du chapitre 1 du Rails Tutorial (Rails 7th edition).  
  → Objectif : consolider les bases, revoir les bonnes pratiques de structure MVC.  
  → À documenter publiquement ou en README si nécessaire.

---
## 🎯 Objectif
Suivre activement les évolutions de l’écosystème Ruby on Rails, améliorer mes compétences en continu et repérer les bonnes pratiques attendues dans le monde professionnel.

---

## 🔍 Suivi des actions

### ✅ 16 juin 2025
- 📩 Contact avec Alexandre Ruban (développeur RoR) via LinkedIn.  
  → Conseils reçus : lecture du [Rails Tutorial](https://www.learnenough.com/ruby-on-rails-7th-edition) et de [Hotrails.dev](https://www.hotrails.dev/).  
  → Engagement personnel : revoir ces ressources pour veille officielle France Travail.  
- 📩 Message d’invitation envoyé à **Eloïse Emptoz** (Product Lead – Moka.Care) concernant le poste de *Junior Software Engineer*.  
  → En attente de publication de l'offre (mentionnée comme à venir).  
  → Stack Ruby confirmée via site de Moka.Care.

---


## 📌 Remarques
- 🔁 Tutos déjà connus, relus dans une logique de conformité (France Travail).  
- 🧠 Démarche critique maintenue : veille stratégique plutôt que consommation passive.

---

## 🛠️ Stack concernée
- Ruby 3.3.x  
- Rails 7.x / 8  
- Hotwire (Turbo, Stimulus.js)  
- PostgreSQL  
- Cloudinary (utilisé dans projet VibeVault)  
- Stripe API

---

## 🔗 Projets reliés à la veille
- **VibeVault** : e-commerce complet (import CSV, panier, paiement Stripe, admin simplifié)
- **Twitter Clone Rails 8** : fonctionnalités sociales avancées, messagerie, notifications

---
  
# 📅 Date : 12 juin 2025
- 🔍 **Veille marché** : Scraping LinkedIn => 0 offre RoR junior en IDF
- 🔍 **Veille marché** : Scraping France Travail=> 1 offre RoR junior en IDF -> arenametrix = offre expiree depuis 2 mois et publieée le 5 juin 
- 🔍 **Veille marché** : Scraping Welcome to Jungle=> 0 offre RoR junior en IDF
- 🔍 **Veille marché** : Scraping ROR Jobs => 0 offre RoR junior en IDF
- 📮 **Candidature** : ZERO  Envoyé
- ❌ **Obstacle** : 100% des offres exigent 2+ ans d'expérience (captures jointes)
- 
### 🔹 Réseautage LinkedIn  ( commenter des posts ROR junior)

## 🔹 Candidatures spontanées LinkedIn – envois d'invitations avec message

### 🎯 Objectif : Élargir son réseau professionnel en Ruby on Rails en ciblant des profils CTO / Tech Leads via LinkedIn (envoi de 14 invitations personnalisées).
### 📌 Méthode : Utilisation de Wallaxy pour automatiser l'envoi d'invitations avec un message intégré.

### 🖼️ Captures d'écran – preuves d'envoi/fichier reseau.md

# 📅 Date : 11 juin 2025
- 🔍 **Veille marché** : Scraping LinkedIn => 0 offre RoR junior en IDF
- 🔍 **Veille marché** : Scraping France Travail=> 1 offre RoR junior en IDF -> arenametrix = offre expiree depuis 2 mois et publieée le 5 juin 
- 🔍 **Veille marché** : Scraping Welcome to Jungle=> 0 offre RoR junior en IDF
- 🔍 **Veille marché** : Scraping ROR Jobs => 0 offre RoR junior en IDF
- 📮 **Candidature** : ZERO  Envoyé
- ❌ **Obstacle** : 100% des offres exigent 2+ ans d'expérience (captures jointes)
- 🛠 **Twitter Clone** : Optimisé les requêtes SQL (N+1) avec `includes`



- **Actualité** : Sortie de Rails 7.1.3 ([rubyonrails.org](https://rubyonrails.org))
- **Ressource** : Tutoriel sur Hotwire ([lien vers l’article](https://www.hotrails.dev/turbo-rails)


### 11/06  
- 🛠 **vibeVault** : Résolu le bug de paiement Stripe (webhook non déclenché)  
- 📚 **Veille** : Découvert `gem 'sidekiq-scheduler'` pour les tâches récurrentes

### 10/06  
- 🚀 **Twitter Clone** : Notifications en temps réel opérationnelles avec Hotwire  
- 🔍 **Ressource** : Tutoriel "Optimiser PostgreSQL avec Rails" 



## 📌 08/06/2025

### 🔧 Gestion des Environnements (dev/prod)
- ✅ Configuration séparée des fichiers `credentials.yml.enc` pour chaque environnement (production et développement).
- ✅ Gestion des clés Stripe, Cloudinary et SMTP de manière sécurisée via ENV vars.
- ✅ Mise en place de scripts d’import (`rake import:closet`) spécifiques à chaque environnement pour éviter les conflits de données.
- ✅ Détection et correction d’un bug de non-chargement des images en production :  
  *Cause* : ActiveStorage mal configuré avec Cloudinary en production (manque du host complet dans les URLs).  
  *Solution* : Ajout de `Rails.application.routes.default_url_options[:host]` dans `production.rb`.

### 🖼️ Active Storage : Blobs & Uploads
- ✅ Problème : en local, les images s’uploadent bien, mais ne s’affichaient pas en production.
- ✅ Analyse : les fichiers n’étaient pas envoyés vers Cloudinary mais stockés en local sur Heroku (éphémère).
- ✅ Résolution : config complète de Cloudinary via `config/storage.yml` + ENV + test en console Rails.
- ✅ Ajout d’un fallback visuel si une image est manquante (résilience côté UI).

---

## 📌 07/06/2025

### 🛡️ Sécurité
- ✅ Mise à jour vers Rails 7.1.3 (faille XSS corrigée)  
  *Impact* : protection accrue des vues rendues avec des données utilisateurs (ex. : nom, description produit).

### 🐌 Performance & Optimisation
- ✅ Intégration de `bullet` pour identifier les requêtes N+1, notamment sur :
  - Affichage des produits (catégories)
  - Commandes récentes en back-office
- ✅ Refactor des vues avec `includes(:category)` et `includes(:order_items)` pour réduire les hits SQL.

### 📦 Gestion des Produits
- ✅ Problème : doublons lors de l’import CSV en production.
- ✅ Résolution : ajout d’un `jolicloset_id` unique + validation `validates_uniqueness_of` + logique conditionnelle dans la rake task.
- ✅ Ajout de logs détaillés pendant l’import pour faciliter le debug en prod (affichage des produits ignorés ou créés).

---

## 📌 05/06/2025

### 👥 Authentification & Invitations
- ✅ Exploration de la gem `devise-invitable` pour intégrer une phase "bêta fermée" dans les futurs projets.
- 🔍 Test prévu sur Twitter Clone : permettre aux utilisateurs de parrainer d’autres membres via email d’invitation.

---

## 📊 Résumé des problèmes résolus (VibeVault)

| Type de problème                     | Statut     | Description                                                                                                                                 |
|-------------------------------------|------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| Uploads Active Storage (prod)       | ✅ Résolu   | Images non visibles en production → mauvaise config Cloudinary → correction de l’URL host et ENV                                           |
| Gestion Stripe (prod)               | ✅ Résolu   | Clés API erronées et callback Stripe non pris en compte → refactor des credentials + dashboard Stripe                                       |
| Import CSV en production            | ✅ Résolu   | Doublons de produits créés → ajout d’un identifiant unique, vérification conditionnelle et rollback si erreur                              |
| Erreurs de paiement silencieuses    | ✅ Résolu   | Aucune notification en cas d’échec de paiement Stripe → ajout de flashs + gestion des erreurs via webhooks                                 |
| Sessions panier intermittentes      | ✅ Résolu   | Problème avec session en production (Heroku) → configuration correcte du `session_store`                                                   |
| Navigation lente (N+1 queries)      | ✅ Résolu   | Pages lentes à charger → intégration de `bullet` + optimisation des requêtes avec `includes` et `counter_cache`                            |
| Notification visuelle absente       | ✅ Résolu   | Confirmation de commande invisible pour l’utilisateur → ajout de `turbo_stream` et affichage des flash en live                             |



## 📌 03/06/2025
- **Actualité** : Rails 7.1.3 corrige une faille XSS  
  *Impact sur vibeVault : Mise à jour urgente*  
- **Astuce** : Utiliser `bullet` pour détecter les N+1 queries
- **Astuce** : gestion des 2 environnements dev  et pro / création de SKU 

## 📌 01/06/2025
- **Découverte** : `gem 'devise-invitable'` pour les invitations  
  *Test prévu sur Twitter Clone*  





