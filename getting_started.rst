
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


Mise en place de la base de données
-----------------------------------

Pour installer un base de données PostgreSQL et son extension spatiale PostGIS
sous Debian Squeeze, vous pouvez lancer la commande suivante::

    $ sudo aptitude install libgeos-3.2.0 postgresql-8.4 postgis postgresql-8.4-postgis

Pour la mise en place de la base de données, nous avons préparé un jeu de
données de test, ainsi qu'un script de création de la base de données.

Avant de créer la base de données, nous allons créer l'utilisateur www-data
avec des droits limités::

    $ sudo su postgres
    $ createuser -P www-data
    Saisir le mot de passe pour le nouveau rôle : www-data
    Le saisir de nouveau : www-data
    Le nouveau rôle est-il super-utilisateur ? (o/n) n
    Le nouveau rôle est-il autorisé à créer des bases de données ? (o/n) n
    Le nouveau rôle est-il autorisé à créer de nouveaux rôles ? (o/n) n

Vous pouvez maintenant récupérer les données depuis la branche
``workshop-stage1`` du repository MapFishSample:
http://github.com/bbinet/PapyrusSample/tarball/workshop-stage1.
Décompressez l'archive, allez dans le répertoire ``geodata``, puis exécuter le
script (vous pouvez éventuellement adapter les variables au début du script
``create_database.bash`` afin qu'elles correspondent à votre environnement)::

    $ curl -L https://github.com/bbinet/PapyrusSample/tarball/workshop-stage1 | tar zxvf -
    $ cd <untarred directory>/geodata/
    $ sudo su postgres
    $ ./create_database.bash -p

Nous pouvons maintenant vérifier que la base de données a bien été créée et que
des données ont été insérées::

    $ psql -h localhost -U www-data -d papyrus_sample

    papyrus_sample=> select count(*) from poi_osm;
    count 
    -------
        42
    (1 ligne)


Résumé
------

Vous avez donc installé le framework Pyramid dans un virtualenv, et vous avez
mis en place une base de données fonctionnelle contenant des données de test.

Tout est maintenant en place pour passer à la création de votre première
application Pyramid.
