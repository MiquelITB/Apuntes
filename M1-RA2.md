## Configuració de xarxa
Xarxa NAT a VirtualBox: Herramientas > Administrador de reds > Redes NAT > Crear


## etc/group: nom_grup:contraseña_cifrada:GID:listado_miembros
  1. groupadd: Per crear un nou grup.
  2. groupdel: Per eliminar un grup.
  3. groupmod: Per modificar un grup existent (nom, GID).
  4. usermod: Per afegir o treure usuaris de grups.
  5. groups: Per veure a quins grups pertany un usuari.
  6. id: Per veure els GID i pertinença a grups d'un usuari.
## etc/shadow: usuario:contraseña_cifrada
  1. passwd: Para cambiar contraseña
  2. change: Cambiar politica de caducidad de contraseñas
  3. useradd: Crear usuarios (-m per crear una home i -aG per afegir usuari al grup, sense eliminar al que esta)
  4. usermod: Modificar usuarios (-s per definir la shell. [/bin/bash o /sbin/nologin])
  5. userdel: Eliminar usuarios
## /etc/security/pwquality.conf: Es defineix les polítiques de contraseñas del sistema

## /etc/passwd: usuari:contraseña:UID:GID:descripció:home:shell
  1. cut: per extreure seccions o camps (-d per definir el delimitador -f per indicar quin camp ej.[cut -d: -f3])
