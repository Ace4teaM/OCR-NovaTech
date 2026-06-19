# Demande

Corrections à apporter sous 48h soit avant dimanche 21 juin 9h :

1. Compléter le pyproject.toml avec toutes les dépendances utilisées.
2. Ajouter un boxplot intégrant la cible a_quitte_l_entreprise.
3. Ajouter deux transformations réelles avec .apply().
4. Montrer explicitement la suppression de variables redondantes à partir de la matrice de corrélation.
5. Clarifier ou renforcer l’encodage des variables qualitatives.
6. Ajouter la stratification dans le train_test_split.
7. Ajouter moyenne et écart-type des métriques en validation croisée.
8. Ajouter la courbe Précision-Rappel.
9. Justifier le seuil de classification à partir de cette courbe.
10. Exécuter réellement la GridSearch et afficher les meilleurs paramètres.
11. Ajouter une seconde méthode de feature importance globale.
12. Ajouter Beeswarm SHAP, deux SHAP scatter plots colorés et deux waterfall plots
13. Corriger les conclusions métier trop affirmatives : causes racines, salaire, heures supplémentaires.
14. Clarifier le risque de data leakage lié au sondage.
15. Corriger les incohérences de la matrice de confusion, du recall et des faux positifs.
16. Réexécuter tous les notebooks dans l’ordre et mettre à jour la présentation avec les résultats corrigés.
17. Ajouter une diapo de recommandations RH formalisées, avec des conseils  opérationnels directement reliés aux résultats de l’étude.


Je vais également réécouter l'échange.

Déposer les livrables dans la partie évaluation et répondre à ce message pour m'avertir du dépôt.



# Actions

Voici les actions mises en place pour corriger les manquements.

## 1. Compléter le pyproject.toml avec toutes les dépendances utilisées.

Voici l'arbre des dépendances créé avec `uv tree`.

```
technova v0.1.0
├── dice-ml v0.12
│   ├── jsonschema v4.26.0
│   │   ├── attrs v26.1.0
│   │   ├── jsonschema-specifications v2025.9.1
│   │   │   └── referencing v0.37.0
│   │   │       ├── attrs v26.1.0
│   │   │       ├── rpds-py v2026.5.1
│   │   │       └── typing-extensions v4.15.0
│   │   ├── referencing v0.37.0 (*)
│   │   └── rpds-py v2026.5.1
│   ├── lightgbm v4.6.0
│   │   ├── numpy v2.4.6
│   │   └── scipy v1.17.1
│   │       └── numpy v2.4.6
│   ├── numpy v2.4.6
│   ├── pandas v3.0.3
│   │   ├── numpy v2.4.6
│   │   ├── python-dateutil v2.9.0.post0
│   │   │   └── six v1.17.0
│   │   └── tzdata v2026.2
│   ├── raiutils v0.4.2
│   │   ├── numpy v2.4.6
│   │   ├── pandas v3.0.3 (*)
│   │   ├── requests v2.34.2
│   │   │   ├── certifi v2026.6.17
│   │   │   ├── charset-normalizer v3.4.7
│   │   │   ├── idna v3.18
│   │   │   └── urllib3 v2.7.0
│   │   ├── scikit-learn v1.9.0
│   │   │   ├── joblib v1.5.3
│   │   │   ├── narwhals v2.22.0
│   │   │   ├── numpy v2.4.6
│   │   │   ├── scipy v1.17.1 (*)
│   │   │   └── threadpoolctl v3.6.0
│   │   └── scipy v1.17.1 (*)
│   ├── scikit-learn v1.9.0 (*)
│   ├── tqdm v4.68.2
│   │   └── colorama v0.4.6
│   └── xgboost v3.2.0
│       ├── numpy v2.4.6
│       └── scipy v1.17.1 (*)
├── fastparquet v2026.5.0
│   ├── cramjam v2.11.0
│   ├── fsspec v2026.4.0
│   ├── numpy v2.4.6
│   ├── packaging v26.2
│   └── pandas v3.0.3 (*)
├── ipykernel v7.2.0
│   ├── comm v0.2.3
│   ├── debugpy v1.8.20
│   ├── ipython v9.14.0
│   │   ├── colorama v0.4.6
│   │   ├── decorator v5.3.1
│   │   ├── ipython-pygments-lexers v1.1.1
│   │   │   └── pygments v2.20.0
│   │   ├── jedi v0.20.0
│   │   │   └── parso v0.8.7
│   │   ├── matplotlib-inline v0.2.2
│   │   │   └── traitlets v5.15.0
│   │   ├── prompt-toolkit v3.0.52
│   │   │   └── wcwidth v0.7.0
│   │   ├── psutil v7.2.2
│   │   ├── pygments v2.20.0
│   │   ├── stack-data v0.6.3
│   │   │   ├── asttokens v3.0.1
│   │   │   ├── executing v2.2.1
│   │   │   └── pure-eval v0.2.3
│   │   └── traitlets v5.15.0
│   ├── jupyter-client v8.8.0
│   │   ├── jupyter-core v5.9.1
│   │   │   ├── platformdirs v4.10.0
│   │   │   └── traitlets v5.15.0
│   │   ├── python-dateutil v2.9.0.post0 (*)
│   │   ├── pyzmq v27.1.0
│   │   ├── tornado v6.5.6
│   │   └── traitlets v5.15.0
│   ├── jupyter-core v5.9.1 (*)
│   ├── matplotlib-inline v0.2.2 (*)
│   ├── nest-asyncio v1.6.0
│   ├── packaging v26.2
│   ├── psutil v7.2.2
│   ├── pyzmq v27.1.0
│   ├── tornado v6.5.6
│   └── traitlets v5.15.0
├── matplotlib v3.10.9
│   ├── contourpy v1.3.3
│   │   └── numpy v2.4.6
│   ├── cycler v0.12.1
│   ├── fonttools v4.63.0
│   ├── kiwisolver v1.5.0
│   ├── numpy v2.4.6
│   ├── packaging v26.2
│   ├── pillow v12.2.0
│   ├── pyparsing v3.3.2
│   └── python-dateutil v2.9.0.post0 (*)
├── pandas v3.0.3 (*)
├── scikit-learn v1.9.0 (*)
├── seaborn v0.13.2
│   ├── matplotlib v3.10.9 (*)
│   ├── numpy v2.4.6
│   └── pandas v3.0.3 (*)
├── shap v0.52.0
│   ├── cloudpickle v3.1.2
│   ├── llvmlite v0.47.0
│   ├── numba v0.65.1
│   │   ├── llvmlite v0.47.0
│   │   └── numpy v2.4.6
│   ├── numpy v2.4.6
│   ├── packaging v26.2
│   ├── pandas v3.0.3 (*)
│   ├── scikit-learn v1.9.0 (*)
│   ├── scipy v1.17.1 (*)
│   ├── slicer v0.0.8
│   └── tqdm v4.68.2 (*)
└── xgboost v3.2.0 (*)
(*) Package tree already displayed
```

et voici les dépendances enregistrées dans `pyproject.toml`

```
dependencies = [
    "dice-ml>=0.12",
    "fastparquet>=2026.5.0",
    "ipykernel>=7.2.0",
    "matplotlib>=3.10.9",
    "pandas>=3.0.3",
    "scikit-learn>=1.9.0",
    "seaborn>=0.13.2",
    "shap>=0.52.0",
    "xgboost>=3.2.0",
]
```

ce dernier correspond à la racine des dépendances créé avec `uv add`, donc techniquement il ne manque pas de dépendances au projet.

Cependant, nous pouvons partir du principe que les sous-dépendances utilisées par les `import` dans le code doivent être importées individuellement à la racine, dans ce cas voici les dépendances manquantes:

```
dependencies = [
    "numpy>=2.4.6"
]
```

Un test de recréation d'un nouvel environnement virtuel confirme ce cas.