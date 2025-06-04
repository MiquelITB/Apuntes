# Sistema de Fitxers a Ubuntu

El sistema de fitxers d'Ubuntu (i Linux en general) s'estructura a partir d'un directori **arrel** (`/`), que és la base de tot. A diferència de Windows, no hi ha lletres de unitat; tot s'organitza de forma jeràrquica sota aquest punt únic.

### Directoris Essencials i la seva Funció:

![image](https://github.com/user-attachments/assets/8a54ea5b-c284-48c2-8314-9dd66eacb09e)

* **`/` (Arrel)**
    * Directori principal. Tota la resta es troba sota ell.

* **`/home`**
    * Conté els directoris personals de cada usuari (Ex: `/home/usuari`).

* **`/root`**
    * Directori personal de l'usuari **administrador** (`root`). Separat de `/home` per seguretat.

* **`/etc` (Etcètera)**
    * Guarda els **fitxers de configuració** del sistema i la majoria de programes.
    * **`/fstab`** --> Fitxer per fer permanent els punts de muntatge.

* **`/bin` i `/sbin` (Binaris)**
    * **`/bin`** --> Conté ordres executables essencials per a tots els usuaris (`ls`, `cp`).
    * **`/sbin`** --> Conté binaris essencials per a l'**administració del sistema** (executables per `root`).

* **`/usr` (Unix System Resources)**
    * Conté la major part de programes d'usuari, biblioteques, documentació i codi font.

* **`/var` (Variable data)**
    * Fitxers de dades que canvien sovint. Inclou **logs del sistema** (`/var/log`), dades de servidors web, etc.

* **`/tmp` (Temporary)**
    * Per a **fitxers temporals**. El contingut es sol esborrar en reiniciar el sistema.

* **`/dev` (Devices)**
    * Fitxers especials que representen els **dispositius de maquinari** (discs, USB, etc.).

* **`/media` i `/mnt` (Muntatges)**
    * **`/media`** --> Punt de muntatge per a dispositius extraïbles muntats automàticament (USB, CD/DVD).
    * **`/mnt`** --> Punt de muntatge genèric per a sistemes de fitxers muntats manualment.

---

### Conceptes Clau:

* **Punt de Muntatge**
    * Acció de "connectar" un sistema de fitxers (partició, USB) a un directori existent dins la jerarquia del sistema arrel per poder-hi accedir.

* **Enllaços (Links)**
    * **Enllaç Simbòlic (Soft Link)**
        * Un fitxer que apunta a un altre fitxer o directori. Similar a una drecera.
        * Si l'original s'esborra, l'enllaç simbòlic queda "trencat".
        * Ex: `ln -s /ruta/fitxer_original /ruta/enllac`
    * **Enllaç Dur (Hard Link)**
        * Una entrada addicional que apunta al mateix "inode" (les dades reals) d'un fitxer.
        * El fitxer no s'esborra completament fins que tots els enllaços durs que apunten a ell són eliminats.
        * Només funciona dins del mateix sistema de fitxers.
        * Ex: `ln /ruta/fitxer_original /ruta/enllac`
     
---
# Sistema de Fitxers a Windows

A Windows, tot s'organitza al voltant de **unitats lògiques** (Ex: $C:$, $D:$). Cada unitat és un punt d'accés independent a un dispositiu o partició.

### Directoris Clau (a la unitat $C:$)

* **`C:\` (Unitat Arrel)**: Punt de partida de la unitat $C:$.
* **`C:\Windows`**: Fitxers essencials del sistema operatiu Windows, nucli i controladors.
* **`C:\Program Files`**: Instal·lació per defecte de programes de 64 bits.
* **`C:\Program Files (x86)`**: Instal·lació per defecte de programes de 32 bits en sistemes de 64 bits.
* **`C:\Users` (o `C:\Usuarios`)**: Conté els perfils de cada usuari.
    * **Dins de `C:\Users\NomUsuari`**:
        * `Desktop` (Escriptori)
        * `Documents` (Documents)
        * `Downloads` (Descàrregues)
        * `Pictures`, `Videos`, `Music`
        * `AppData` (Carpeta oculta amb configuracions i dades d'aplicacions).
* **`C:\ProgramData`**: Dades d'aplicacions no lligades a un usuari específic (sovint oculta).
* **`C:\Windows\System32`**: Fitxers DLL, executables del sistema i altres fitxers crítics de Windows.
* **`C:\Windows\Temp`**: Fitxers temporals del sistema i aplicacions.

---

### Conceptes Ràpids:

* **Unitats Lògiques**: Assignació de lletres ($C:$, $D:$) a particions o dispositius.
* **Fitxers DLL**: Biblioteques de codi compartit per diversos programes.
* **Dreceres (Shortcuts)**: Fitxers `.lnk` que apunten a altres fitxers o programes (similar a enllaços simbòlics).
* **Registre de Windows**: Base de dades jeràrquica amb configuracions del SO, maquinari i aplicacions.


---
## Formateig i Nomenclatura de Dispositius

### Nomenclatura

#### Linux
- **Discos Durs**: S'identifiquen com a `/dev/sda`, `/dev/sdb` (per a discos SATA/USB), o `/dev/nvme0n1` (per a discos NVMe).
- **Particions**: Són subdivisions dels discos, per exemple: `/dev/sda1`, `/dev/sda2`, `/dev/nvme0n1p1`. El número al final indica la partició dins del disc.

#### Windows
- **Lletres d'Unitat**: Les particions o dispositius s'identifiquen amb lletres, com ara `C:`, `D:`, `E:`.

---

### Tipus de Particions

#### Linux
- **Primària**: Pots tenir un màxim de 4 particions primàries per disc.
- **Estesa**: És una partició especial que actua com a "contenidor" per a les particions lògiques. Només pots tenir-ne una per disc.
- **Lògica**: Són les particions que es creen dins d'una partició estesa. Això et permet tenir més de 4 particions en un disc.
- **Swap**: S'utilitza com a "memòria virtual" per al sistema. Si la RAM s'omple, el sistema fa servir aquesta partició per guardar dades temporalment.

#### Windows
- **Primària**: És la partició principal on normalment s'instal·la el sistema operatiu.
- **Lògica/Unitat Lògica**: Similar a Linux, es creen dins d'una partició estesa en discos amb format MBR.
- **Volum Simple**: Són les particions equivalents a les primàries quan el disc està formatat amb GPT (un sistema de particionat més modern).
- **Recuperació**: Conté eines i arxius per restaurar el sistema operatiu a un estat anterior o solucionar problemes.
- **EFI System Partition (ESP)**: És una partició petita i essencial en sistemes que usen UEFI (el successor del BIOS). Conté l'arrancador del sistema operatiu.

---

### Formateig de Dispositius

**Formatejar un dispositiu significa preparar-lo perquè hi puguis guardar dades. Aquest procés esborra TOT el que hi hagi al disc o partició.**

#### Linux

A Linux, utilitzem l'ordre `mkfs` (de "make filesystem", fer sistema de fitxers) des de la terminal per formatejar. Recorda substituir `/dev/sda1`, `/dev/sdb1`, etc., per la partició correcta que vols formatejar. **¡Vés amb molta cura, ja que és una acció destructiva!**

- Per formatejar una partició amb el sistema de fitxers **ext4** (el més comú a Linux):
  `sudo mkfs.ext4 /dev/sda1`

- Per formatejar una partició amb **FAT32** (útil per a USBs i compatibilitat amb Windows/macOS):
  `sudo mkfs.fat -F 32 /dev/sdb1`

- Per formatejar una partició amb **NTFS** (el sistema de fitxers principal de Windows):
  `sudo mkfs.ntfs /dev/sdc1`

#### Windows

A Windows, tens dues maneres principals de formatejar dispositius, totes dues amb una interfície gràfica:

- **Des de l'Explorador de Fitxers**:
    1. Obre l'**Explorador de Fitxers** (la icona de la carpeta groga).
    2. Ves a "Aquest PC" (o "El meu PC").
    3. Clica amb el **botó dret** sobre la lletra de la unitat que vols formatejar (per exemple, `D:`).
    4. Selecciona l'opció **"Formateja..."** i segueix les instruccions.

- **Des de l'Administració de Discos**:
    1. Prem les tecles `Windows + X` al mateix temps i selecciona **"Administració de discos"** del menú que apareix.
    2. A la finestra d'Administració de Discos, localitza la partició o el disc que vols formatejar.
    3. Clica amb el **botó dret** sobre la partició.
    4. Selecciona l'opció **"Formateja..."** i configura les opcions que necessitis.

## Sistemes de Fitxers

### Què són?
Un sistema de fitxers (filesystem) és la manera com el sistema operatiu organitza i gestiona els fitxers en un disc o partició. Defineix com s'emmagatzemen, es recuperen i s'accedeixen a les dades.

---

# Sistemes de Fitxers Comuns

### Linux

-   **Ext4 (Extended File System 4)**
    -   **Ús principal**: Estàndard actual per a la majoria de distribucions Linux.
    -   **Característiques**: Alt rendiment, fiabilitat, suport per a volums grans i fitxers grans, i retrocompatibilitat amb ext2/ext3.
    -   **Adequat per**: Sistemes operatius, emmagatzematge general.

-   **XFS**
    -   **Ús principal**: Sistemes amb grans volums de dades i alta concurrència (servidors, bases de dades).
    -   **Característiques**: Dissenyat per a l'escalabilitat, molt bo amb fitxers grans, bona recuperació.
    -   **Adequat per**: Servidors, NAS, grans volums de dades.

-   **Btrfs (B-tree File System)**
    -   **Ús principal**: Sistema de fitxers modern amb característiques avançades.
    -   **Característiques**: "Copy-on-write" (CoW), instantànies (snapshots), checksums, gestió de volums integrada, RAID de programari.
    -   **Adequat per**: Sistemes amb necessitat d'instantànies, integritat de dades, gestió avançada.

-   **FAT32 (File Allocation Table 32)**
    -   **Ús principal**: Dispositius USB, targetes de memòria.
    -   **Característiques**: Gran compatibilitat amb diversos sistemes operatius (Windows, macOS, Linux).
    -   **Limitacions**: No admet fitxers individuals de més de 4GB.

-   **NTFS (New Technology File System)**
    -   **Ús principal**: El sistema de fitxers natiu de Windows.
    -   **Característiques**: Suport per a permisos de seguretat, xifratge, compressió, diari.
    -   **Adequat per**: Particions per a Windows, discs externs compartits amb Windows.

---

### Windows

-   **NTFS (New Technology File System)**
    -   **Ús principal**: **Estàndard principal de Windows** per a unitats de sistema, discos durs interns i externs.
    -   **Característiques**: Seguretat (permisos d'usuari), suport per a grans volums i fitxers, compressió, xifratge de fitxers, diari (per a recuperació en cas de fallada).
    -   **Adequat per**: Qualsevol partició de Windows, discs durs de gran capacitat.

-   **FAT32 (File Allocation Table 32)**
    -   **Ús principal**: Dispositius d'emmagatzematge extraïbles (USB, targetes SD).
    -   **Característiques**: **Molta compatibilitat** amb altres sistemes operatius (Linux, macOS, dispositius antics).
    -   **Limitacions**: No pot emmagatzemar fitxers individuals de més de 4GB. Límits de mida de partició.

-   **exFAT (Extended File Allocation Table)**
    -   **Ús principal**: Unitats flash USB, targetes SD de gran capacitat. Dissenyat per substituir FAT32 en aquests escenaris.
    -   **Característiques**: **Sense límit de 4GB per fitxer**, bona compatibilitat amb Windows, macOS i algunes versions de Linux.
    -   **Adequat per**: Discs externs i USBs que necessitin moure fitxers grans entre Windows i altres SOs.

---

### Conceptes Clau

-   **Diari (Journaling)**: Un registre de canvis pendents. Ajuda a recuperar-se ràpidament d'errors sense haver de comprovar tot el disc. (Present en Ext4, XFS, Btrfs, NTFS).
-   **Inodes (Linux)**: Estructures de dades que emmagatzemen informació sobre un fitxer o directori (propietari, permisos, ubicació de les dades).
-   **Clústers (Windows)**: La unitat mínima d'emmagatzematge en un sistema de fitxers. Com més petit és el clúster, més eficient és l'emmagatzematge, però pot ser més lent.

---

## Permisos de Fitxers i Directoris

### Què són?
Els permisos controlen qui pot llegir, escriure o executar fitxers i directoris. Són fonamentals per a la seguretat del sistema.

---

### Tipus de Permisos

Cada permís té un significat diferent per a fitxers i directoris:

| Permís | Simbòlic | Valor Octal | Sobre un **Fitxer** | Sobre un **Directori** |
| :----- | :-------- | :---------- | :------------------------------------------------ | :------------------------------------------------------- |
| Lectura | `r`       | `4`         | Permet veure el contingut del fitxer.             | Permet llistar el contingut del directori (`ls`).        |
| Escriptura | `w`       | `2`         | Permet modificar o esborrar el fitxer.          | Permet crear, esborrar o renombrar fitxers dins del directori. |
| Execució | `x`       | `1`         | Permet executar el fitxer (si és un programa/script). | Permet accedir al directori (`cd`) i als seus fitxers (si es tenen els permisos). |

---

### Propietaris dels Permisos

Els permisos s'apliquen a tres categories d'usuaris:

1.  **Usuari propietari (`u`)**: El creador o propietari del fitxer/directori.
2.  **Grup propietari (`g`)**: El grup al qual pertany el fitxer/directori.
3.  **Altres (`o`)**: Totes les altres persones al sistema.

---

### Visualitzar Permisos (`ls -l`)

La comanda `ls -l` mostra els permisos en un format de 10 caràcters.
El primer caràcter indica el **tipus de fitxer**:
* `-`: Fitxer regular
* `d`: Directori
* `l`: Enllaç simbòlic
* ... (altres menys comuns)

Els 9 caràcters següents es divideixen en tres grups de tres (`rwx`):
* **Primer grup (posicions 2-4)**: Permisos per a l'**usuari propietari**.
* **Segon grup (posicions 5-7)**: Permisos per al **grup propietari**.
* **Tercer grup (posicions 8-10)**: Permisos per a **altres** usuaris.

Un guionet (`-`) indica l'absència d'un permís.

**Exemple d'interpretació:**

Per a `-rw-r--r--`:
* `-`: És un fitxer regular.
* `rw-`: L'**usuari propietari** pot llegir (`r`) i escriure (`w`), però no executar (`-`).
* `r--`: El **grup propietari** només pot llegir (`r`), però no escriure ni executar.
* `r--`: **Altres** usuaris només poden llegir (`r`), però no escriure ni executar.

---

### Modificar Permisos (`chmod`)

La comanda `chmod` permet canviar els permisos, utilitzant mode simbòlic o octal.

#### Mode Simbòlic (més llegible)

S'usen `u`, `g`, `o`, `a` (all) i `+`, `-`, `=` per afegir, treure o assignar permisos.

* `chmod u+x fitxer.sh`: Afegeix permís d'execució a l'usuari propietari.
* `chmod go-w fitxer.txt`: Treu permís d'escriptura al grup i a altres.
* `chmod o=r fitxer.txt`: Assigna només permís de lectura a altres.
* `chmod a+rwx meu_directori`: Dóna tots els permisos a tothom (usuari, grup, altres).

#### Mode Octal (més ràpid)

S'assigna un número de 3 o 4 xifres (base 8), on cada xifra representa la suma dels valors dels permisos (`r=4, w=2, x=1`).

* **Càlcul**:
    * Usuari: Suma els valors de `rwx` (Ex: `rwx` = 4+2+1=7; `rw-` = 4+2+0=6)
    * Grup: Idem
    * Altres: Idem

* **Exemples**:
    * `chmod 755 script.sh`: `rwx` (usuari), `r-x` (grup), `r-x` (altres). (Executar per usuari, llegir/executar per grup/altres).
    * `chmod 644 document.txt`: `rw-` (usuari), `r--` (grup), `r--` (altres). (Llegir/escriure per usuari, només llegir per grup/altres).
    * `chmod 700 privat/`: `rwx` (usuari), `---` (grup), `---` (altres). (Només accés per a l'usuari propietari).

---

### Permisos Especials (Avançat)

Aquests bits s'afegeixen com una quarta xifra a l'esquerra en mode octal (per exemple, `1777` per al sticky bit).

* **SUID (Set User ID - `4000`)**:
    * Sobre un executable: El programa s'executa amb els permisos del propietari del fitxer, no de l'usuari que l'executa.
    * Indicador en `ls -l`: `s` al lloc de la `x` de l'usuari (`rws`).
    * **Precaució**: Pot ser un risc de seguretat si no s'utilitza amb cura.

* **SGID (Set Group ID - `2000`)**:
    * Sobre un executable: El programa s'executa amb els permisos del grup propietari del fitxer.
    * Sobre un directori: Els nous fitxers creats dins el directori hereten el grup propietari del directori, no el grup primari de l'usuari que els crea.
    * Indicador en `ls -l`: `s` al lloc de la `x` del grup (`rwxrwSrwx`).

* **Sticky Bit (`1000`)**:
    * Sobre un directori: Els usuaris només poden esborrar o renombrar els fitxers que ells mateixos han creat dins d'aquest directori, fins i tot si tenen permisos d'escriptura.
    * Indicador en `ls -l`: `t` al lloc de la `x` dels altres (`rwxrwxrwt`).
    * **Ús comú**: Directori `/tmp`.

---

## Manipulació de Particions en Linux

### Què és una partició?
Una partició és una divisió lògica d'un disc dur o SSD. Permet organitzar l'espai d'emmagatzematge i, per exemple, tenir diferents sistemes de fitxers o sistemes operatius en el mateix disc.

---

### Eines per Manipular Particions

A Linux, les eines de línia de comandes més comunes per gestionar particions són:

* **`fdisk`**: Per a discs amb taules de particions **MBR** (Master Boot Record). És més antic, però encara útil.
* **`gdisk`**: Per a discs amb taules de particions **GPT** (GUID Partition Table). És el successor de `fdisk` per a discs moderns i de gran capacitat.
* **`parted`**: Eina més potent i moderna que pot gestionar tant MBR com GPT. Permet fer canvis sense reiniciar, però és més arriscada si no se sap què es fa.

**Precaució**: Manipular particions pot **esborrar dades irrecuperablement**. Assegura't de fer una còpia de seguretat abans de qualsevol operació important.

---

### Identificació de Discs i Particions

Abans de res, has d'identificar els teus discs i les seves particions:

* **Llistar discs i particions:**
    ```bash
    sudo fdisk -l          # Per a MBR i GPT (mostra molta informació)
    sudo lsblk -f          # Més visual, mostra dispositius, particions, tipus de FS i punts de muntatge
    ```
    * Exemples de discs: `/dev/sda`, `/dev/sdb`, `/dev/nvme0n1`
    * Exemples de particions: `/dev/sda1`, `/dev/sdb2`, `/dev/nvme0n1p1`

---

### Operacions Bàsiques amb Particions

Utilitzarem `gdisk` o `fdisk` per simplicitat en l'exemple de creació/eliminació, però recorda usar l'eina adequada per al teu tipus de taula de particions.

#### 1. Accedir a l'Eina

* **Per a disc MBR (amb `fdisk`):**
    ```bash
    sudo fdisk /dev/sdX  # Substitueix X per la lletra del teu disc (a, b, c, etc.)
    ```
* **Per a disc GPT (amb `gdisk`):**
    ```bash
    sudo gdisk /dev/sdX  # Substitueix X per la lletra del teu disc
    ```
    Un cop dins, prem `m` (o `?`) per veure les opcions del menú.

#### 2. Crear una Partició

* Dins de `fdisk` o `gdisk`:
    1.  Prem `n` (new partition).
    2.  Et demanarà el número de partició (normalment el següent disponible).
    3.  Et demanarà el primer sector (prem Enter per defecte per a l'inici).
    4.  Et demanarà l'últim sector o la mida (+50G, +1T, etc.).
    5.  Si fas servir `gdisk`, et demanarà el codi HEX del tipus de partició (ex: `8300` per a Linux filesystem, `8200` per a swap, `0700` per a Microsoft basic data). Consulta `L` per veure els codis.
    6.  Prem `w` (write) per guardar els canvis al disc. **Això fa els canvis permanents!**

#### 3. Eliminar una Partició

* Dins de `fdisk` o `gdisk`:
    1.  Prem `p` (print) per veure la llista de particions i els seus números.
    2.  Prem `d` (delete partition).
    3.  Et demanarà el número de partició a esborrar.
    4.  Prem `w` (write) per guardar els canvis.

#### 4. Formatejar una Partició (Crear un Sistema de Fitxers)

Després de crear una partició, cal donar-li un sistema de fitxers.
```bash
sudo mkfs.ext4 /dev/sdXN    # Per crear un sistema de fitxers ext4
sudo mkfs.fat -F 32 /dev/sdXN # Per crear FAT32
sudo mkfs.ntfs /dev/sdXN    # Per crear NTFS (necessites instal·lar ntfs-3g)
# Substitueix X per la lletra del disc i N pel número de partició.
