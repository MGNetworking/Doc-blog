# Documentation

* [Python](#python)
* [Sphinx](#sphinx)

## Python

Pour créer le projet

Créer l'environnement virtuel

```shell
python -m venv venv
```

Ce connecté à cet environnement

```shell
.\venv\Scripts\activate
```

Ajouter les dépendances

```shell
pip install -r requirements.txt
```

Puis vérifier les dépendances

```shell
pip freeze
```

## Sphinx

Fair la compilation de la documentation

- powershell

```ps1
./make html
```

- linux

```ps1
make html
```

Après avoir build le projet, ouvrir le dossier ``_build/`` puis ouvrir le fichier index.html 
en utilisant un navigateur