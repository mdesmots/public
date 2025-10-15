# Guide d'utilisation des logos pour Google Addon

## Fichiers créés

Les logos suivants ont été générés à partir d'une **version carrée** créée sur la base du fichier SVG original "WesternSoftwareLogo (290 x 160 px).svg". La zone centrale carrée a été extraite pour éviter toute déformation lors de la conversion en format carré requis pour les addons Google :

### Logo principal
- **`WesternSoftwareLogo-addon-128.png`** (128x128px) - Recommandé pour la configuration de l'addon

### Logos alternatifs
- **`WesternSoftwareLogo-addon-96.png`** (96x96px)
- **`WesternSoftwareLogo-addon-64.png`** (64x64px)  
- **`WesternSoftwareLogo-addon-48.png`** (48x48px)
- **`WesternSoftwareLogo-addon-32.png`** (32x32px)
- **`WesternSoftwareLogo-addon-16.png`** (16x16px)

## Configuration de l'addon Google

Dans votre fichier `appsscript.json`, utilisez l'URL suivante pour le logo :

```json
{
  "oauthScopes": [...],
  "addOns": {
    "common": {
      "name": "Votre Addon",
      "logoUrl": "https://github.com/mdesmots/gs-westernsoftware/raw/main/public/assets/logo/WesternSoftwareLogo-addon-128.png",
      "homepageTrigger": {
        "runFunction": "buildAddOn"
      }
    }
  }
}
```

## Caractéristiques techniques

- Format : PNG avec transparence
- Dimensions : Format carré (recommandé pour Google)
- Couleur de fond : Orange (#FFB900) avec éléments graphiques noirs
- Compatible avec tous les environnements Google Workspace

## Notes

✅ **Processus de création :**
1. **Fichier source** : `"WesternSoftwareLogo (290 x 160 px).svg"` (format rectangulaire 290x160)
2. **SVG carré créé** : `"WesternSoftwareLogo-square.svg"` (format carré 300x300)
3. **Extraction** de la zone centrale pour éviter toute déformation
4. **Conversion** en PNG dans toutes les tailles requises

Les PNG conservent parfaitement :
- ✅ Le design authentique Western Software 
- ✅ Le fond orange (#FFB900) caractéristique
- ✅ Tous les éléments graphiques vectoriels d'origine
- ✅ **Format carré parfait** sans déformation
- ✅ Optimisé pour les addons Google

La taille 128x128 pixels est la taille standard recommandée par Google pour les addons.

## Fichiers créés avec succès

| Fichier | Taille | Dimensions | Statut |
|---------|--------|------------|--------|
| **WesternSoftwareLogo-addon-128.png** | **2.9 KB** | **128x128px** | **Principal** |
| WesternSoftwareLogo-addon-96.png | 2.2 KB | 96x96px | Alternatif |
| WesternSoftwareLogo-addon-64.png | 1.5 KB | 64x64px | Alternatif |
| WesternSoftwareLogo-addon-48.png | 1.1 KB | 48x48px | Alternatif |
| WesternSoftwareLogo-addon-32.png | 715 B | 32x32px | Alternatif |
| WesternSoftwareLogo-addon-16.png | 427 B | 16x16px | Alternatif |

### Fichier SVG source carré
- **`WesternSoftwareLogo-square.svg`** - Version carrée 300x300px du logo original

## 🔧 Corrections apportées

**Problème résolu :** Les traits noirs du logo n'apparaissaient pas dans les PNG convertis.

**Solutions appliquées :**
- ✅ Suppression des variables CSS (`--stroke-color`) qui posaient problème lors de la conversion
- ✅ Remplacement par des couleurs directes (`stroke="#000000"`)
- ✅ Augmentation de l'épaisseur des traits de 10 à 12 pixels pour une meilleure visibilité
- ✅ Attributs de style appliqués directement sur chaque élément `<path>`

**Résultat :** Les traits noirs sont maintenant parfaitement visibles dans tous les PNG ! 🎯 