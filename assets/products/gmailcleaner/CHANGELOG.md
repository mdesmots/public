# 📝 Changelog - `product.json`

Historique des modifications du fichier `product.json` pour GmailCleaner.

---

## 2025-12-05 - Intégration Site Web et Screenshots

### ✅ Modifications Site Web

- **Ajout des boutons d'installation** vers le Google Workspace Marketplace
  - Bouton "Install" sur la page d'accueil (liste des produits)
  - Bouton "Install from Marketplace" dans la page de détails du produit
  - Boutons des cartes de prix liés au marketplace
  - URL du marketplace : `https://workspace.google.com/marketplace/app/cleaner_for_gmail/175823175354`

- **Intégration des screenshots** dans la page de détails
  - Nouvelle section "Screenshots" entre "Use Cases" et "Security"
  - Affichage de 3 screenshots :
    - `home-first.png` - Page d'accueil et premiers pas
    - `new-rule.png` - Création d'une nouvelle règle
    - `execution.png` - Exécution des règles
  - Grille responsive avec cartes stylisées

### ✅ Modifications `product.json`

- **Ajout de la section `screenshots`** dans le fichier `product.json`
  - Structure avec titre et liste d'images
  - Chaque screenshot contient : `title`, `description`, `url`
  - URLs pointant vers GitHub (raw.githubusercontent.com)

### 📋 Fichiers Modifiés

- `ws-portal/dist/index.html` - Ajout du bouton Install
- `ws-portal/dist/products.html` - Ajout de la section screenshots
- `ws-portal/dist/js/product-loader.js` - Fonction `renderScreenshots()` et gestion des boutons
- `ws-portal/dist/styles.css` - Styles pour les screenshots et boutons
- `public/assets/products/gmailcleaner/product.json` - Section screenshots ajoutée

---

## 2025-11-15 - Stabilisation de la Structure

### ✅ Modifications

- **Ajout de `unitAmount`** dans la section `pricing` pour chaque plan
  - `free`: `unitAmount: 0`
  - `basic`: `unitAmount: 299` (2.99€)
  - `standard`: `unitAmount: 999` (9.99€)
  - `premium`: `unitAmount: 1999` (19.99€)

- **Mise à jour des prix** :
  - Basic : 2.99€ (était précédemment différent)
  - Standard : 9.99€ (était précédemment différent)
  - Premium : 19.99€ (était précédemment différent)

### 🔒 Structure Stabilisée

La structure est maintenant **stabilisée** et ne doit plus être modifiée sans :
1. Mise à jour du site web
2. Mise à jour du script Stripe si nécessaire
3. Documentation des changements

### 📋 Utilisation

- **Site web** : Utilise `pricing.{plan}.price` (formaté)
- **Script Stripe** : Utilise `pricing.{plan}.unitAmount` (centimes)

---

## Règles pour les Modifications Futures

### ✅ Peut être modifié sans risque :
- Contenu éditorial (descriptions, textes)
- Prix (en modifiant `price` ET `unitAmount`)
- Métadonnées SEO

### ❌ Ne doit PAS être modifié :
- Structure de base (noms de champs, types)
- Noms des plans (`free`, `basic`, `standard`, `premium`)
- Suppression de champs requis

---

**Date de création** : 2025-11-15





