## 09/06 ✅ Personnalisation de l’interface utilisateur (Rails 7 + Bootstrap 5)

**Objectif** : Améliorer l’expérience utilisateur (UX) et le rendu visuel d’une plateforme e-commerce (`VibeVault`) développée avec Ruby on Rails 7.

### ✅ Modifications réalisées :

#### 1. Refonte de la navbar

* Centrage de la barre de navigation (`navbar`) pour un rendu plus esthétique.
* Ajout d’un logo stylisé avec texte : **VibeVault** et sous-titre *Mode & Luxe*.
* Tests de plusieurs affichages : logo seul, navbar seule, puis combinaison des deux sur deux lignes pour un rendu plus haut de gamme.

#### 2. Menu latéral gauche (left menu)

* Intégré via un `partial` dans `app/views/layouts/application.html.erb` pour être affiché uniquement sur certaines pages (`products#index`, `products#home`).
* Amélioration de l'affichage sur mobile et desktop.
* Correction d’un bug : le menu ne s’affichait pas sur la homepage. Ajout de conditions explicites dans le helper `show_left_menu?`.

#### 3. Affichage des produits

* Correction d’un bug de duplication de l’affichage des produits dans la vue `index`.
* Intégration correcte du partial `_product.html.erb` avec rendu unique par produit via `collection:`.

#### 4. Pagination

* Mise en place d’une pagination **minimaliste** avec Bootstrap 5 :

  * Position : haut à droite.
  * Affichage des numéros de pages avec les extrémités visibles (ex. : `1 2 3 … 34`).
  * Ajout d’un style CSS personnalisé (`ultra-small-pagination`) pour un rendu plus compact.

#### 5. Logo stylisé en CSS

* Tests de plusieurs formats d’images (`logo.png`, `lllogo.png`).
* Logo finalement remplacé par une version CSS + HTML pour une meilleure intégration responsive.

#### 6. Protection en production

* Debug d’une erreur `current_user` sur `show` : gestion du cas où aucun utilisateur n’est connecté lors de l’appel au partial `likes/button`.

---

**Statut :** toutes les modifications ont été testées en local et en production.

**Prochaine étape :** continuer l’optimisation responsive + ajout de fonctionnalités avancées (filtres multi-critères, code promo, etc.).
