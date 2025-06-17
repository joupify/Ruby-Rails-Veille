# Synthèse veille technique – Juin 2025 

---

## Projet principal : VibeVault (plateforme e-commerce Ruby on Rails)

- Projet personnel lancé **en production** avec de vrais articles dans la base de données.
- Hébergement : Heroku.
- Stockage images : Cloudinary.
- Fonctionnalités développées :
  - Import CSV des produits (script rake `import:closet`).
  - Gestion panier d’achat.
  - Paiement avec Stripe.
  - Notifications en temps réel.
  - Interface responsive.
  - Back-office simplifié.
  - Filtres et recherche avancée.
- En cours : gestion des promotions, codes promo, livraisons/statuts.
- Tech stack : Ruby on Rails 7, PostgreSQL, Stimulus.js, Turbo, Devise, Active Storage, Stripe, Sidekiq.

---

## Actions réalisées en juin 2025

- Script Rake pour import des produits via CSV, avec gestion des doublons par `jolicloset_id`.
- Téléchargement des images via OpenURI et upload sur Cloudinary.
- Analyse des doublons et mise à jour des produits existants (script à développer pour prod).
- Revue de code pour améliorer la robustesse et la maintenabilité.
- Tests unitaires et fonctionnels avec RSpec (couverture en progression).
- Veille active sur les nouvelles versions Ruby on Rails (7 et 8).
- Documentation technique enrichie des étapes de déploiement Heroku et gestion des clés API Stripe.
- Suivi des bugs remontés et corrections apportées.
- Adaptation continue pour une meilleure compatibilité mobile.

---

## Observations marché Ruby on Rails – Juin 2025

- Peu d’offres juniors RoR en France, quasi absence dans les systèmes officiels (France Travail).
- Nombreuses annonces obsolètes ou fausses (exemple : offre Artemetrix expirée depuis 2 mois, toujours visible sur FT via Jobijoba depuis le 5 juin).
- Difficultés persistantes à trouver un emploi RoR sans expérience pro significative.
- Importance de maintenir la veille et d’enrichir le portfolio personnel.
- Nécessité de consolider les compétences techniques pour répondre aux exigences des recruteurs.

---

## Note importante (à part)

> **Offre Artemetrix**  
> L’offre Artemetrix a expiré depuis plus de 2 mois, mais apparaît encore depuis le 5 juin 2025 sur le site France Travail, publiée via Jobijoba.  
> Cette annonce est **faussement disponible**, ce qui confirme que France Travail ne contrôle pas efficacement la véracité des annonces publiées sur son site.  
> Cela complique la recherche d’emploi et fausse les indicateurs de disponibilité de postes RoR juniors.

---

## Informations complémentaires

- Le projet VibeVault est un projet personnel, donc le dépôt GitHub reste **privé** (non public).
- Les scripts d’automatisation de veille pour les sites Indeed, WTJ, RubyOnRemote, LinkedIn sont en cours d’étude, priorité à LinkedIn.
- Poursuite de la veille sur les nouveautés et bonnes pratiques Ruby on Rails.
- Mise à jour régulière de la documentation interne.

---

## Synthèse globale

Malgré un contexte difficile sur le marché RoR junior, je poursuis ma montée en compétences technique et la consolidation de mon projet personnel.  
La veille technique et l’analyse du marché restent au cœur de ma stratégie pour optimiser mes candidatures et préparer au mieux les entretiens.  
La faible visibilité des offres réelles me poussent à intensifier mes démarches et à élargir mes sources d’information.

---


