# PIXO, créateur de pixels

Éditeur d'icônes "Pixel Art" autonome, exécuté entièrement dans le navigateur.

[![License](https://img.shields.io/badge/License-Apache_2.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat&logo=html5&logoColor=white)](https://fr.wikipedia.org/wiki/Hypertext_Markup_Language)
[![JavaScript](https://img.shields.io/badge/JavaScript-323330?style=flat&logo=javascript&logoColor=F7DF1E)](https://fr.wikipedia.org/wiki/JavaScript)
[![CSS](https://img.shields.io/badge/CSS-563d7c?&style=flat&logo=css3&logoColor=white)](https://fr.wikipedia.org/wiki/Feuilles_de_style_en_cascade)

## Description

PIXO est une page web autonome (`PIXO.HTML`) dédiée à la création et la retouche d'icônes de petites dimensions, jusqu'à 64x64 pixels. L'interface est adaptée au navigateur en HTML, CSS et JavaScript pur, sans framework ni bundler.

## Outils

- **Sélection rectangulaire** : "marching ants", voile bleu, déplacement par drag, copier/couper/coller
- **Lasso** : sélection libre tracée à la souris, masque pixel par pixel
- **Baguette magique** : sélection des pixels contigus de même couleur sur le calque actif
- **Crayon** : tracé Bresenham, taille (1, 2, 3, 4, 6, 8 px) et forme (carré, rond, triangle, losange) configurables
- **Remplissage** : flood fill avec deux modes (contigu, global) et tolérance 0 à 100, avec replay live
- **Gomme** : effacement transparent, taille et forme partagées avec le crayon
- **Pipette** : échantillonne la couleur visible, alimente la couleur active (bouton gauche ou bouton droite)
- **Tampon de recopie** : verrouillage de la source via Ctrl+clic, hérite de la taille et forme du pinceau

## Fonctionnalités

- Système de calques avec opacité et 7 modes de fusion (`normal`, `multiply`, `additive`, `difference`, `negate`, `screen`, `xor`)
- Modale de paramètres par calque (renommage, opacité, mode de fusion, visibilité)
- Deux couleurs actives gauche/droite, échange par `X`
- Panneau palette : 8 couleurs récentes + top 32 couleurs de l'icône courante
- Miroir horizontal, miroir vertical, rotation libre avec aperçu temps réel
- Redimensionnement avec ancrage 3x3 conservant tous les calques
- Import par drag-drop avec module de grille pour les images au-dela de 64 px
- Export PNG de la composition finale
- Format projet `.pixo` (ZIP contenant `metadata.json` et un PNG par calque)
- Historique annuler/refaire (50 entrées)
- Persistance automatique dans `localStorage`
- Damier de transparence et grille 8x8 en overlay
- Zoom à la molette
- Barre d'état avec coordonnées du curseur

## Raccourcis clavier

- `Ctrl+Z` / `Ctrl+Y` : annuler / rétablir
- `Ctrl+A` / `Ctrl+D` : tout sélectionner / désélectionner
- `Ctrl+C` / `Ctrl+X` / `Ctrl+V` : copier / couper / coller
- `Ctrl+S` : enregistrer le projet `.pixo`
- `Ctrl+Maj+S` : exporter en PNG
- `Ctrl+O` : ouvrir un projet
- `X` : échanger les couleurs gauche et droite
- `Suppr` : effacer la sélection
- `Échap` : valider le flottant et désélectionner

## Langues supportées

Quinze langues, sélectionnables dans le header et persistées dans `localStorage` :

- Français (fr), Anglais (en) : intégrées dans `PIXO.HTML`
- Tchèque (cs), Danois (da), Allemand (de), Grec (el), Espagnol (es), Italien (it), Néerlandais (nl), Norvégien (no), Polonais (pl), Portugais (pt), Roumain (ro), Russe (ru), Suédois (sv) : chargées depuis `LANG/PIXO-XX.JS`

Détection automatique de la langue au démarrage via `navigator.language`, repli sur l'anglais si elle est introuvable.

## Technologies

- **HTML5** : structure et canvas
- **CSS3** : interface, variables `:root` pour la palette
- **JavaScript Vanilla** : logique en Immediately Invoked Function Expression(IIFE), sans dépendance
- **Phosphor Icons** : police d'icônes issue du CDN unpkg, version 2.1.2 : [Icônes Phosphor](https://phosphoricons.com/)

## Installation

1. Télécharger `PIXO.HTML` et le dossier `lang/` (ou cloner ce repository)
2. Ouvrir `PIXO.HTML` dans un navigateur moderne
3. Aucune installation, aucun serveur, aucune compilation

## Auteur

- Le-Stef

## Contribution

Les contributions sont les bienvenues. N'hésitez pas à proposer des améliorations ou à signaler des bugs.

## Licence

Ce projet est distribué sous licence **Apache 2.0**. Voir le fichier [LICENSE](LICENSE) pour plus de détails.
