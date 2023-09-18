# Taller de Linux
La documentación de una máquina virtual para aprender los conceptos básicos de administración de Linux, todo esto con el fin de servir como una introducción a la administración de servidores en la nube.

# Usuarios iniciales
1. root
1. sistemas
1. user

# Usuarios que debes crear
1. soporte (añadir al grupo sudo)
1. superadmin (añadir al archivo sudoers)
1. cliente (sin privilegios)

# Usuarios malignos
1. sistemas (sudoers) 
	1. Respaldar BD, contenido [ok]
	1. Prueba el respaldo [ok]
	1. Crea al grupo system, admins [ok]
	1. Crea al usuario process (lo añade a grupo admins) [ok]
	1. Añade grupo admins a sudoers [ok]
	1. Comandos administrativos que no son relevantes [ok]
	1. Mueve el respaldo a /opt/respaldo [ok]
1. process %admin (este hace el ataque y rompe cosas)
	1. Crea al usuario reverse (sudo) y system (sudoers) [ok]
	1. Borrar Base de datos y contenido del sitio web [ok]
	1. Desinstalar mysql  [ok]
	1. Crea una web (casi identica) [ok]
		1. WebShell Oculta [ok]
		1. Con un archivo Backup que es un script malicioso (Alterar PATH) [ok]
1. reverse /no/login (sudo)
	1. Crea backdoor como servicio php UDP [ok]
	1. Creación de usuario ssh (servicio) [ok]
	1. Cronjob [ok]
		1. Ejecución de script [ok]
	1. Borra algunos comandos de history [ok]
1. system (cronjob) (sudoers)
	1. Pasa script maligno a respaldo [ok]
	1. Al respaldo de BD y contenido lo cifra [ok]
	1. Crea WebShell php UDP [ok]
	1. Inmutabilidad a los archivos malignos [ok]
	1. Borra algunos comandos [ok]
	1. Hacer configuraciones de complicar las cosas
		1. Interfaz de red [ok]
		1. Apagar servicio SSH [ok]
		1. Romper repositorios de software [ok]
		1. Configuración de teclado [ok]
		1. PATH [ok]
1. ssh (system)

# Retos sobre la máquina

## Parte 1 - Configuraciones 
### Usuarios: root y soporte
1. Configuración de PATH [ok]
1. Crear los siguientes usuarios [ok]
	1. soporte (añadir al grupo sudo)
	1. superadmin (añadir al archivo sudoers)
	1. cliente (sin privilegios)
1. Reparar los repositorios de software [ok]

## Parte 2 - Otras formas de instalar paquetes
### Usuarios: soporte
1. DPKG - Instalación de: [ok]
	1. Apache
	1. Instala PHP

## Parte 3 - Restaurando el orden
### Usuarios: superadmin
1. Restaurando el sitio web PHP
	1. Descomprimir el archivo con contraseña
1. Invistigar qué ha hecho el usuario intruso (history)
1. Eliminar todos los servicios malignos
	1. Reverse Shell UDP
	1. Reverse Shell TCP
	1. Crontab root
1. Eliminar a los usuarios malignos
	1. process %admin
	1. reverse /no/login
	1. sistemas (al que verán el history)

# Parte 4 - Blindando el sistema
### Usuarios: soporte
1. Instalar fail2ban
1. Implementar login mediante SSH Key
1. Cambiar SSH de puerto
1. Apagar firmas de servicios & banners
1. Script SIEM
