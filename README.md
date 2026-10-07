# Obsidian Web Clipper Templates

Mes templates pour [Obsidian Web Clipper](https://obsidian.md/clipper), l'extension officielle d'Obsidian qui enregistre des pages web sous forme de notes Markdown.

Les fichiers sont synchronisés dans iCloud et versionnés sur GitHub.

## Templates

| Template | Fichier | Déclencheurs | Dossier |
|---|---|---|---|
| **Défaut** | `défaut-clipper.json` | Aucun (template de repli) | `Clippings` |
| **AI Chats** | `ai-chats-clipper.json` | ChatGPT, Claude, Gemini, DeepSeek, Perplexity | `Clippings` |
| **GitHub Repositories** | `github-repositories-clipper.json` | Page d'accueil d'un repo GitHub | `Clippings` |
| **Goodreads** | `goodreads-clipper.json` | `goodreads.com/book/` | `References` |
| **Google Maps** | `google-maps-clipper.json` | `google.com/maps/place/` | `References` |
| **Recipes** | `recipes-clipper.json` | Pages avec schema `Recipe`, Joshua Weissman, Marmiton | `Clippings` |
| **Reddit Posts** | `reddit-posts-clipper.json` | Posts `reddit.com/r/.../comments` | `Clippings` |
| **Wikipedia Articles** | `wikipedia-articles-clipper.json` | `*.wikipedia.org/wiki/` | `Clippings` |
| **YouTube Videos** | `youtube-videos-clipper.json` | `youtube.com/watch` | `Clippings` |
| **YouTube Videos (Summary)** | `youtube-videos-(summary)-clipper.json` | `youtube.com/watch` | `Clippings` |

### Ce que fait chaque template

- **Défaut** : titre, auteur, date de publication, image et URL, puis une section `## Notes` vide.
- **AI Chats** : génère un résumé de la conversation en français (500 caractères max) dans un callout `summary`. Nécessite l'Interpreter.
- **GitHub Repositories** : récupère le nom du repo, le propriétaire et la date du dernier commit.
- **Goodreads** : couverture, description repliable, auteurs, genres, ISBN, langue, nombre de pages et note Goodreads (`scoreGr`). Un champ `rating` vide est prévu pour ma propre note. La note porte le titre du livre.
- **Google Maps** : coordonnées extraites de l'URL, adresse, et des champs `type`, `loc` et `rating` à remplir à la main. La note porte le nom du lieu.
- **Recipes** : temps de préparation, de repos, de cuisson et total (lus dans le schema), plus `cuisine` et `rating` à remplir.
- **Reddit Posts** : texte du post, commentaires, auteur, subreddit et date.
- **Wikipedia Articles** : contenu de l'article nettoyé (sans infobox, navbox, tables, etc.) et références converties en notes de bas de page.
- **YouTube Videos** : vidéo intégrée, transcription dans un callout repliable, chaîne, date et durée. Un champ `timestamps` est prévu.
- **YouTube Videos (Summary)** : identique au précédent, avec en plus un résumé en français (350 caractères max) généré par l'Interpreter.

## Conventions

Tous les templates partagent les mêmes propriétés de base :

- `tags` : `clippings` pour le contenu web, `references` pour les fiches (livres, lieux)
- `categories` : lien vers une note de catégorie (`[[Clippings]]`, `[[Books]]`, `[[Places]]`, `[[Recipes]]`)
- `topics` : laissé vide, à remplir après coup
- `image` et `url`

Les clippings sont nommés `YYYY-MM-DD-HHmmss <titre>` pour rester triés chronologiquement. Les fiches de référence (Goodreads, Google Maps) portent simplement le nom de l'objet.

## Installation

1. Installer l'extension [Obsidian Web Clipper](https://obsidian.md/clipper).
2. Ouvrir les paramètres de l'extension, puis **Templates** > **Import**.
3. Sélectionner un ou plusieurs fichiers `.json` de ce dépôt.

Les templates **AI Chats** et **YouTube Videos (Summary)** utilisent l'[Interpreter](https://help.obsidian.md/web-clipper/interpreter), qui doit être activé et configuré avec un fournisseur de modèle dans les paramètres de l'extension.

Pour adapter les templates à un autre vault, il suffit de modifier le champ `path` (dossier de destination) et les valeurs de `categories`.

## Archives

Le dossier `Archives/` contient d'anciennes versions des templates, dont les templates spécifiques à Joshua Weissman et Marmiton, remplacés depuis par le template générique **Recipes**.
