1. Gestion du pare-feu (Firewall)
##################################

Recherche de la configuration IP du serveur Ubuntu

.. code-block:: bash
    :linenos:

    ifconfig

Gestion des port d'écoute
--------------------------- 

Connaitre l'état du pare-feu

.. code-block:: bash
    :linenos:

    sudo ufw status

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

Dans le pare-feu Ubuntu, nous pouvons ajouter des règles pour autoriser l'adresse IP à tout 
le trafic ou pour certains ports réseau à l'aide de la commande ufw allow.

Ces régle on pour action de filtré 

.. code-block:: bash
    :linenos:

    sudo ufw allow from <Remote-IP> to <local-IP>

Exemple, cette règle de pare-feu autorisera tout le trafic provenant de l'adresse IP ``192.168.1.93``

.. code-block:: bash
    :linenos:

    sudo ufw allow from 192.168.1.93

Autoriser tout le trafic à partir de l'IP ``192.168.1.50``, 
mais uniquement sur l'IP du serveur local ``192.168.0.10``.

.. code-block:: bash
    :linenos:

    ufw allow from 192.168.1.50 to 192.168.0.10

Cette fois, nous autorisons tout le trafic réseau lié au protocole TCP à l'adresse 
IP ``192.168.1.10`` du pare-feu Ubuntu

.. code-block:: bash
    :linenos:

    ufw allow from 192.168.1.10 to any proto tcp


Ouverture du port tcp entrant ``8080`` de vers tout les adresses IP source.

.. code-block:: bash
    :linenos:

    sudo ufw allow from any to any port 8080 proto tcp

ou aussi

.. code-block:: bash
    :linenos:

    sudo ufw allow 8080/tcp

Autre exemple ouverture de tout les port tcp 80 venant de l'adresse IP ``192.168.1.10``

.. code-block:: bash
    :linenos:

    ufw allow from 192.168.1.10 to any proto tcp port 80

Cette règle ouvrira le port ``UDP 53`` sur ``IP 192.168.1.10``.

.. code-block:: bash
    :linenos:

    ufw allow from 192.168.1.10 to any proto udp port 53