# 1. Introducción a la línea de Comandos

## 1.1. Instalación de Ubuntu Bash en Windows

Habilitar el Modo Programador:
```
> Configuración 
> Actualización y Seguridad 
> Para Programadores 
> Modo de Programador
```
Permitir un Subsistema de Windows para Linux:

```
> Panel de Control 
> Programas 
> Activar o desactivar características de Windows 
> Subsistema de Windows para Linux 
> Permitir reinicio
```
Instalar Ubuntu desde la Microsoft Store:

```
> Microsoft Store 
> Ubuntu
```

Actualizar la lista de programas que tiene el sistema:
```
sudo apt update
```

```
sudo apt upgrade
```

Programa de terminal que nos muestra información del sistema instalado.
```
sudo apt install screenfetch
```
Instalar extensión [Remote - WSL]() para VSCode. 
Extensión para Windows Subsystem for Linux.

## 1.2. Instalar nodejs

Actualizar la lista de programas que tiene el sistema:
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


Montar el disco C en ubuntu:

```
cd /mnt/c
```

Establecer un directorio para alojar nuestros archivos:
```
cd Users/
mkdir floxcristian
```

Abrir un proyecto con VSCode:
```
code .
```
Instalar zsh:
```
sudo apt install zsh
```
Instalar oh-my-zsh:
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
Configurar zsh/oh-my-zsh:
```
vim .bashrc
```

```
if test -t 1; then
exec zsh
fi
```

ESC
:wq



Instalando el template Powerlevel10k
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k

Cambiar el theme de zsh:
```
code .zshrc
INSERT
ZSH_THEME="powerlevel10k/powerlevel10k"
ESC
:wq

Instalando las fuentes Meslo GS NF:


Instalación de Powerline Fonts

Cambiar el tema y las fuentes

En VSCode ir al icono Settings
en el searchBox buscar terminal.font
MesloLGS NF

p10k configure
```




Atajos de teclado en Bash
```
ctrl + u: Limpiar lo escrito
ctrl + l: Limpiar toda la terminal
pwd: saber directorio donde estoy.
El directorio mnt es donde estan las particiones de windows.
mkdir: crear una carpeta
touch: crear archivo. Ejemple: touch index.js
vim index.js: para editar archivo
cat: ver contenido de un archivo. Ejemplo: cat index.js
```

# Instalar Fuentes

**MesloLGS NF:**
<img src="https://i.imgur.com/FOp76KU.png">
<img src="https://i.imgur.com/KKQLOpP.png">

**[Firacode Nerd Font Mono](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraMono):**
<img src="https://i.imgur.com/3Z7BU7A.png">

## Plugins para ZSH

```
code .zshrc
```

```
POWERLEVEL9K_MODE="nerdfont-complete"
```

# Windows Terminal

## Establecer Font

## Establecer WSL por defecto
