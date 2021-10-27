1. Gestion du pare-feux
##########################

Liste de commande port d'écoute 

Connaitre le port d'écoute d'une applciation, dans l'exemple suivant on recherche 
soit ssh, apache serveur soit on vérifie que le port 8080 est ouvert.

.. code-block:: bash
    :linenos:

    sudo netstat -tulnp | grep ssh
    sudo netstat -tulnp | grep apache2
    sudo netstat -tulnp | grep 8080


La list des ports d'écoute du serveur

.. code-block:: bash
    :linenos:

    ss -ltn

