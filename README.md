# LaboratorioPromoxVECiberseguridadOD

# Descripcion del Proyecto:

Laboratorio Promox Virtual Environment 8.3.0, Curso en Ciberseguridad Ofensiva y Defensiva SRVESMAD01.
La finalidad de este proyecto, es la elaboración de un laboratorio de pruebas, en una maquina con entorno virtualizado con el software de libre distribucion Promox y la división de tareas a cada alumno.


1.  El sistema operativo a revisar será la ISO de software libre/distribucion de la pagina web de MAX Educamadrid, este sera el equipo cliente: https://www.educa2.madrid.org/web/max

<br>Descarga directa, version MAX-10.0: <br>

https://ftp.rediris.es/mirror/MaX-Linux/MaXdesktop/

2.  El sistema operativo a revisar sera el ISO de software libre/distribucion de Almax 9.7, que ara de equipo servidor: https://almalinux.org/es/

# Características Técnicas de la maquina Host:

Version del producto instalado, del fabricante Proxmox y la forma de conexión.

Version de Promax: Virtual Environment 8.3.0 <br>
Nombre Host: <b>SRVESMA01</b> <br>
DNS: 9.9.9.9 <br>
Web a conectar en un navegador: https://192.168.1.243:8006 <br>
IP: 192.168.1.243 <br>
Modelo: Intel Core I3

# Equipo tecnico y Roles:

Roles de usuario creados y el perfil que desempeña cada usuario en el proyecto.

Grupos: AdminUsers: Grupo con permisos de administración, creación, modificación y eliminación en el Datacenter.  <br>
Grupos: UsuariosNormales: 

--Roles -- Grupos: AdminUsers  <br><br>
Username: root <br>
Password: xxxxx<br>
Dominio: PAM
<br>
Name - <b>System Administrator:</b> Aron Gomez <br>
Username: agvillena@pve <br>
Password: xxxxx <br>
<br>
Name - <b>System Administrator:</b> Diana Del Valle <br>
Username: dvalle@pve <br>
Password: xxxxx <br>

--Roles -- Grupos: UsuariosNormales<br><br>
Name - <b>Redactor Técnico:</b> Borja Holgado <br>
Username: bholgado@pve <br>
Password: xxxxx <br>

-Roles Users de Test-

Name - <b>Tester de Software:</b> Roberto <br>
Username: roberto@pve <br>
Password: xxxxx <br>

Name - <b>Tester de Software:</b> <s> Matias </s> <br>
Username: <s> matias@pve </s> <br>
Password: xxxxx <br>

# 1.  Instalacion distribucion MAX por dvalle:

En la documentación, :memo: Notas Laboratorio Proxmox Virtual Environment esta la descripción de como instalar, paso a paso, la versión del sistema operativo MAX.

Configuracion, de 4 GB de Ram y un disco duro de 32 GB de almacenamiento. Se a creado un backup a día 31 de Octubre del 2026, Full update, y Instalacion completa. A su vez, una Snapshots a 03 de noviembre del 2026, en caso de necesitar restablecer puntos anteriores. Hostname: max10 , IP: 192.168.1.72

Mediante terminal deshabilitamos el usuario alumno, por que no guarda ningún cambio una vez se logue en el sistema y cierra sesión en la cuenta. Trabajaremos con el usuario Madrid y Profesor.
<br><br>

<b>
<br>
-Abrir un terminal-
<br>
Deshabilitado: "$ sudo passwd -dl alumno"
<br>
Habilitar: $ sudo passwd alumno</b>
<br>
<br>
Usuario: <s> Alumno </s>
<br>
Contraseña: <s> alumno </s>
<br><br>
Usuario (root): Madrid
<br>
Contraseña: cmadrid
<br><br>
Usuario: Profesor
<br>
Contraseña: profesor

# 2.  Instalacion distribucion ALMALINUX por dvalle:

Hostname: locaslhost.localdomain
<br>
IP: 192.168.1.147
<br>
<br>
Usuario (root): root
<br>
Contraseña: AlmaAdmin01
<br><br>
Usuario (ssh): user
<br>
Contraseña: Alm.Us.99
<br>

  1.Instalamos telnet en la maquina servidor. Al conectar tenemos permisoso con el usuario "user" , luego podremos ejecutar el root, por seguridad. Una vez conectado por ssh su-
<br><br>
<b>
sudo dnf update
<br>
sudo dnf install telnet
<br>
sudo dnf install telnet.server
<br>
systemctl status telnet.socket
<br>
systemctl enable telnet.socket
<br>
systemctl start telnet.socket
</b>
<br><br>
  2.Instalar Webmin - :memo:: InstalacionWebmin_11112026.docx

https://download.webmin.dev/

<b>dnf install /root/Descargas/webmin-2.671.202611110542-1.noarch.rpm</b>
<br><br>
Con este comando observamos todos los servicios instalados en la maquina y que estan corriendo.<br>
<b>systemctl list-units --type=service --all</b>

<img width="494" height="255" alt="image" src="https://github.com/user-attachments/assets/e0161cef-e1d6-4572-925a-2f9b82cb522a" />
<br>
3. Instalamos Wazuh

Nos logueamos con el usuario user y cambiamos al sudo su <br>
<b>ufw disable</b> <br>
<b>apt update && apt install git</b> <br><br>
Optamos por crear un usuario <b>sudo useradd bholgado</b> y la password <b>Clase12345678</b>
Para verificar que el usuario esta creado en el sistema escribiremos <b>greep "bholgado" /etc/passwd</b><br>
<img width="295" height="27" alt="image" src="https://github.com/user-attachments/assets/736206a1-4071-48e5-8d84-bb36ac923fb5" /><br>
Damos permisos de root al usuario <b>sudo usermod -aG wheel bholgado</b>








<br><br><br> *Chacklist

SO/Distribucion MAX IP: 192.168.1.72
- ¿Como conectar a la maquina por escritorio remoto?
- Revisar vulnerabilidades / con el usuario profesor . El de alumno, debe de estar desactivado. Y el de Madrid es el que tiene permisos de administrador.
- Instalar el agente de Wazu, en el usuario profesor.

SO/Distribucion ALMA IP: 192.168.1.147
- Conectar SSH.
-   Telnet-ok
-   Webmin-ok
-   FTP-?
- ¿Como conectar a la maquina por escritorio remoto?
- Comprobar funcionaminto de la version.
- Instalar Servidor Wazu.
