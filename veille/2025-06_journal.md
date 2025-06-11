-#*🛠️ Veille Technique RoR - Juin 2025*

- ## * Veille Technique RoR - Juin 2025- Suivi Hebdo*



- **Actualité** : Sortie de Rails 7.1.3 ([rubyonrails.org](https://rubyonrails.org))
- **Astuce** : Optimisation des requêtes N+1 avec `includes`
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





