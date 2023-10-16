.. ghoverblog to doc documentation master file, created by
   sphinx-quickstart on Mon Oct 18 00:16:46 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Documentation du blog **ghoverblog** !
========================================

Ce projet a plusieurs objectif. Il constitue une base d’expérience solide en création,
gestion et mise à jour d’un site internet. 

.. image:: doc/image/decoration.jpg
    :width: 250
    :alt: image décoration informatique
    :align: left

L'objectif de ce blog et de posté des articles portant sur l'informatique faisant référence a d'autre article 
ou des tutoriel.

Un espace commentaire sera dédier à chaque article permettant d'avoir un échange entre les utilisateurs connecter au site 
qui souhaiterai intervenir sur l'article.

Cette documentation permet de rassemblé tout les informations concernant la gestion et la création du site.  
Dans cette objectif, cette documentation servira d'aide-mémoire sur les choix et la comprehension.

Pour résumer ce cette documentation permettra :

#. La création et la gestion d'un serveur virtuelle 

   * La création d'une machine virtuelle linux ``Ubuntu``, sont administration distance via le terminal
   * La partie réseau avec l'achat du nom de domaines la gestion des sous domaines.
   * La gestion d'un serveur Proxy avec ``Apache serveur`` pour la gestion des flux entrant sortant.
   * La création d'une base de données ``PostgreSQL`` avec la gestion des permissions et la gestion sur le réseau local.

#. La gestion de la sécurité du serveur et du site 
 
   * La gestion du pare-feu pour sécurisé tous les ports.
   * La création d'un micro service de sécurité ``Keycloak`` avec la connection de celui-ci à Postgresql.

#. La parti mise en service du site 
 
   * La parti Devops avec ``Jenkins`` qui permet la mise en production du site en correspondance avec ``Github``  

.. Information sur serveur virtuelle Ubuntu 
.. toctree::
   :maxdepth: 2
   :caption: Ubuntu Serveur

   doc/Serveur/Installation du serveur Ubuntu
   doc/Serveur/Connexion SSH
   doc/Serveur/PostgreSQL
   doc/Serveur/Jenkins
   doc/Serveur/Apache serveur
   doc/Serveur/Tomcat
   doc/Serveur/Production


   doc/Serveur/Installation/Git serveur
   doc/Serveur/Configuration/Attribution d'une adresse IP fixe
   doc/Serveur/Configuration/Liste des paths 

.. Info sur base de données
.. toctree::
   :maxdepth: 2
   :caption: Base de données/Postgresql :
   
   doc/Base de données/Postgresql/configuration
   doc/Base de données/Model conceptuelle de données
   doc/Base de données/Model logique de données
   doc/Base de données/Les Script

.. Configuration Apache serveur
.. toctree::
   :maxdepth: 2
   :caption: Apache serveur :

   doc/Apache serveur/Configuration

   .. Sécurité du serveur
.. toctree::
   :maxdepth: 2
   :caption: Sécurité 

   doc/Sécurité/pare-feu
   doc/Sécurité/SSL

.. Information sur la parti back-end Micro service Spring
.. toctree::
   :maxdepth: 2
   :caption: back-end :

   doc/back-end/L'architecture du back-end
   doc/back-end/Le stokage des données utiliseur

.. Information sur la parti Front-end avec angular
.. toctree::
   :maxdepth: 2
   :caption: Front-end :

   doc/Front-end/Le template utilisé
   doc/Front-end/L'architecture du Front-end 

.. Sécurité du serveur
.. toctree::
   :maxdepth: 2
   :caption: Keycloak :

   doc/Keycloak/Qu'est-ce que Keycloak
   doc/Keycloak/Le protocole OIDC
   doc/Keycloak/Cas d'utilisation
   doc/Keycloak/Architecture
   doc/Keycloak/Le mode Standalone
   doc/Keycloak/Gestion de la base de données
   doc/Keycloak/Déclartion et chargement du driver
   doc/Keycloak/Configuration d'un Domaine

.. Information sur la parti production
.. toctree::
   :maxdepth: 2
   :caption: Dévops :

   doc/Dévops/Github
   doc/Dévops/Jenkins/Description
   doc/Dévops/Jenkins/Webhooks et Job
   doc/Dévops/Articture Dev/prod


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
