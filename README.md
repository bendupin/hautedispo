Explication
==========

Cour de haute disponibilité

-Le dossier ubuntu-nginx contient les fichiers de configuration du container qui fait la répartition de charge.

-Le dossier docker-wordpress-nginx continet les fichiers de configuration des containers qui possède le wordpress.

-Le dossier mysql contient les fichiers de configuration du container qui à le rôle de serveur SQL.



Les commandes sont les suivantes :

docker build –t ubuntu-nginx ubuntu-nginx

docker run –d –p 80:80 –name front ubuntu-nginx

docker build –t docker-wordpress-nginx docker-wordpress-nginx

docker run –d –p 8080:80 –name wordpress1 docker-wordpress-nginx

docker run –d –p 8081:80 –name wordpress2 docker-wordpress-nginx

docker build –t mysql mysql

docker run –d –p 5432:3306 –name dba mysql
