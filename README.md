<h1 align="center"> Introducción a la línea de Comandos</h1>

# 1. Instalar Ubuntu Bash en Windows

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

## 1.2. Instalar extensión Remote - WSL para VSCode

Esta es una extensión para Windows Subsystem for Linux.

Ir a VSCode y buscar e instalar la extensión **Remote - WSL**.


## 1.3. Instalar Screenfetch

Screenfetch rd un programa de terminal que nos muestra información del sistema instalado.

Instalar screenfetch:
```
sudo apt install screenfetch
```


## 1.4. Instalar nodejs

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

# Personalizando nuestra terminal

## Instalar zsh

**zsh** es un shell compatible con bash, pero que añade varias funcionalidades. Una de las más interesantes es su integración con git.

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
code .bashrc
```
Añadir lo siguiente después del primer comentario:
```
if test -t 1; then
exec zsh
fi
```



# 1.5. Instalar el tema Powerlevel10k para Oh-My-ZSH

Clonar el respositorio:
```
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

Abrir el archivo de configuración de zsh:
```
code .zshrc
```
Añadir el siguiente código para establecer **Powerlevel10k** como tema por defecto:
```
ZSH_THEME="powerlevel10k/powerlevel10k"
```

Instalando las fuentes Meslo GS NF:


Instalación de Powerline Fonts

Cambiar el tema y las fuentes







# 3. Instalar Nerd Fonts

Para la configuración correcta de los glifos, no es compatible cualquier fuente.
Por ello vamos al [repositorio de Nerd Fonts](https://github.com/ryanoasis/nerd-fonts,), descargamos la fuente deseada y la instalamos en el sistema.

## 3.1. Establecer fuente en la terminal de Ubuntu

## 3.2. Establecer fuente en la terminal de VSCode

1. En VSCode ir al icono **Settings**.
2. En el searchBox buscar **terminal.font**
3. Establecer **MesloLGS NF** como fuente.

**MesloLGS NF:**
<img src="https://i.imgur.com/FOp76KU.png">
<img src="https://i.imgur.com/KKQLOpP.png">

**[Firacode Nerd Font Mono](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraMono):**
<img src="https://i.imgur.com/3Z7BU7A.png">


## 1.8. Plugins para ZSH

Abrir el archivo de configuración de zsh:
```
code .zshrc
```

```
POWERLEVEL9K_MODE="nerdfont-complete"
```

# Windows Terminal

## Establecer Font

## Establecer WSL por defecto
