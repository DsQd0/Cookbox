# Cookbox

Appli de batch cooking : une bibliothèque de 10 recettes, un tirage aléatoire de 4 pour le mois, la liste de courses (stock + frais par semaine), la préparation étape par étape avec minuteurs, les repas de la semaine et le suivi frigo/congélateur.

C'est une PWA (Progressive Web App) en HTML/CSS/JS pur, sans build ni dépendances — un simple site statique installable sur téléphone.

Direction artistique reprise de Loverbox (façon Letterboxd) : fond quasi noir (#14171b), cartes ardoise (#1b1f27), vert (#30cb75) comme accent principal, orange/ambre pour les catégories courses/prép, texte en Inter sans-serif bold.

## Installer sur son téléphone

1. Active GitHub Pages pour ce dépôt (une seule fois) :
   - Repo GitHub → **Settings** → **Pages**
   - Source : **Deploy from a branch**
   - Branche : choisis la branche qui contient ce code (ex. `claude/cookbox-batch-cooking-app-xh6rxy`, ou `main` une fois la PR mergée) — dossier `/ (root)`
   - **Save**, puis attends ~1 minute. L'URL apparaît en haut de la page (du type `https://<ton-user>.github.io/Cookbox/`).
2. Ouvre cette URL sur ton téléphone.
3. Installe l'appli :
   - **iPhone (Safari)** : bouton Partager → *Sur l'écran d'accueil*.
   - **Android (Chrome)** : menu ⋮ → *Installer l'application* (ou bannière automatique).

L'icône Cookbox apparaît alors sur l'écran d'accueil, en plein écran, sans barre d'adresse.

## Développement local

Aucune installation nécessaire, c'est du HTML/CSS/JS statique :

```bash
python3 -m http.server 8000
# puis ouvrir http://localhost:8000
```

## Structure

- `index.html` — l'application (une seule page)
- `manifest.json` — métadonnées PWA (nom, icônes, couleurs)
- `sw.js` — service worker (cache l'appli pour un usage hors-ligne)
- `icons/` — icônes de l'appli (192, 512, apple-touch-icon, et la source `icon.svg`)

## Données

Les cases cochées, le tirage des 4 recettes du mois et l'onglet actif sont sauvegardés dans le `localStorage` du navigateur — propre à chaque appareil, rien n'est envoyé sur un serveur.
