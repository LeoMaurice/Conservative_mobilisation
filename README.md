# Projet Mobilisation Anti Trans

# Requirements
Ce github nécessite [python (version 3.9 de préférence)](https://www.python.org/downloads/release/python-390/), jupyter, [R](https://www.r-project.org/), [RStudio](https://posit.co/products/open-source/rstudio/) et [Quarto](https://quarto.org/).

Il est possible d'installer l'ensemble des libraires python nécessaires avec : 
```pip install -r requirements.txt```

L'ensemble des librairies R devrait s'installer dans le premier bloc du code .qdm

# Explications d'utilisation des codes.

## Analyse

L'analyse est entièrement réalisée R dans le fichier `/src/analyse et figures.qmd` qui peut être facilement lu sur RStudio.

Ce code utilise le métadonnées des organisations `/data/Base de données anti trans.xlsx` et les données textuelles lemmatisées `/data/intermediate/base_lemmatized.csv`.

Après avoir exécuté le premier bloc du .qmd (fonctionne comme un jupyter notebook), les différentes bibliothèques nécessaires devraient s'installer et certaines fonctions importées depuis /src/helpers. A ce moment, l'ensemble des blocs peut être exécuté avec un run all ou un render. Un render est conseillé et devrait donner un html ouvrable et facilement regardable dans un navigateur web.

Il est impératif de mettre `save_figures = F` dans le premier bloc ou dans le cas contraire de créer le dossier /output/results pour avoir les figures dans un dossier.

## Fabrication de la base lemmatisée

Les métadonnées et sites scrappés sont présentés dans le `/data/Base de données anti trans.xlsx`.

Le code `/src/Scrapping_websites.ipynb` réalise les scrappings automatiques des sites avec beaucoup de documents à récupérer.

Les données sont présentes dans le dossier /data. En son sein, le dossier `/data/text` contient notamment les différents tsv (csv tabulé) qui regroupent les différents textes collectés (manuellement ou pas). Deux bases manuelles sont présentes l'une correspondant aux pdf (base manuel 2) et ceux récupérés par copié collé directement dans un fichier excel.

Le code Merging permet de fusionner toutes les bases en `/data/intermediate/base_merged.csv`

Le code Cleaning part de la base fusionnée, supprime les mots les moins fréquent et réalise la base lemmatisée (`/data/base_lemmatized.csv`).

Il est possible d'installer l'ensemble des libraires python nécessaires avec : 
```pip install -r requirements.txt```

# Archive
Les dossiers archives sont là pour un historique personnel des auteurs.

Merci de les ignorer.

# Some ref

[STM explanation](https://raw.githubusercontent.com/bstewart/stm/master/vignettes/stmVignette.pdf)
[STM github](https://github.com/bstewart/stm?tab=readme-ov-file)
[Tidytext](https://www.tidytextmining.com/tfidf.html?q=bind#the-bind_tf_idf-function)