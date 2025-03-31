# DHCP
El servei DHCP permet la configuració d’adreces IP, màscares, passarel·les per defecte i moltes altres opcions de configuració de manera totalment dinàmica. DHCP és l’acrònim de dynamic host configuration protocol, en català, protocol de configuració dinàmica d’equips.
Un servidor DHCP anirà assignant als equips clients els valors que els corresponguin. Aquesta assignació es fa per un període de temps finit, passat el qual caldrà renovar-se.

### Avantatges del DHCP
- Centralitza l'administració.
- Evita errors i conflictes IP.
- Estalvia temps.
- Simplifica l’administració.

### Client DHCP
Un equip client DHCP és un equip que sol·licita la IP i altres paràmetres de configuració de xarxa a un servidor DHCP en lloc de tenir-los definits localment en l’equip.
Aquestes adreces IP dinàmiques són fixes (sempre les mateixes) o dinàmiques d’interval (pot ser qualsevol IP del conjunt d’adreces IP que té disponibles per concedir el servidor DHCP).
El client DHCP ha de tenir en funcionament un dimoni (daemon) encarregat de la gestió de les tasques DHCP per part del client. El programa client realitza la part de negociació encarregada al client (DHCP discovery, request) i també porta un registre de les concessions (leases) rebudes.

## Configuració de un cleint DHCP

### A Linux/Debian

1. Amb la comanda *ip link show* verificam quines interfícies podem fer servir.

2. Un cop seleccionada, obrim i modificam el fitxer corresponent: *sudo nano /etc/network/interfaces*

   En aquest fitxer, afegim o modificam al la següent informació:
   
   *auto enp0sx*

    *iface enp0sx inet dhcp*

3. Guardam l'arxiu i reiniciam la red: *sudo systemctl restart networking*

### A Windows

1. Obrim la configuracio de red cercant *Adaptador de red* y li donam a *Propiedades al adaptador que volem configurar*

2. Dintre el protocol IPv4 marcam *Optencion de ip automáticamente* i *Obtener la dirección del servidor DNS automáticamente*

3. Un cop configurat, en el CMD verificam que s'han establerts els canvis amb la comanda *ipconfig /all*

### Servidor DHCP
Usualment, en una xarxa corporativa el servidor DHCP utilitza una IP estàtica definida per l’administrador. Això li permet estar sempre disponible per als clients amb la mateixa IP i no el fa dependre d’un altre servidor extern.




![image](https://github.com/user-attachments/assets/14b8e57e-42ed-4942-980b-4f3609ebf00e)





