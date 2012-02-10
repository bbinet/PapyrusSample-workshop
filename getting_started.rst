
Mise en place
=============

Installation de l'environnement Python
--------------------------------------

Sous Debian, vous pouvez lancer les commandes suivantes:

Sous Windows, vous devez installer dans l'ordre les dépendances suivantes:

  * Python: la dernière version disponible est la 2.7
    http://www.python.org/getit/releases/2.7.2/

  * Python for Windows extensions
    http://sourceforge.net/projects/pywin32/files/pywin32/Build216/

  * Psycopg2 for windows (win_psycopg)
    http://stickpeople.com/projects/python/win-psycopg/

Création d'un virtualenv
------------------------

Passons maintenant à l'installation de virtualenv et à la création d'un
virtualenv pour ce workshop.

Recupérer la dernière version disponible directement depuis:
https://raw.github.com/pypa/virtualenv/master/virtualenv.py

Une fois ``virtualenv.py`` téléchargé, vous pouvez lancer la commande suivante pour
créer un nouveau virtualenv::

    $ python virtualenv.py venv

Ou sous windows::

    > C:\Python27\python.exe virtualenv.py --system-site-packages venv

.. note::

    Sous windows, nous choisissons de ne pas nous isoler complètement du
    système afin de pouvoir utiliser Psycopg2 qui a été installé au niveau
    système.

Une fois le virtualenv créé, vous pouvez l'activer afin que toutes les
commandes soit exécutées en priorité dans le contexte du virtualenv plutôt que
dans celui de l'environnement système.
Pour activer le virtualenv::

    $ source venv/bin/activate

Ou sous windows::

    > venv\Scripts\activate.bat

Le résultat de cette commande doit modifier l'apparence de l'invite de commande
afin de bien signifier que le virtualenv est activé.
    

Installation de Pyramid
-----------------------

Une fois le virtualenv activé, nous allons installer Pyramid dans ce venv::

    (venv) $ pip install Pyramid

Afin de vérifier que Pyramid a été installé correctement, vous pouvez lancer la
commande::

    (venv) $ pcreate --list
    Available scaffolds:
      alchemy:       Pyramid SQLAlchemy project using url dispatch
      starter:       Pyramid starter project
      zodb:          Pyramid ZODB project using traversal


Mise en place d'une base postgres/postgis
-----------------------------------------

Pour la mise en place de la base de données, nous avons préparé un jeu de
données de test, ainsi qu'un script de création de la base de données.
Vous pouvez d'abord récupérer le données ICI? puis exécuter le script::

    (venv) $ ./create_database.bash -p

TODO: comment récupérer les données et le script???

