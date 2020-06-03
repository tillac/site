
# Site web tillac-data

<!-- badges: start -->
<!-- badges: end -->

Ce repo contient le site web [tillac](https://www.tillac-data.com/).

## Style

+ La feuille de style scss est dans `assets/scss` qui est généré vers `resources/_gen` ;
+ Les templates html des différentes pages sont dans `layouts` ;
+ Les images pour les posts sont dans `static/img` avec les non encore utilisées dans `unused`.

Le style est inspiré du [thème Cayman pour Hugo](https://github.com/zwbetz-gh/cayman-hugo-theme), avec des adaptations substantielles.

## Éléments globaux

Les éléments globaux sont dans `content`, à la racine.

## Posts de blog

Les posts de blogs sont dans `content/post`.

### Création simple

Pour créer ou mettre à jour des posts de blog :

+ On se sert de l'addin RStudio "New Post" et on ajoute les éléments ;
+ Choisir une image et ajouter dans le YAML : `top_image: '/img/chemin_image.jpg'` avec le bon chemin.

### Création depuis dossier externe

Dans le cas où le post est déjà rédigé à l'extérieur dans un répertoire spécifique sur Github :

+ On fait de même, en créant une enveloppe de post ;
+ On créé un submodule dans `static/post/external` du dossier voulu :

  + On se positionne dans le bon dossier avec `cd static/post/external` ;
  + Puis on fait `git submodule add url_du_rep_git`;

+ On pointe le child du premier chunk (vide) vers `../../static/post/external/chemin_du_Rmd` ;
+ On ajoute l'image.

Certains chemins internes peuvent causer des problèmes. Il faut alors les régler.

Pour mettre à jour le dossier externe : 

+ `git fetch` ;
+ `git merge origin/master`.

L'inspiration de cette démarche est ici : https://timmastny.rbind.io/blog/git-blogdown-projects-workflow/.

Il faut bien penser à revenir dans le dossier source avec git en faisant `cd ../..` sinon les opérations de versioning ne fonctionneront plus.

### Règle de nommage

On nomme le fichier avec l'année en préfixe.
