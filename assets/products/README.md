# Public Assets - Products Data

Ce dossier contient les données JSON des produits Western Software, hébergées publiquement sur GitHub.

## Structure

```
public/assets/products/
├── gmailcleaner/
│   └── product.json
├── invoicesense/
│   └── product.json
├── mailsense/
│   └── product.json
├── index.json
└── README.md
```

## URLs GitHub

Les fichiers sont accessibles via les URLs suivantes :

- **GmailCleaner** : https://raw.githubusercontent.com/mdesmots/public/refs/heads/main/assets/products/gmailcleaner/product.json
- **InvoiceSense AI** : https://raw.githubusercontent.com/mdesmots/public/refs/heads/main/assets/products/invoicesense/product.json
- **MailSense AI** : https://raw.githubusercontent.com/mdesmots/public/refs/heads/main/assets/products/mailsense/product.json
- **Index des produits** : https://raw.githubusercontent.com/mdesmots/public/refs/heads/main/assets/products/index.json

## Utilisation

Ces fichiers JSON sont utilisés par le site web pour charger dynamiquement les informations des produits via la page `products.html` avec des paramètres URL.

### Exemples d'utilisation

- `products.html` - Charge l'index des produits
- `products.html?product=gmailcleaner` - Charge les données GmailCleaner
- `products.html?product=invoicesense` - Charge les données InvoiceSense AI
- `products.html?product=mailsense` - Charge les données MailSense AI

## Avantages

- ✅ **Performance** : Hébergement CDN via GitHub
- ✅ **Disponibilité** : URLs publiques stables
- ✅ **Maintenance** : Mise à jour centralisée
- ✅ **Cache** : Mise en cache automatique par les navigateurs
- ✅ **Versioning** : Historique des modifications via Git

## Mise à jour

Pour mettre à jour les données d'un produit :

1. Modifier le fichier JSON correspondant dans ce dossier
2. Commiter et pousser les changements
3. Les modifications sont immédiatement disponibles sur le site

## Format des données

Chaque fichier JSON suit la structure standardisée définie dans le script `product-loader.js` :

- `name` : Nom du produit
- `tagline` : Slogan du produit
- `description` : Description complète
- `features` : Fonctionnalités principales
- `pricing` : Plans tarifaires
- `installation` : Étapes d'installation
- `usage` : Guide d'utilisation
- `useCases` : Cas d'usage
- `security` : Garanties de sécurité
- `support` : Options de support
- `meta` : Métadonnées SEO
