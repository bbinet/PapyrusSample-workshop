.. PapyrusSample workshop documentation master file, created by
   sphinx-quickstart on Thu Feb  9 15:46:04 2012.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

PapyrusSample workshop
======================

Ce workshop à caractère didactique a pour objectif de construire une petite
application basée sur Pyramid et Papyrus, afin de démontrer les possibilités
offertes par ce framework de développement.

Nous procèderons par étapes: à chaque nouvelle section du workshop, vous serez
invités à améliorer l'application, rajouter des fonctionnalités, pour
finalement obtenir l'application PapyrusSample.
Une correction du code associé à chaque étape de ce workshop sera disponible.

Voici les différentes sections que nous allons aborder:

.. toctree::
   :maxdepth: 2

   getting_started.rst

0. Rappels
   (pointeurs vers les docs respectives)

   * Python

   * SqlAlchemy

   * GeoAlchemy

1. Mise en place

   * install de l'environnement python w/ w32api

   * install virtualenv

   * creation d'un venv

   * installation pyramid dans venv

   * mise en place base postgres/postgis
     creation table pois + insertion données

2. Découverte projet pyramid

   * dérouler le scaffold alchemy

   * populate, pserve

   * découvrir le projet généré

   * comprendre la structure du projet
     et aborder les notions clés de pyramid

   * outils de debug (debugtoolbar, pshell)

3. Modifications du projet Pyramid

   * nettoyage du projet pyramid généré et:

   * remplacement view/template my_view/mytemplate.pt par index/index.mako.html

   * création d'une simple carte openlayers avec osm

   * mapping sqlalchemy/geoalchemy de la table pois

   * modifier la view 'index' pour afficher le nombre total de pois

   * bonus task: ajouter des couches carto supplémentaires

4. Update webservice avec Papyrus

   * install papyrus

   * creation webservice papyrus

   * étude protocole mapfish

   * ajout d'un layer vector pour visualiser les données geojson

   * faire également un webservice json custom

------ Fin découverte pyramid et papyrus

------ Début création de l'appli mapfishsample

5. Environnement buildout et déploiement

   * présentation buildout

   * dérouler scaffold c2cpyramid

   * découvrir les fichiers générés

   * découverte de jsbuild

   * installation en environnement apache/mod_wsgi

6. Layout global de l'appli

7. info

8. editing

9. search

10. print

X. Add a formalchemy/geoformalchemy backend interface

X. papyrus_maproxy, papyrus_ogcproxy

TODO:
modifier tout le workshop pour pointer vers le dépot github de camptocamp au
lieu de bbinet: s/bbinet/camptocamp/
