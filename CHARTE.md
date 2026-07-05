# TOOD — Charte graphique

To-do list rapide et agréable : capturer, se faire rappeler, ne plus rien oublier.
Personnalité : chaleureux, joueur, efficace. Ambiance carnet de notes moderne, pas outil corporate.

## Logo

**Concept** : le wordmark TOOD dont les deux O portent le sens — le premier est une **horloge** (le rappel), le second une **coche** (le fait). Le logo raconte le cycle complet d'une tâche.

| Fichier | Usage |
|---|---|
| `icon-512.png` / `icon-192.png` | Icône PWA (fond ivoire + confettis, maskable Android) |
| `logo-horizontal.png` | Version transparente haute déf (documents, présentation) |
| `logo-header.png` | Header de l'app (800×240, transparent) |
| `monogramme.png` | Coche corail seule — avatar, favicon, petits formats <48 px |

Règles : ne pas changer les proportions, ne pas recolorer les éléments individuellement (le trio encre/corail est l'identité), fond ivoire ou blanc de préférence. En dessous de 48 px, utiliser le monogramme.

## Palette

| Nom | Hex | Rôle |
|---|---|---|
| Ivoire | `#FBF6EF` | Fond principal |
| Encre | `#232733` | Texte, wordmark |
| Corail | `#FF6B5A` | Accent principal : actions, chips actives, coche du logo |
| Ambre | `#F5B84D` | Source PHOTO, signal secondaire |
| Menthe | `#4FC59A` | Succès, tâche terminée |
| Lavande | `#8B93FF` | Source MAIL |
| Rose | `#F06292` | Décoratif (confettis) |
| Rouge alerte | `#E5484D` | En retard, erreurs — jamais décoratif |

Neutres UI : surface `#FFFFFF`, surface secondaire `#F3ECE1`, traits `#E9E1D4`, texte atténué `#8D867A`.

Règle de sens : chaque couleur vive a UN rôle. Le corail agit, la menthe valide, l'ambre et la lavande identifient la source. Ne pas les intervertir.

## Typographie

- **Poppins** (Google Fonts) — identité : logo (Bold 700), titres et labels de section (SemiBold 600), boutons (600)
- **System UI** — corps de texte, listes, formulaires (performance + lisibilité native)

Labels de section : 11 px, majuscules, letter-spacing 1.5 px, SemiBold.

## Tokens CSS (déjà dans index.html)

```css
:root {
  --bg: #FBF6EF; --surface: #FFFFFF; --surface2: #F3ECE1;
  --text: #232733; --muted: #8D867A; --line: #E9E1D4;
  --accent: #FF6B5A; --ambre: #F5B84D; --lavande: #8B93FF;
  --ok: #4FC59A; --danger: #E5484D;
  --radius: 14px;
}
```

## Ton rédactionnel

Phrases courtes, tutoiement, verbes d'action ("Capture une tâche", "Enregistrer"). Les états vides invitent à agir, les erreurs disent quoi faire ("Connexion impossible — vérifie les réglages"). Jamais de jargon technique côté interface.

## Déploiement de cette version

1. Remplacer dans le repo GitHub : `index.html`, `manifest.json`, `sw.js`, `icon-192.png`, `icon-512.png` + ajouter `logo-header.png`
2. Le cache passe en `tood-v2` (déjà fait dans sw.js) → mise à jour forcée au prochain chargement
3. Réinstaller la PWA pour rafraîchir l'icône d'écran d'accueil (les réglages API survivent en localStorage)
