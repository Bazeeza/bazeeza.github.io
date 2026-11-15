# bazeeza.github.io

![HTML5](https://img.shields.io/badge/HTML5-semantic-2b9dff?style=flat-square&labelColor=070d1c&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-design_tokens-3fe0a0?style=flat-square&labelColor=070d1c&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-none-c792ea?style=flat-square&labelColor=070d1c)
![Accessibility](https://img.shields.io/badge/target-WCAG_2.2_AA-ffb454?style=flat-square&labelColor=070d1c)

> **English summary.** Source of the personal portfolio of `bazeeza`, a network and telecommunications technician in training. One static HTML page, two stylesheets, no JavaScript, no web fonts, no build step. Colors come from design tokens shared with the GitHub profile banner, and the markup follows WCAG 2.2 AA practices (landmarks, heading order, visible focus, contrast-checked colors). The site is currently offline.

Portfolio d'une page : présentation, compétences, projets, expérience et contact.

> [!NOTE]
> Le dépôt est **privé** et le site est **hors ligne** pour le moment. Sa remise en ligne est une décision du propriétaire.

## Structure

```text
bazeeza.github.io/
├── index.html              Page unique, en français
├── assets/
│   ├── css/
│   │   ├── tokens.css      Jetons de design : couleurs, polices, espacements
│   │   └── main.css        Composants, ne contient aucune valeur brute
│   └── img/
│       ├── favicon.svg     Icône d'onglet
│       └── topologie.svg   Illustration décorative du héros
└── docs/
    └── design-system.md    Palette, contrastes, typographie, composants, règles d'accessibilité
```

## Choix techniques

| Choix | Pourquoi |
|---|---|
| HTML et CSS seulement | Rien à compiler ni à mettre à jour ; la page fonctionne même si JavaScript est désactivé |
| Jetons de design dans `tokens.css` | La palette du profil GitHub est définie une seule fois ; un changement de couleur touche une seule ligne |
| Polices système | Aucune requête vers un tiers, affichage immédiat |
| Balisage sémantique | Les lecteurs d'écran peuvent passer d'une région ou d'un titre à l'autre |
| Animations coupées avec `prefers-reduced-motion` | Respecte le réglage « réduire les animations » du système |

Le détail des couleurs, des contrastes et des composants est dans [docs/design-system.md](docs/design-system.md).

## Aperçu en local

Il n'y a rien à installer. Ouvrir `index.html` dans un navigateur suffit.

Pour tester la page comme sur un vrai serveur (chemins relatifs, en-têtes), lancer un serveur statique à la racine du dépôt, par exemple :

```bash
python -m http.server 8000
```

puis ouvrir `http://localhost:8000`.

## Vérifier l'accessibilité

1. Naviguer **au clavier seulement** (Tab, Maj+Tab, Entrée) : le lien « Aller au contenu » apparaît en premier, et le focus reste visible partout.
2. Réduire la fenêtre sous 620 px : le menu reste accessible sous l'invite.
3. Activer « réduire les animations » dans le système : l'illustration du héros s'arrête.
4. Outils des navigateurs : Lighthouse (Chrome) ou l'inspecteur d'accessibilité (Firefox).

## Contact

[info@bazeeza.ca](mailto:info@bazeeza.ca)
