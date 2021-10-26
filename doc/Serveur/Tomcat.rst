6. Tomcat
#################

Installation de tomcat sur Ubuntu server
----------------------------------------



Configuration du module jk 
---------------------------

Pour réceptionné les requêtes venant de l'extérieur vers le serveur tomact 
nous devons paramétre le module jk qui feras le forwarding vers le serveur
tomcat. 

Pour cela nous devons configurer tomact pour qu'il reception les requêtes 
que serveur Proxy apache lui retourne.

Voici le repertoir tomcat ou ce situe les fichier de configuration

.. code-block:: bash
    :linenos:

    /etc/tomcat9

.. image:: ../image/ubuntu_tomact_fichier.png
    :width: 800
    :alt: image repertoire tomcat 9