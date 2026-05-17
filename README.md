# Éconologicien

Blog de finances personnelles généré avec [Hugo](https://gohugo.io/) et déployé sur GitHub Pages.

## Structure du projet

```
.
├── hugo.toml              # Configuration Hugo
├── content/
│   └── articles/          # Articles du blog (Markdown)
├── layouts/
│   ├── index.html         # Template de la page d'accueil
│   └── _default/
│       ├── baseof.html    # Template de base (commun à toutes les pages)
│       └── single.html    # Template d'un article
├── static/
│   └── styles.css         # Feuille de styles partagée
├── archetypes/
│   └── default.md         # Archétype pour les nouveaux articles
└── .github/workflows/
    └── deploy.yml         # Pipeline GitHub Actions
```

## Lancer le site en local

1. [Installer Hugo](https://gohugo.io/installation/) (v0.100+)
2. Cloner le dépôt et se placer dedans :
   ```bash
   git clone https://github.com/Maalshekto/econologicien.git
   cd econologicien
   ```
3. Démarrer le serveur de développement :
   ```bash
   hugo server
   ```
4. Ouvrir <http://localhost:1313/econologicien/> dans le navigateur.

## Ajouter un article

1. Créer un nouveau fichier Markdown dans `content/articles/`, par exemple :
   ```bash
   hugo new articles/mon-nouvel-article.md
   ```
2. Éditer le fichier généré : renseigner le `title`, la `date` et écrire le contenu après le front matter.
3. Passer `draft = false` pour que l'article soit publié.
4. Commit + push sur `main`.

## Pipeline GitHub Actions

Le workflow `Deploy GitHub Pages` se déclenche :

- automatiquement sur chaque `push` vers `main`
- manuellement via `workflow_dispatch`

Étapes du pipeline :

1. Checkout du dépôt
2. Installation de Hugo
3. Construction du site (`hugo --minify`) → dossier `public/`
4. Configuration de GitHub Pages
5. Upload de l'artefact (`public/`)
6. Déploiement sur GitHub Pages

## Configuration GitHub Pages

Dans les **Settings** du dépôt → **Pages** :
- Source : **GitHub Actions**
