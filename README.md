Instalacion automatizada de los sitios de web de la empresa
======

Este script automatiza la instalacion del servidor web Apache2 en un servidor remoto que utiliza Ubuntu y descarga y configura automaticamente los sitios web utilizados por **EQUIPAMIENTOS DE SEGURIDAD S.A.** de sus respectivos repositorios de *GitHub*.

Para lograrlo se usa la herramienta **Ansible** desde un equipo *controlador* que correra el script de automatizacion en un equipo *nodo*.

Introduccion a **Ansible**: 

[![Video de introduccion a Ansible](https://img.youtube.com/vi/icR-df2Olm8/0.jpg)](https://www.youtube.com/watch?v=icR-df2Olm8)

Requerimientos en el equipo controlador:

* Sistema de la familia Unix/Linux
* Ansible 2.5, que a su vez requiere:
  * Cliente SSH
  * Python 2 (2.6 o mas reciente) o Python 3 (3.5 o mas reciente)

Requerimientos en el equipo nodo:

* Ubuntu 18.04 o superior
* Tener configurado un servidor OpenSSH (Las imagenes de Ubuntu Server brindan una opcion para ofrecer esto por defecto)
* Python 2 (2.6 o mas reciente) o Python 3 (3.5 o mas reciente)

Para instalar o configurar SSH (ya sea cliente o servidor):
* https://help.ubuntu.com/lts/serverguide/openssh-server.html

Para instalar o configurar Ansible en el equipo controlador:
* https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#latest-releases-via-apt-ubuntu


Para clonar los repositorios desde github se precisa tener una llave SSH configurada en la cuenta https://github.com/mezka

Los scripts `write_domains_to_hosts_file.yml` y `delete_domain_from_hosts_file` son por si se quiere testear el script en una maquina virtual local.

======

Para instalar la ultima version de Ansible (solo se necesita instalar en el equipo controlador):

`sudo apt-get install ansible`

Se debe configurar el script para apuntar al servidor remoto en el archivo `inventory.ini`.

Para correr el script:

`ansible-playbook --ask-become-pass webserver.yml`
