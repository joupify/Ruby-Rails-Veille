# Twitter Clone - Suivi Technique (2025)
  📌 Récapitulatif des Projets
🕊️ Twitter Clône – Développement Full-Stack avec Ruby on Rails 8 
📆 Année : 2025
📍 Description
Application web inspirée de Twitter, permettant aux utilisateurs de publier des tweets, d'interagir avec d'autres membres (likes, retweets, commentaires) et de suivre leurs abonnements en temps réel.
🔧 Technologies utilisées
Backend : Ruby on Rails 8, PostgreSQL
Frontend : Stimulus.js, Hotwire Turbo
Authentification : Devise
Stockage : Active Storage (images de profil & bannières)
Notifications : Noticed + Sidekiq pour les notifications en arrière-plan
Tâches en arrière-plan : Active Job (EventJob)
Base de données : PostgreSQL
🚀 Fonctionnalités Implémentées
1️⃣ Système d’authentification (Devise)
 ✅ Inscription / Connexion / Déconnexion
 ✅ Gestion du mot de passe (réinitialisation par e-mail)
 ✅ Système de session sécurisé
2️⃣ Gestion du Profil Utilisateur
 ✅ Création et modification du profil (nom, bio, avatar, bannière)
 ✅ Génération automatique d’un username unique si absent
 ✅ Suivi des statistiques d’un utilisateur (nombre de tweets, likes, commentaires)
3️⃣ Fonctionnalités des Tweets
 ✅ Création de tweets (texte uniquement)
 ✅ Affichage des tweets dans la timeline
 ✅ Likes : possibilité d’aimer un tweet
 ✅ Retweets : republication d’un tweet
 ✅ Commentaires : possibilité d’ajouter un commentaire sur un tweet
 ✅ Compteur de vues : suivi du nombre de vues sur chaque tweet
 ✅ Partage de tweets
 ✅ Système de favoris pour sauvegarder des tweets préférés
4️⃣ Système de Suivi (Follow/Unfollow)
 ✅ Suivre et se désabonner d’un utilisateur
 ✅ Liste des abonnements (Followings)
 ✅ Liste des abonnés (Followers)
 ✅ Vérification pour éviter de se suivre soi-même
5️⃣ Notifications & Interactions en Temps Réel
 ✅ Notifications des likes, retweets et commentaires
 ✅ Notification lorsqu’un utilisateur est mentionné dans un tweet
 ✅ Notification lorsqu’un utilisateur est suivi
 ✅ Affichage des notifications non lues sur l’interface
6️⃣ Navigation & Interface Utilisateur
 ✅ Page d’accueil avec la timeline
 ✅ Page de profil utilisateur (avec statistiques et tweets)
 ✅ Affichage conditionnel des boutons (ex: Follow/Unfollow)
 ✅ Affichage dynamique des tweets avec le nom et la photo de l’auteur
7️⃣ Autres fonctionnalités terminées
 ✅ Messages privés (DMs)
 ✅ Hashtags et recherche avancée
 ✅ Mode nuit
 ✅ Tendances (Trending Topics)

🔜 Fonctionnalités en cours de développement / à venir
🔸 Vérification de compte (badge bleu)
 🔸 Mode brouillon pour les tweets
 🔸 Bloquer et signaler un utilisateur
 🔸 Statistiques avancées pour les utilisateurs
 🔸 Monétisation avec abonnements premium

🛠️ Compétences mises en avant
✔️ Développement Full Stack avec Rails 8 et Hotwire Turbo
 ✔️ Gestion des interactions en temps réel (Turbo Streams, WebSockets)
 ✔️ Respect des bonnes pratiques Rails et optimisation des performances
 ✔️ UI/UX dynamique inspirée des plateformes sociales modernes



## 📝 Fonctionnalités Implémentées
- **Système de notifications temps réel** : Utilisation de Noticed + Sidekiq  
  *Problème résolu : Latence des notifications → Optimisé avec Redis*  
- **Gestion des tweets** :  
  ```ruby
  # Exemple de code (app/models/tweet.rb)
  has_many :likes, dependent: :destroy

🔍 Veille Technologique
Découverte : Hotwire Turbo 8.0 améliore le rendu côté client

Testé : gem 'image_processing' pour optimiser les uploads d'images
