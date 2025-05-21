
# 📝 Apuntes de Configuración NFS (Ubuntu servidor y Windows cliente)

## 📂 Archivos de configuración utilizados

- `/etc/exports`: Archivo principal en el servidor NFS donde se definen las carpetas compartidas y los permisos de acceso.

## 🧾 Comandos utilizados en Ubuntu (Servidor NFS)

```bash
# Actualizar repositorios e instalar el servidor NFS
sudo apt update
sudo apt install nfs-kernel-server
```
> Instala el servicio NFS necesario para compartir carpetas en red.

```bash
# Crear directorios que se compartirán
sudo mkdir -p /ubuntunfs/nfs1Miquel
sudo mkdir -p /ubuntunfs/nfs2Miquel
sudo mkdir -p /ubuntunfs/nfs3anonim
```
> Crea las carpetas locales que serán exportadas por NFS.

```bash
# Asignar propietarios y permisos
sudo chown -R usuario:grupo /ubuntunfs/nfs1Miquel
sudo chmod 755 /ubuntunfs/nfs1Miquel

sudo chown -R usuario:grupo /ubuntunfs/nfs2Miquel
sudo chmod 777 /ubuntunfs/nfs2Miquel

sudo chown -R nobody:nogroup /ubuntunfs/nfs3anonim
sudo chmod 777 /ubuntunfs/nfs3anonim
```
> Establece permisos adecuados para controlar el acceso.

```bash
# Editar el archivo de exportaciones
sudo nano /etc/exports
```
> Permite definir qué carpetas se comparten, a qué IPs y con qué permisos.

Ejemplo de contenido:
```
/ubuntunfs/nfs1Miquel *(ro,sync)
/ubuntunfs/nfs2Miquel 192.168.1.100(rw,sync)
/ubuntunfs/nfs3anonim *(rw,sync,no_subtree_check,anonuid=65534,anongid=65534)
```

```bash
# Aplicar y reiniciar la configuración
sudo exportfs -ra
sudo systemctl restart nfs-kernel-server
```
> Recarga las carpetas compartidas y reinicia el servicio NFS.

---

## 🧾 Comandos utilizados en Windows Server (Cliente NFS)

```powershell
# Instalar el cliente NFS
Install-WindowsFeature NFS-Client
```
> Instala el componente que permite montar carpetas NFS en Windows.

```powershell
# Ver exportaciones NFS disponibles desde el servidor Ubuntu
showmount -e 192.168.1.50
```
> Muestra las carpetas compartidas por NFS desde la IP indicada.

```cmd
# Montar manualmente las carpetas NFS
mount -o anon \\192.168.1.50\ubuntunfs1Miquel Z:
mount -o anon \\192.168.1.50\ubuntunfs2Miquel Y:
mount -o anon \\192.168.1.50\ubuntunfs3anonim X:
```
> Conecta las carpetas NFS a letras de unidad en Windows usando acceso anónimo.

```cmd
# Verificar contenido y permisos
Z:
dir
echo prueba > test.txt
```
> Accede a la carpeta montada y prueba los permisos de escritura.
```

# 📌 Notas
- Reemplazar `usuario:grupo` por el propietario real en Ubuntu.
- Reemplazar `192.168.1.50` con la IP de tu servidor Ubuntu.
