# Fleurs Roussel · page d'accueil

Intégration de la maquette Figma « Fleurs Roussel · Maquette page d'accueil » avec **Tailwind CSS 4**.
Projet réalisé dans le cadre du brief « De la maquette à la page avec Tailwind » (Simplon, La F@brique Numérique 41).

## Aperçu

Page d'accueil d'une fleuriste artisanale de Blois : en-tête, héros, trois bouquets de la semaine, atouts, atelier et pied de page.
Deux maquettes de référence : mobile (390 px) et ordinateur (1440 px). Le mobile est écrit d'abord, sans préfixe.

## Prérequis

- [Node.js](https://nodejs.org/) (version LTS) et npm

## Installation

```bash
git clone https://github.com/jexpire41-oss/accueil-roussel.git
cd accueil-roussel
npm install
```

## Développement

Lance la compilation de Tailwind en continu : le fichier `dist/output.css` est régénéré à chaque modification de `index.html` ou de `src/input.css`.

```bash
npm run dev
```

Ouvre ensuite `index.html` dans le navigateur (ou avec le serveur intégré de ton éditeur).

## Build

Génère le CSS final minifié dans `dist/output.css` :

```bash
npm run build
```

Le fichier `dist/output.css` est versionné : la page s'ouvre directement sans compilation.

## Structure du projet

```
accueil-roussel/
├── index.html        # la page
├── src/input.css     # point d'entrée Tailwind : polices locales et thème (@theme)
├── dist/output.css   # CSS compilé (généré)
├── fonts/            # Playfair Display et Inter (fichiers locaux)
├── images/           # illustrations et icônes SVG
└── package.json      # scripts dev et build
```

## Choix techniques

- **Thème** : couleurs (framboise, bordeaux, sauge, crème, pétale, encre, blanc) et polices (titres en Playfair Display, texte en Inter) déclarées dans `@theme`, dans `src/input.css`. Aucune valeur arbitraire dans le HTML.
- **Responsive** (mobile d'abord) :
  - à partir de 640 px (`sm:`) : boutons du héros côte à côte, deux cartes de bouquet par ligne ;
  - à partir de 768 px (`md:`) : en-tête sur une ligne, héros, atouts, atelier et pied de page en colonnes ;
  - à partir de 1024 px (`lg:`) : trois cartes de bouquet par ligne, titre du héros à 60 px.
- **Accessibilité** : HTML sémantique (`header`, `main`, `section`, `article`, `nav`, `address`, `footer`), textes alternatifs sur les images, contour de focus clavier visible (2 px, décalé de 2 px) et survol sur tous les liens et boutons.
- **Aucun** attribut `style` et aucun CSS en dehors de `src/input.css`.

## Limites connues

- Les liens « Livraison » du menu et du pied de page pointent vers `#livraison` : cette page ne fait pas partie du projet.
- Le lien « Mentions légales » du pied de page est un lien vide (`#`).

## Auteur

Chris, formation Simplon · La F@brique Numérique 41.
