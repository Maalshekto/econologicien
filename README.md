# Éconologicien

Blog statique (GitHub Pages) avec des exemples d'articles sur les finances personnelles.

## Structure du projet

- `index.html` : page d'accueil qui liste les articles
- `articles/` : pages HTML des articles
- `styles.css` : styles partagés
- `.github/workflows/deploy.yml` : pipeline GitHub Actions de déploiement vers GitHub Pages

## Ajouter un article

1. Créer un nouveau fichier HTML dans `articles/`, par exemple `articles/mon-nouvel-article.html`.
2. Utiliser la structure des articles existants (titre, contenu, lien de retour).
3. Ajouter le lien vers cet article dans `index.html` (section `Articles récents`).
4. Commit + push sur `main`.

## Pipeline GitHub Actions

Le workflow `Deploy GitHub Pages` se déclenche :

- automatiquement sur chaque `push` vers `main`
- manuellement via `workflow_dispatch`

Étapes du pipeline :

1. Checkout du dépôt
2. Configuration de GitHub Pages
3. Upload de l'artefact statique (le contenu du dépôt)
4. Déploiement sur GitHub Pages

## Configuration GitHub Pages

Dans les paramètres du dépôt (`Settings > Pages`) :

- Source : **GitHub Actions**

Ensuite, l'URL du site déployé est fournie dans le job de déploiement.
