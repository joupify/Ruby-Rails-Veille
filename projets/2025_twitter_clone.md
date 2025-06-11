# Twitter Clone - Suivi Technique (2025)

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
