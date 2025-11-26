# 📋 Schéma de Structure pour `product.json`

**Date** : 2025-11-15  
**Statut** : ⚠️ **STRUCTURE STABILISÉE - Ne plus modifier la structure**

---

## ⚠️ RÈGLE IMPORTANTE

**La structure de `product.json` est maintenant STABILISÉE et ne doit plus être modifiée.**

Toute modification de la structure peut casser :
- ✅ Le site web (`western-software.com`)
- ✅ Le script Stripe (`init.mjs`)
- ✅ Les autres produits qui utilisent le même format

---

## ✅ Structure Actuelle (STABLE)

### Champs Requis par le Site Web

```json
{
  "name": "string",                    // ✅ REQUIS - Nom du produit
  "tagline": "string",                 // ✅ REQUIS - Slogan
  "description": "string",             // ✅ REQUIS - Description complète
  "shortDescription": "string",        // ✅ REQUIS - Description courte
  "features": {                        // ✅ REQUIS - Fonctionnalités
    "automationRules": { ... },
    "flexibleExecution": { ... },
    "advancedManagement": { ... }
  },
  "pricing": {                         // ✅ REQUIS - Plans tarifaires
    "currency": "eur",                 // ✅ REQUIS - Devise
    "free": {                          // ✅ REQUIS - Plan gratuit
      "name": "Free",
      "price": "€0",                   // ✅ REQUIS - Prix formaté (pour le site)
      "unitAmount": 0,                 // ✅ REQUIS - Prix en centimes (pour Stripe)
      "period": "/month",
      "features": [ ... ],
      "buttonText": "Try for free"
    },
    "basic": { ... },                  // ✅ REQUIS - Plan Basic
    "standard": { ... },               // ✅ REQUIS - Plan Standard
    "premium": { ... }                 // ✅ REQUIS - Plan Premium
  },
  "installation": { ... },             // ✅ REQUIS - Étapes d'installation
  "usage": { ... },                    // ✅ REQUIS - Guide d'utilisation
  "useCases": { ... },                // ✅ REQUIS - Cas d'usage
  "security": { ... },                 // ✅ REQUIS - Sécurité
  "support": { ... },                  // ✅ REQUIS - Support
  "meta": { ... }                     // ✅ REQUIS - Métadonnées SEO
}
```

### Champs Utilisés par le Script Stripe

Le script `init.mjs` utilise uniquement :
- `pricing.currency` → Devise
- `pricing.{plan}.unitAmount` → Prix en centimes pour chaque plan

**Les autres champs sont ignorés par le script Stripe.**

---

## 🔒 Champs qui NE DOIVENT PAS être modifiés

### Structure de base
- ❌ Ne pas supprimer de champs requis
- ❌ Ne pas renommer de champs
- ❌ Ne pas changer le type de données (string → number, etc.)

### Section `pricing`
- ❌ Ne pas supprimer `currency`
- ❌ Ne pas supprimer les plans (`free`, `basic`, `standard`, `premium`)
- ❌ Ne pas supprimer `unitAmount` (utilisé par Stripe)
- ❌ Ne pas supprimer `price` (utilisé par le site web)
- ❌ Ne pas changer les noms de plans (doivent correspondre à `plans.config.js`)

---

## ✅ Champs qui PEUVENT être modifiés

### Contenu éditorial (sans risque)
- ✅ `name` - Nom du produit
- ✅ `tagline` - Slogan
- ✅ `description` - Description complète
- ✅ `shortDescription` - Description courte
- ✅ `features.*.title` - Titres des fonctionnalités
- ✅ `features.*.items` - Liste des fonctionnalités
- ✅ `installation.steps` - Étapes d'installation
- ✅ `usage.sections` - Guide d'utilisation
- ✅ `useCases.cases` - Cas d'usage
- ✅ `security.features` - Fonctionnalités de sécurité
- ✅ `support.options` - Options de support
- ✅ `meta.*` - Métadonnées SEO

### Prix (avec précaution)
- ✅ `pricing.{plan}.price` - Prix formaté (ex: "€2.99")
- ✅ `pricing.{plan}.unitAmount` - Prix en centimes (ex: 299)
- ⚠️ **Important** : Modifier les deux en même temps pour cohérence

---

## 📝 Règles de Modification

### 1. Modification des Prix

**AVANT de modifier les prix** :
1. ✅ Vérifier que le nouveau prix est cohérent
2. ✅ Modifier `price` (formaté) ET `unitAmount` (centimes)
3. ✅ Tester avec le script Stripe en mode `--dry-run`
4. ✅ Synchroniser avec le repository GitHub `public`

**Exemple** :
```json
"basic": {
  "name": "Basic",
  "price": "€2.99",        // ← Modifier ici
  "unitAmount": 299,        // ← ET ici (299 centimes = 2.99€)
  ...
}
```

### 2. Modification du Contenu

**Sans risque** si vous modifiez uniquement :
- Textes descriptifs
- Listes de fonctionnalités
- Étapes d'installation
- Métadonnées SEO

**⚠️ Attention** : Ne pas modifier la structure (ajout/suppression de champs)

### 3. Ajout de Nouveaux Champs

**⚠️ DÉCONSEILLÉ** sauf si :
- ✅ Le site web est mis à jour pour supporter le nouveau champ
- ✅ Le script Stripe est mis à jour si nécessaire
- ✅ Tous les produits sont mis à jour de manière cohérente

**Recommandation** : Créer un nouveau fichier ou version plutôt que modifier la structure existante.

---

## 🧪 Validation

Avant de pousser des modifications :

1. **Valider le JSON** :
   ```bash
   node -e "require('./product.json'); console.log('✅ JSON valide');"
   ```

2. **Vérifier la structure** :
   - Tous les champs requis sont présents
   - Les types de données sont corrects
   - `unitAmount` correspond à `price` (ex: 299 = "€2.99")

3. **Tester avec Stripe** (si modification des prix) :
   ```bash
   node lib/scripts/stripe/init.mjs --validate-only --key sk_test_XXXX
   ```

---

## 📚 Documentation de Référence

- **Format standardisé** : Défini dans `product-loader.js` (site web)
- **Utilisation Stripe** : `lib/scripts/stripe/init.mjs` (fonction `loadPricingConfig`)
- **Repository GitHub** : `https://github.com/mdesmots/public`

---

## 🎯 Recommandations Finales

1. **Stabiliser la structure actuelle** ✅
2. **Documenter toute modification** dans un changelog
3. **Tester avant de pousser** vers GitHub
4. **Synchroniser immédiatement** après modification
5. **Ne pas modifier la structure** sans mettre à jour le site web

---

**Date de création** : 2025-11-15  
**Dernière mise à jour** : 2025-11-15  
**Statut** : 🔒 **STRUCTURE STABILISÉE**





