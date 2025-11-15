# 📝 Changelog - `product.json`

Historique des modifications du fichier `product.json` pour GmailCleaner.

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

