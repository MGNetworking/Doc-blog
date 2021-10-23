.. ghoverblog to doc documentation master file, created by
   sphinx-quickstart on Mon Oct 18 00:16:46 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to ghoverblog to doc's documentation!
=============================================

Les objectifs de ce projet sont multiples, il constitue une base d’expérience en création, gestion et mise à jour
d’un site internet. 

#. La création et la gestion d'un serveur virtuelle :

   * La création d'une machine virtuelle linux ``Ubuntu``, sont administration distance via le terminal
   * La partie réseau avec l'achat du nom de domaines la gestion des sous domaines.
   * La gestion d'un serveur Proxy avec ``Apache serveur`` pour la gestion des flux entrant sortant.
   * La création d'une base de données ``PostgreSQL`` avec la gestion des permissions et la gestion sur le réseau local.

#. La gestion de la sécurité du serveur et du site :
 
   * La gestion du pare-feu pour sécurisé tous les ports.
   * La création d'un micro service de sécurité ``Keycloak`` avec la connection de celui-ci à Postgresql.

#. La parti mise en service du site :
 
   * La parti Devops avec ``Jenkins`` qui permet la mise en production du site en correspondance avec ``Github``  

L'objectif de ce blog et de posté des articles portant sur l'informatique faisant référence a d'autre article 
ou des tutoriel.

Un espace commentaire sera dédier à chaque article permettant d'avoir un échange entre les utilisateurs connecter au site 
qui souhaitre intervenir sur l'article.

Cette documentation permet de rassemblé tout les informations concernant la gestion et la création du site.  
Dans cette objectif, celle servira d'aide-mémoire sur les choix et la compréhention.

.. Information sur serveur virtuelle Ubuntu 
.. toctree::
   :maxdepth: 2
   :caption: Serveur :

   Serveur/Installation du Ubuntu
   Serveur/Installation/PostgreSQL
   Serveur/Installation/Jenkins
   Serveur/Installation/Apache serveur
   Serveur/Installation/Git serveur

   Serveur/Configuration/EtcKeeper
   Serveur/Configuration/Connection SSH
   Serveur/Configuration/Attribution d'une adresse IP fixe
   Serveur/Configuration/Liste des paths 

.. Info sur base de données
.. toctree::
   :maxdepth: 2
   :caption: Base de données/Postgresql :
   
   Base de données/Postgresql/configuration
   Base de données/Model conceptuelle de données
   Base de données/Model logique de données
   Base de données/Les Script

.. Configuration Apache serveur
.. toctree::
   :maxdepth: 2
   :caption: Apache serveur :

   Apache serveur/Configuration

.. Sécurité du serveur
.. toctree::
   :maxdepth: 2
   :caption: Keycloak :

   Keycloak/Qu'est-ce que Keycloak
   Keycloak/Le protocole OIDC
   Keycloak/Cas d'utilisation
   Keycloak/Architecture
   Keycloak/Le mode Standalone
   Keycloak/Gestion de la base de données
   Keycloak/Déclartion et chargement du driver
   Keycloak/Configuration d'un Domaine

   .. Sécurité du serveur
.. toctree::
   :maxdepth: 2
   :caption: Sécurité :

   Sécurité/pare-feu
   Sécurité/SSL

.. Information sur la parti production
.. toctree::
   :maxdepth: 2
   :caption: Dévops :

   Dévops/Github
   Dévops/Jenkins/Description
   Dévops/Jenkins/Webhooks et Job
   Dévops/Articture Dev/prod

.. Information sur la parti back-end Micro service Spring
.. toctree::
   :maxdepth: 2
   :caption: back-end :

   back-end/L'architecture du back-end
   back-end/Le stokage des données utiliseur 

.. Information sur la parti Front-end avec angular
.. toctree::
   :maxdepth: 2
   :caption: Front-end :   

   Front-end/Le template utilisé
   Front-end/L'architecture du Front-end 


Indices and tables
==================

* :ref:`genindex`
* :ref:`modindex`
* :ref:`search`
