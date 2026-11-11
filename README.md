# LaboratorioPromoxVECiberseguridadOD

# Descripcion del Proyecto:

Laboratorio Promox Virtual Environment 8.3.0, Curso en Ciberseguridad Ofensiva y Defensiva SRVESMAD01.
La finalidad de este proyecto, es la elaboración de un laboratorio de pruebas, en una maquina con entorno virtualizado con el software de libre distribucion Promox y la división de tareas a cada alumno.


1.  El sistema operativo a revisar será la ISO de software libre de la pagina web de MAX Educamadrid, este sera el equipo cliente: https://www.educa2.madrid.org/web/max

<br>Descarga directa, version MAX-10.0: <br>

https://ftp.rediris.es/mirror/MaX-Linux/MaXdesktop/

2.  El sistema operativo a revisar sera el ISO de software libre de Almax 9.7:

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

# 1.  Instalacion sistema SO MAX por dvalle

En la documentación, Notas Laboratorio Proxmox Virtual Environment esta la descripción de como instalar, paso a paso, la versión del sistema operativo MAX.

Configuracion, de 4 GB de Ram y un disco duro de 32 GB de almacenamiento. Se a creado un backup a día 31 de Octubre del 2026, Full update, y Instalacion completa. A su vez, una Snapshots a 03 de noviembre del 2026, en caso de necesitar restablecer puntos anteriores. Hostname: max10 , IP: 192.168.1.72

Mediante terminal deshabilitamos el usuario alumno, por que no guarda ningún cambio una vez se logue en el sistema y cierra sesión en la cuenta. Trabajaremos con el usuario Madrid y Profesor.
<br><br>
<b>(Deshabilitado, "$ sudo passwd -dl alumno")<b/>
<br>
Habilitar: $ sudo passwd alumno

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

# 2.  Instalacion sistema SO ALMALINUX por dvalle

Hostname: 
IP: 192.168.1.147
<br>
<b>sudo dnf update</b>
<br><br>
Usuario (root): root
<br>
Contraseña: AlmaAdmin01
<br><br>
Usuario: user
<br>
Contraseña: Alm.Us.99

Instalamos telnet en la maquina











<br><br><br>

SO MAX
- ¿Como conectar a la maquina por escritorio remoto?
- Revisar vulnerabilidades / con el usuario profesor . El de alumno, debe de estar desactivado. Y el de Madrid es el que tiene permisos de administrador.
- Instalar el agente de Wazu, en el usuario profesor.

SO Red Hat
- Conectar SSH.
- ¿Como conectar a la maquina por escritorio remoto?
- Comprobar funcionaminto de la version.
- Instalar Servidor Wazu.
