1. Installation du serveur Ubuntu
#################################

Installation
=============

Introduction
--------------

Sur le Nas il faut stocker l’iso du server, il faut qu’il soit ajouté dans le 
système de virtualisation du serveur (Virtual Machine Manager) Nas dans la section 
image. Une fois cette image ajouter, dans la partie Machine virtuelle de Virtual 
Machine Manager vous pouvez créer votre serveur virtuel.

Une fois créer cliquer sur connection et suivez les étapes de création :

-	Choisissez la langue
-	La disposition du clavier et sa variante
-	Connection réseaux laisse l’adresse locale il faut une adresse type 192.168.1.xx, si vous n’avez pas ce genre d’adresse vous ne pourrez pas vous connectez en ssh.
-	Adresse du proxy ne rien mettre
-	Mirror adresse laisse comme sa
-	Guide Storage Configuration sélectionner la partie Custom Storage Layout pour créer une partition swap pour le serveur. 

Pour créer une partition swap , suivre l’exemple ci-dessous


1. Partition swap 
-----------------
Pour créer une partition swap , suivre l’exemple ci-dessous

.. image:: ../image/ubuntu_partition.png
    :width: 800
    :alt: image partition swap serveur Ubuntu n°1

Puis dans le menu de création de partition faire ci-dessous

.. image:: ../image/ubuntu_partition_2.png
    :width: 800
    :alt: image partition swap serveur Ubuntu n°2

2. Partition root
-----------------
Après avoir ajouté la partition swap, il nous faut créer la partition root pour le système de la manière suivant.

.. image:: ../image/ubuntu_partition_3.png
    :width: 800
    :alt: image partition swap Ubuntu serveur n°3

Si vous voulez laisser tout l’espace pour la partition principale avec le format du fichier ext4 
à la racine du future serveur, alors faire comme sur l’image.

.. image:: ../image/ubuntu_partition_4.png
    :width: 800
    :alt: image partition swap Ubuntu serveur n°4

Résultat finale avant validation

.. image:: ../image/ubuntu_partition_5.png
    :width: 800
    :alt: image partition swap Ubuntu serveur n°5

Résultat finale avant validation

.. image:: ../image/ubuntu_partition_6.png
    :width: 800
    :alt: image partition swap Ubuntu serveur n°6

.. image:: ../image/ubuntu_partition_7.png
    :width: 800
    :alt: image partition swap Ubuntu serveur n°7

Il ne reste plus qu'a :

- Configurer un profile utilisateur (avant ou aprés l'installation)
- Installer ``open ssh`` (pour pouvoir vous connectez pas la suite) puis importer vos clef ssh depuis GitHub, sélectionné allow password authentication over ssh 
- Installer si vous desirez des fonctionnalité snap ou les outils dont vous avez besoin.Si vous n'etez pas sur de ce que vous voulez,
  vous pourrez toujours les installer par la suite.

Et voila, lancer l’installation du serveur.