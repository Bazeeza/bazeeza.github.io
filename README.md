# bazeeza.github.io

![HTML5](https://img.shields.io/badge/HTML5-semantic-2b9dff?style=flat-square&labelColor=070d1c&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS-design_tokens-3fe0a0?style=flat-square&labelColor=070d1c&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-none-c792ea?style=flat-square&labelColor=070d1c)
![Accessibility](https://img.shields.io/badge/target-WCAG_2.2_AA-ffb454?style=flat-square&labelColor=070d1c)

> **English summary.** Source of the personal portfolio of `bazeeza`, a network and telecommunications technician in training. One static HTML page, two stylesheets, no JavaScript, no web fonts, no build step. Colors come from design tokens shared with the GitHub profile banner, and the markup follows WCAG 2.2 AA practices (landmarks, heading order, visible focus, contrast-checked colors). The site is currently offline.

Portfolio d'une page : présentation, compétences, projets (dépôts phares, projets de cours, autres réalisations), expérience et contact.

> [!NOTE]
> Le dépôt est **privé** et le site est **hors ligne** pour le moment. Sa remise en ligne est une décision du propriétaire ; les étapes sont dans [docs/mise-en-ligne.md](docs/mise-en-ligne.md).

## Structure

```text
bazeeza.github.io/
├── index.html              Page unique, en français
├── 404.html                Page « introuvable » servie par GitHub Pages (noindex)
├── robots.txt              Règles pour les robots, liste les sitemaps du domaine
├── sitemap.xml             Plan du site (une seule URL)
├── assets/
│   ├── css/
│   │   ├── tokens.css      Jetons de design : couleurs, polices, espacements
│   │   └── main.css        Composants, ne contient aucune valeur brute
│   └── img/
│       ├── favicon.svg     Icône d'onglet
│       └── topologie.svg   Illustration décorative du héros
└── docs/
    ├── design-system.md    Palette, contrastes, typographie, composants, règles d'accessibilité
    └── mise-en-ligne.md    Liste de vérification avant de republier le site
```

## Choix techniques

| Choix | Pourquoi |
|---|---|
| HTML et CSS seulement | Rien à compiler ni à mettre à jour ; la page fonctionne même si JavaScript est désactivé |
| Jetons de design dans `tokens.css` | La palette du profil GitHub est définie une seule fois ; un changement de couleur touche une seule ligne |
| Polices système | Aucune requête vers un tiers, affichage immédiat |
| Balisage sémantique | Les lecteurs d'écran peuvent passer d'une région ou d'un titre à l'autre |
| Animations coupées avec `prefers-reduced-motion` | Respecte le réglage « réduire les animations » du système |
| Animations en `transform` et `opacity` seulement | Le navigateur les confie au compositeur : aucun repeint de la page à chaque image |
| `color-scheme: dark` | Le navigateur peint le fond sombre avant d'avoir reçu le CSS : pas d'éclair blanc au chargement |
| Feuille d'impression | Un recruteur peut imprimer la page ou l'enregistrer en PDF : texte noir sur blanc, adresses des projets imprimées |

Le détail des couleurs, des contrastes et des composants est dans [docs/design-system.md](docs/design-system.md).

## Poids de la page

Mesuré avec `wc -c` le 2026-11-18, fichiers non compressés :

| Fichier | Octets |
|---|---|
| `index.html` | 22 083 |
| `assets/css/main.css` | 14 399 |
| `assets/css/tokens.css` | 2 807 |
| `assets/img/topologie.svg` | 2 235 |
| `assets/img/favicon.svg` | 440 |
| **Total de la page d'accueil** | **41 964 (5 requêtes)** |

Les règles d'impression (`@media print`) font partie des deux feuilles de style : elles ne coûtent aucune requête de plus.

Aucune police, aucun script exécutable, aucune ressource d'un tiers. Le bloc `application/ld+json` de `index.html` est une donnée lue par les moteurs de recherche, pas du JavaScript.

## Référencement (SEO)

| Élément | Où | Rôle |
|---|---|---|
| `title` et `meta description` | `index.html` | Titre et résumé affichés dans les résultats de recherche (description sous 160 caractères) |
| `link rel="canonical"` | `index.html` | Une seule adresse officielle pour la page |
| Open Graph et `twitter:card` | `index.html` | Aperçu du lien collé dans LinkedIn, Teams ou Slack |
| Données structurées `Person` | `index.html` | Uniquement des faits déjà visibles sur la page |
| `robots.txt` | racine | Les robots lisent seulement celui de la racine du domaine : il liste aussi le sitemap de `thm-badge-finder`, servi sous le même domaine |
| `sitemap.xml` | racine | Plan du site |
| `404.html` | racine | `noindex`, chemins absolus (`/assets/...`) car la page peut être servie à n'importe quelle profondeur |

> [!NOTE]
> Il n'y a pas encore d'image `og:image` : la plupart des robots d'aperçu refusent le SVG. Une image PNG de 1200 × 630 px aux couleurs de la bannière reste à produire.

**Reference :** [Google Search Central, SEO Starter Guide](https://developers.google.com/search/docs/fundamentals/seo-starter-guide) · [The Open Graph protocol](https://ogp.me/) · [sitemaps.org](https://www.sitemaps.org/protocol.html) · [GitHub Docs, Creating a custom 404 page](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-custom-404-page-for-your-github-pages-site)

## Sources des projets

Chaque carte de la section « Projets » résume un dépôt. Le texte reprend ce que dit le README de ce dépôt : aucun chiffre ni résultat qui n'y figure pas. Quand un dépôt change (nouvelle version, nouveau runbook), sa carte doit être relue.

| Groupe | Carte | Source | Visibilité de la source |
|---|---|---|---|
| Projets phares | Technical Runbooks | [Bazeeza/Technical-Runbooks](https://github.com/Bazeeza/Technical-Runbooks) | Public |
| Projets phares | Helpdesk Toolkit | [Bazeeza/helpdesk-toolkit](https://github.com/Bazeeza/helpdesk-toolkit) | Public |
| Projets phares | Homelab Infrastructure | [Bazeeza/homelab-infrastructure](https://github.com/Bazeeza/homelab-infrastructure) | Public |
| Projets de cours | Téléphonie IP FreePBX | Aucun dépôt (description fournie par le propriétaire) | — |
| Projets de cours | Réseaux Cisco et Zabbix | Bazeeza/Projets-Runbooks, cours 420-H63 et 420-H66 | **Privé** |
| Projets de cours | Durcissement CIS Benchmark | Bazeeza/Projets-Runbooks, cours 420-H34 | **Privé** |
| Projets de cours | Services Internet sur AWS | Bazeeza/Projets-Runbooks (420-H66) et [Bazeeza/AutomationHub](https://github.com/Bazeeza/AutomationHub) | Privé / public |
| Autres réalisations | TryHackMe Badge Finder | [Bazeeza/thm-badge-finder](https://github.com/Bazeeza/thm-badge-finder) | Public |

> [!NOTE]
> Les liens des cartes Cisco et CIS mènent à `Projets-Runbooks`, qui est **privé** : un visiteur verrait une erreur 404. Avant de remettre le site en ligne, il faut soit rendre ce dépôt public (après avoir vérifié tout son historique), soit retirer ces deux liens.

## Aperçu en local

Il n'y a rien à installer. Ouvrir `index.html` dans un navigateur suffit.

Pour tester la page comme sur un vrai serveur (chemins relatifs, en-têtes), lancer un serveur statique à la racine du dépôt, par exemple :

```bash
python -m http.server 8000
```

puis ouvrir `http://localhost:8000`.

La page `404.html` utilise des chemins absolus (`/assets/...`) : ouverte directement depuis le disque, elle s'affiche sans style. Avec le serveur local, ouvrir `http://localhost:8000/404.html` pour la voir comme en ligne.

## Vérifier l'accessibilité

1. Naviguer **au clavier seulement** (Tab, Maj+Tab, Entrée) : le lien « Aller au contenu » apparaît en premier, et le focus reste visible partout.
2. Réduire la fenêtre sous 620 px : le menu passe sous l'invite, sur deux lignes au besoin, sans défilement horizontal ; la barre n'est plus collante.
3. Réduire sous 520 px (mode appareil des outils de développement, par exemple 375 px de large) : titre et métadonnées des cartes l'un sous l'autre, faits « libellé puis valeur ».
4. Activer « réduire les animations » dans le système : l'illustration du héros et la pastille d'état s'arrêtent.
5. Sur un écran tactile (ou en émulation tactile), les liens du menu, les boutons et les liens des cartes font au moins 44 px de haut.
6. Lecteur d'écran (NVDA, VoiceOver) : les fragments anglais (`./about`, `LINK STATUS: UP`) sont lus avec une voix anglaise ; la liste des liens annonce « voir les runbooks Technical Runbooks » plutôt que six « voir le… » identiques.
7. Outils des navigateurs : Lighthouse (Chrome) ou l'inspecteur d'accessibilité (Firefox).
8. Aperçu avant impression (Ctrl+P) : fond blanc, aucune barre de menu ni bouton, aucune carte coupée en deux, adresse imprimée après chaque lien de projet.

## Contact

[info@bazeeza.ca](mailto:info@bazeeza.ca)
