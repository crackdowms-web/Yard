# YardCheck — Application d'inspection réception

Application mobile web (PWA) pour l'inspection des véhicules à la réception TMMF.

## Fichiers

```
yardcheck/
├── index.html      ← Application complète (tout-en-un)
├── manifest.json   ← Manifeste PWA (installation sur l'écran d'accueil)
└── README.md
```

## Fonctionnalités

- **Liste des véhicules** avec recherche par carrosserie ou VIN
- **Scanner de code-barres** via la caméra du téléphone (ZXing)
- **Saisie manuelle** du VIN en alternative au scan
- **Décision OK / NOK / Rapatriement** avec commentaire optionnel
- **Rapport de synthèse** avec compteurs par résultat
- Interface **responsive** optimisée mobile, support des encoches (safe-area)

## Déploiement

### Option 1 — Hébergement local (réseau interne)
1. Placer les fichiers sur un serveur web (Apache, Nginx, IIS…)
2. Servir en **HTTPS** obligatoire pour l'accès caméra
3. Accéder depuis le téléphone via l'URL interne

### Option 2 — GitHub Pages (gratuit)
1. Créer un dépôt GitHub
2. Uploader les fichiers
3. Activer GitHub Pages dans les paramètres
4. L'URL sera : `https://[user].github.io/[repo]/`

### Option 3 — Netlify / Vercel (drag & drop)
1. Aller sur netlify.com ou vercel.com
2. Glisser-déposer le dossier `yardcheck/`
3. URL HTTPS générée automatiquement

## Installation sur l'écran d'accueil (PWA)

Sur Android (Chrome) :
- Ouvrir l'URL → menu ⋮ → "Ajouter à l'écran d'accueil"

Sur iOS (Safari) :
- Ouvrir l'URL → bouton Partager → "Sur l'écran d'accueil"

## Scanner VIN

- Fonctionne uniquement en **HTTPS** (exigence du navigateur pour la caméra)
- Compatible codes-barres 1D (Code128, Code39) et QR codes
- Fallback : saisie manuelle du VIN toujours disponible
- Tester en saisissant un VIN comme : `JTDKBCBBX0A588549`

## Personnaliser les véhicules

Dans `index.html`, modifier le tableau `vehicles` :

```javascript
const vehicles = [
  { body:'27141', vin:'JTDKBCBBX0A588549', color:'040' },
  // Ajouter vos lignes ici...
];
```

---
YardCheck v1.0 — Mars 2026
