# Doc projet

- [Run](#run)
- [Erreur de permission](#erreur-de-permission)

## Run

Pour lancer un projet Sphinx et générer la documentation, voici les étapes principales à suivre :

1. Créer l'environnement virtuel Dans le répertoire de votre projet, exécutez :

   ```shell
   python -m venv env
   ```

   Cela crée un dossier env qui contient l'environnement virtuel.

2. Activer l'environnement virtuel
   Sous Windows :

   ```shell
   .\env\Scripts\activate
   ```

   Sous Linux/macOS :

   ```shell
   source env/bin/activate
   ```

Une fois activé, vous verrez généralement le nom de l'environnement virtuel (par exemple, (env)) au début de votre invite de commande.

3. Installer les dépendances dans l'environnement Maintenant que l'environnement est activé, installez les dépendances spécifiées dans requirements.txt :

   ```shell
   pip install -r requirements.txt
   ```

4. Vérifiez que Sphinx est installé Vérifiez que Sphinx est bien disponible dans cet environnement :

   Le fichier conf.py contient les configurations du projet.
   Les fichiers .rst (comme index.rst) définissent le contenu de la documentation.

   ```shell
   sphinx-build --version
   ```

5. Construire la documentation
   Utilisez le fichier Makefile (Linux/macOS) ou make.bat (Windows) pour construire la documentation dans différents formats.

- Pour générer la documentation au format HTML, exécutez :

  - Sur Linux/macOS

  ```shell
  make html
  ```

  - Sur Windows

  ```shell
  ./make.bat html
  ```

4. Consulter la documentation générée
   Après avoir exécuté la commande ./make.bat html, la documentation HTML générée se trouve généralement dans le dossier \_build/html/ du projet. Voici comment ouvrir la documentation :

- Étape 1 : Localiser le fichier index.html
  Naviguez dans le répertoire où votre projet est situé, puis ouvrez le dossier `\_build/html`. Le fichier principal de la documentation est index.html.

- Étape 2 : Ouvrir dans un navigateur
  Utilisez un gestionnaire de fichiers pour localiser le fichier index.html dans` \_build/html`. Double-cliquez sur `index.html`. Cela ouvrira la documentation dans votre navigateur par défaut.

* Étape 3 : (Optionnel) Lancer un serveur HTTP local
  Si vous préférez naviguer sur un serveur local pour faciliter l'accès, vous pouvez utiliser Python pour lancer un serveur HTTP dans le dossier` \_build/html` :

  Ouvrez un terminal et naviguez dans le dossier \_build/html :

  ```shell
      cd \_build/html
  ```

  Lancez un serveur local avec Python :

  ```shell
  python -m http.server
  ```

  ou directement :

  ```shell
  python -m http.server --directory _build/html
  ```

  Ensuite, ouvrez un navigateur et accédez à http://localhost:8000.
  Si vous avez des erreurs ou des besoins spécifiques, précisez-les pour que je puisse vous aider davantage !

## Erreur de permission

Dans le cas d'une erreur de permission qui nécessite une mise a jour ou une installation de `pip`, Voici comment résoudre ce problème :

1. Utiliser l'option --user
   Ajoutez l'option --user pour installer pip dans votre répertoire utilisateur, ce qui évite les problèmes de permissions globaux :

   ```shell
   python.exe -m pip install --upgrade pip --user
   ```

2. Exécuter en tant qu'administrateur
   Si vous souhaitez mettre à jour pip globalement, exécutez votre terminal en tant qu'administrateur :

   1. Fermez votre terminal actuel.
   2. Recherchez "cmd" ou "PowerShell" dans le menu démarrer.
   3. Faites un clic droit et choisissez Exécuter en tant qu'administrateur.
   4. Réessayez la commande :

   ```shell
       python.exe -m pip install --upgrade pip
   ```

3. Assurer l'accès au répertoire
   Si vous avez toujours des problèmes :

   - Vérifiez que votre compte utilisateur a bien les permissions d'accès au répertoire `c:\python312\lib\site-packages\`.
   - Vous pouvez temporairement désactiver l'antivirus ou les outils de protection si cela bloque l'accès.

Après ces étapes, vous devriez pouvoir mettre à jour pip sans problème.
