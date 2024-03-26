# Projet Mobilisation Anti Trans

# Requirements
Ce github nécessite [python (version 3.9 de préférence)](https://www.python.org/downloads/release/python-390/), jupyter, [R](https://www.r-project.org/), [RStudio](https://posit.co/products/open-source/rstudio/) et [Quarto](https://quarto.org/).

Il est possible d'installer l'ensemble des libraires python nécessaires avec : 
```pip install -r requirements.txt```

L'ensemble des librairies R devrait s'installer dans le premier bloc du code de `/src/analyse et figures.qmd`.

# Explications d'utilisation des codes.

## Analyse

Les analyses sont entièrement réalisées en R dans le fichier `/src/analyse et figures.qmd` qui peut être facilement lu et exécuté sur RStudio.

Ce code utilise le métadonnées des organisations collectées dans `/data/Base de données anti trans.xlsx` et les données textuelles lemmatisées `/data/intermediate/base_lemmatized.csv`.

Après avoir exécuté le premier bloc du .qmd (fonctionne comme un jupyter notebook), les différentes bibliothèques nécessaires devraient s'installer et certaines fonctions importées depuis `/src/helpers`. A ce moment, l'ensemble des blocs peut être exécuté avec un run all ou un render. Un render est conseillé et devrait donner un html consultable dans un navigateur web.

Il est impératif de mettre `save_figures = F` dans le premier bloc ou dans le cas contraire de créer le dossier `/output/results` pour avoir les figures dans ce dossier.

## Fabrication de la base lemmatisée

Les métadonnées et sites scrappés sont présentés dans le `/data/Base de données anti trans.xlsx`.

Les données sont présentes dans le dossier `/data`. 

En son sein, le dossier `/data/text` contient notamment les différents tsv (csv tabulé) qui regroupent les différents textes collectés (manuellement ou pas). Deux bases manuelles sont présentes l'une correspondant aux pdf (stocké dans `/data/pdf`, mise en base sous le nom de `manuel2.tsv`, avec un jupyter notebook associé `src/Creation base manuelle 2.ipynb`) et ceux récupérés par copié collé directement dans un fichier excel.

Les bases intermédiaires servant à d'autres étapes dans le processus sont mise dans `/data/intermediate`.

Le code Merging permet de fusionner toutes les bases en `/data/intermediate/base_merged.csv`

Le code Cleaning part de la base fusionnée, supprime les mots les moins fréquents et réalise la base lemmatisée (`/data/intermediate/base_lemmatized.csv`).

Il est possible d'installer l'ensemble des libraires python nécessaires avec : 
```pip install -r requirements.txt```

## Exploration des noms de domaines

`src/scrapping_websites.ipynb` permet de créer des réseaux interactifs de noms de domaines présents en lien sur des sites qui servent d'"origine" (seed). On a pu identifier quelques sites à partir de la Petite Sirène principalement avec cette méthode.

`data/network/` contient les données du scrapping de la Petite Sirène car l'opération est longue. Le code précédent peut permettre de le revoir de façon reproductible.

Malgré toutes ces remarques, cette partie du code sur les réseaux vu qu'elle était exploratoire est aussi la moins reproduite et reproductible. En particulier les données des différents réseaux trouvées ne pouvaient être mises sur le github pour une question de place.

# Archive
Les dossiers archives sont là pour un historique personnel des auteurs.

Merci de les ignorer.

# Some ref

[STM explanation](https://raw.githubusercontent.com/bstewart/stm/master/vignettes/stmVignette.pdf)
[STM github](https://github.com/bstewart/stm?tab=readme-ov-file)
[Tidytext](https://www.tidytextmining.com/tfidf.html?q=bind#the-bind_tf_idf-function)