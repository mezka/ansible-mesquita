Instalacion automatizada de los sitios de web de la empresa
======

Este script automatiza la instalacion del servidor web Apache2 en un servidor remoto que utiliza Ubuntu y descarga y configura automaticamente los sitios web utilizados por **EQUIPAMIENTOS DE SEGURIDAD S.A.** de sus respectivos repositorios de *GitHub*.

Para lograrlo se usa la herramienta **Ansible** desde un equipo *controlador* que correra el script de automatizacion en un equipo *nodo*

Introduccion a **Ansible**: 

[![Video de introduccion a Ansible](https://img.youtube.com/vi/icR-df2Olm8/0.jpg)](https://www.youtube.com/watch?v=icR-df2Olm8)

Requerimientos en el equipo controlador:

* Sistema de la familia Unix/Linux
* Ansible 2.5, que a su vez requiere:
  * Cliente SSH
  * Python 2 (2.6 o mas reciente) o Python 3 (3.5 o mas reciente)

Requerimientos en el equipo nodo:

* Ubuntu 16.04 o superior
* Tener configurado un servidor OpenSSH (Las imagenes de Ubuntu Server brindan una opcion para ofrecer esto por defecto)
* Python 2 (2.6 o mas reciente) o Python 3 (3.5 o mas reciente)

Para instalar o configurar SSH (ya sea cliente o servidor):
* https://help.ubuntu.com/lts/serverguide/openssh-server.html

Para instalar o configurar Ansible en el equipo controlador:
* https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#latest-releases-via-apt-ubuntu

Configuracion del script
======

Usuario y contrasenia de GitHub en `conf/git_username_password.yml`
Dominio de las paginas web y repositorios en `conf/websites.yml`

Ejecutando el script
======

`ansible-playbook --ask-become-pass --become-method sudo --inventory-file=inventory.ini webserver.yml`
