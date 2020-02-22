# 1. Introducción a la línea de Comandos

## 1.1. Instalación de Ubuntu Bash en Windows

Habilitar el Modo Programador:
```
> Configuración > Actualización y Seguridad > Para Programadores > Modo de Programador
```
Permitir un Subsistema de Windows para Linux:

```
> Panel de Control > Programas > Activar o desactivar características de Windows > Subsistema de Windows para Linux > Permitir reinicio
```
Instalar Ubuntu Bash:

```
> Microsoft Store > Instalar Ubuntu
```
Instalar extensión para VSCode que permite 

Instalar extensión `Remote - WSL`

## 1.2. Instalar nodejs

```bash
sudo apt update
```

```bash
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
```

```bash
sudo apt-get install gcc g++ make
```

```bash
sudo apt-get install -y nodejs
```
**-sL:**

+ **-s:** (--silent) modo silencioso: no muestra la barra de progreso ni los mensajes de error.

+ **-L:** (--location) si el server informa que la página se ha movido, esta opción hará que curl rehaga la solicitud en el nuevo lugar.


**-E:** forma corta de ejecutar un script (como root) sin tener que guardar el archivo y luego ejecutarlo.


Acceder al disco C desde ubuntu

```bash
cd /mnt/c
cd Users/
mkdir floxcristian
code .
```