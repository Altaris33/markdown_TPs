**Application Social Company Blog avec Flask**
===

1. [Description](#Description)
2. [Démarrage & Installation](#Démarrage-&-Installation)
3. [Utilisation avancée](#Utilisation-avancée)
4. [Configuration avancée](#Configuration-avancée)
5. [Extension Personnalisation](#Extension-&-Personnalisation)
6. [Point d'entrée](#Point-d'entrée)
7. [Crédits](#Crédits)
8. [Liens](#Liens)

## Description


Le projet Social Company Blog a pour objectif de créer un système de blogposts afin que des utilisateurs inscrits puissent publier, modifier et supprimer des articles. </br>
Le microframework utilisé est Flask. Flask est un microframework léger créé afin de démarrer des applications légères en simplicité (KISS). Il embarque au démarrage les extensions WerkZeug et Jinja. Au fur et à mesure que le projet gagne en complexité, il est possible d'ajouter des extensions.


## Démarrage & Installation

**Setup**

- Windows </br>
    - Télécharger l'executable pour Windows + variable  d'environnement python à ajouter. </br>
    - Vérifier que PIP est installé -> `_pip help_`. </br>
    - Installer VirtualEnv -> `_pip install virtualenv_`. </br>
    - Récupérer le fichier requirements.txt contenant toutes les dépendances Flask. `pip install -r requirements.txt`. </br>
- Linux and MacOS.  </br>
    - Vérifier la version de Python installée avec `_python3 --version_`.  </br>
    - Récupérer le fichier requirements.txt contenant toutes les dépendences Flask. `_pip install -r requirements.txt_`. </br>

**Architecture du projet**

L'architecture dite *MVC* suit la hiérarchie suivante:

| Elément | Fonction
|---------| --------|
|`app.py`   | fichier exécutable et point d'entrée|
|`__init__.py`| fichir d'initialisation des objets et routes de l'application|
| `models.py` | fichier des modèles|
| `data.sqlite` | fichier du code source de la Base de Données|
| `altariscompanyblog` | dossier principal |
| `users` | dossier des entités Users |
| `blog_posts` | dossier des entités blog_posts |
| `templates` | contient les vues (MVC) du projet |
| `static` | contient les fichiers annexes (CSS, Boostrap, images...)|
| `migrations` | dossier des migrations (BDD)|

**Exécution**
`python app.py`.

**URL racine**
`http://localhost:5000`.

 

## Utilisation avancée

- Utilisateur confirmé
    - Inscription -> /register.
    - Connexion une fois inscrit -> /login.
    - Publication de poste -> /create.
    - Deconnexion -> /logout.
    - Gestion de compte -> /account.
- Développeur
    - Evolution -> gestion des erreurs liées aux identifiants non-existants.
    - Ajout de style sur les vues (CSS, Bootstrap)  
    - Modification de la Base de Données (voir la configuration avancée).

## Configuration avancée

**Développement**
L'application respecte une architecture de type MVC (Model, View, Controller). Pour tout développeur envieux d'apporter des modifications, il est possible d'implémenter de nouvelles fonctionnalités en respectant l'architecture d'origine.

**Exécution** </br>
Exécuter avec la commande `python app.py` en environnement de développement.

**Debuggage** </br>
Débuggage avec le code PIN apparaissant en console une fois l'application lancée.

**Gestion de la Base de Données**

Utiliser `Flask-Migrate`.

- Windows </br>
    - `set FLASK_APP=app.py`.  -> ajout de la variable d'environnement pour Windows.
- Linux  </br>
    - `export FLASK_APP=app.py`. -> ajout de la variable d'environnement pour Linux et MacOS. </br>
    - `flask db init ` -> ajout du répertoire *migrations*. </br>
    - `flask db migrate -m “un message” `-> configure les fichiers dans *migrations*. </br>
    - `flask db upgrade` -> met à jour la base de donnée avec la migration. </br>

## Extension & Personnalisation

Possibilité de déploiement l'application en supprimant le paramètre `Debug` dans le fichier `app.py`.
Récupérer le projet avec`git clone` et appliquer ces propres modifications. </br>
Le framework étant Flask, il permet également l'utilisation d'une librairie gérant les APIs et des services RESTful.

## Point d'entrée

Fichier `app.py`:

```python
from altariscompanyblog import app


if __name__ == '__main__':
    app.run(debug=True)
```

## Crédits

- Remerciements à Jose Portilla, formateur en data sciences et Python.
- Utilisation du site officiel du microframework Flask
- Réalisé par J LAERA.

## Liens
- Documentation Flask : http://flask.palletsprojects.com/en/1.1.x/
- Releases: https://pypi.org/project/Flask/
- Code source: https://github.com/Altaris33/flaskblog