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
bash
Copier
Modifier
./bin/importmap pin bootstrap @popperjs/core
Cela a ajouté dans config/importmap.rb :

ruby
Copier
Modifier
pin "bootstrap", to: "bootstrap.js", preload: true
pin "@popperjs/core", to: "@popperjs/core.js"
3. Import dans app/javascript/application.js
js
Copier
Modifier
import "@popperjs/core"
import "bootstrap"
4. Chargement du CSS dans app/assets/stylesheets/application.bootstrap.scss
scss
Copier
Modifier
@import "bootstrap";
Et vérification que ce fichier est bien lié dans le manifest.js :

js
Copier
Modifier
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
