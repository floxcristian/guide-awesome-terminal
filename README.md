<h1 align="center"> Introducción a la línea de Comandos</h1>

# Objetivos 

+ Aumentar las capacidades de configuración del shell y terminal de Ubuntu.
+ Personalizar el prompt de nuestra Terminal utilizando la shell ZSH y el programa oh-my-zsh.

# 1. Instalar el Subsistema de Ubuntu en Windows 10

Hace ya tres años, Microsoft presentó **WSL**, lo que son las siglas de Windows Susbystem for Linux. 
el terminal de Ubuntu nos ofrece posibilidades muy interesantes que merece la pena tener a mano.

Lógicamente, no es perfecto. Tal y como explicaremos a continuación, habrá algunas tareas que no podamos realizar, en parte porque lo que vamos a instalar y usar es solo un terminal, es decir, una ventana en la que introduciremos las líneas de comandos para hacer lo que necesitemos. A continuación os explico los pasos a seguir para instalar el terminal de Ubuntu 18.04 en Windows 10 y qué podemos hacer con él.

Y eso sería todo. Ya tenemos el terminal de Ubuntu instalado en Windows. Por defecto ya podemos usar comandos como el APT, por lo que la primera prueba que recomiendo es instalar “neofetch”:

# 3. ¿Qué podemos y no podemos hacer con WSL?

Lo que hay que tener claro es qué es un terminal. Explicado rápido y mal, es un sistema operativo que funciona única y exclusivamente con líneas de comandos y no puede mostrar imágenes más allá del texto que introducimos/muestra. Esto significa que, por ejemplo, podemos instalar cualquier programa que esté disponible en los repositorios de Ubuntu, pero no podremos lanzar aquellos que hagan uso de una GUI, como Firefox (aunque no tendría sentido instalar nada que esté disponible para Windows de manera oficial). También significa que no podremos seguir, por ejemplo, este tutorial para grabar la pantalla con ffmpeg: si introducimos el comando y presionamos Intro, empezará la tarea, pero parará cuando se dé cuenta de que “no hay ningún monitor disponible”.

# 4. Problema con las rutas

Algo que me gustaría que solucionaran en el futuro está relacionado con las rutas. No son lo mismo y no las reconoce igual. El problema está en cómo las escribe Windows y cómo las necesita Linux. Lo bueno es que es fácil recordar cómo convertir una ruta de Windows a Linux.

Por ejemplo: la ruta C:\Users\Pablo\Destktop\ de Windows sería /mnt/c/Users/Pablo/Desktop. Sabiéndolo, si alguna vez queremos arrastrar un archivo de Windows al terminal de Ubuntu, lo que tenemos que hacer es básicamente cambiar las barras invertidas por barras normales, poner la “c” minúscula, quitar los dos puntos y delante añadir “/mnt/”. No es difícil de recordar.


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

Actualizar la lista de programas de Ubuntu:
```
sudo apt update
```

```
sudo apt upgrade
```

## 1.2. Instalar extensión Remote - WSL para VSCode

Esta es una extensión para **Windows Subsystem for Linux**.

Ir a VSCode y buscar e instalar la extensión **Remote - WSL**.


## 1.3. Instalar Neofetch

Neofetch es un programa de terminal que nos muestra información del sistema instalado.

Instalar neofetch:
```
sudo apt install neofetch
```
Ver información de nuestro sistema:
```
neofetch
```

<img src="https://i.imgur.com/XpsUHdA.png">

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

Verificar que la instalación ha sido completada:
```
zsh --version
```

## Instalar Oh-My-ZSH

 **Oh-My-ZSH** es un proyecto de código abierto que nos ayudará a configurar el shell utilizando un sin número de plugins que tendremos a nuestra disposición. 

Instalar oh-my-zsh:
```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

## Establecer zsh como shell por defecto

??????
```
chsh  -s  /bin/zsh
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

# Instalar Fuentes Powerline

 Para poder utilizar el tema anterior será necesario la instalación de las fuentes **Powerline** y **Awesone-Powerline**.

 Instalar fuentes **Powerline**:
 ```
git clone https://github.com/powerline/fonts.git --depth=1
cd fonts
./install.sh
cd ..
rm -rf fonts
 ```
 Instalar fuentes **Awesome-Powerline**:
 ```
git clone https://github.com/gabrielelana/awesome-terminal-fonts
cp -r ~/awesome-terminal-fonts/build ~/.fonts
fc-cache -fv ~/.fonts
 ```


# 3. Instalar Nerd Fonts

Otro tema que mezcla muy bien los distintos glyphs y letras es el tema basado en Nerd Fonts, este es un tema que incluye diferentes iconos de distintas fuentes como Font Awesome, Devicons, Octicons y otros más. 
Para la configuración correcta de los glifos, no es compatible cualquier fuente.
Por ello vamos al [repositorio de Nerd Fonts](https://github.com/ryanoasis/nerd-fonts,), descargamos la fuente deseada y la instalamos en el sistema.

A continuación una vista previa de las Nerd Fonts.

**MesloLGS NF:**
<img src="https://i.imgur.com/FOp76KU.png">
<img src="https://i.imgur.com/KKQLOpP.png">

**[Firacode Nerd Font Mono](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraMono):**
<img src="https://i.imgur.com/3Z7BU7A.png">

## 3.1. Establecer fuente en la terminal de Ubuntu

## 3.2. Establecer fuente en la terminal de VSCode

1. En VSCode ir al icono **Settings**.
2. En el searchBox buscar **terminal.font**
3. Establecer **MesloLGS NF** como fuente.




## 1.8. Plugins para ZSH

Abrir el archivo de configuración de zsh:

zsh-syntax-highlighting?
```
code .zshrc
```

```

POWERLEVEL9K_MODE="nerdfont-complete"

POWERLEVEL9K_LEFT_PROMPT_ELEMENTS=(root_indicator dir dir_writable vcs)
POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS=(status background_jobs time battery)

POWERLEVEL9K_DIR_PATH_SEPARATOR=$' \uE0B1 '
POWERLEVEL9K_TIME_FORMAT="%D{%d/%m/%y - %H:%M}"

# Prompt settings
POWERLEVEL9K_PROMPT_ADD_NEWLINE=true
POWERLEVEL9K_PROMPT_ON_NEWLINE=true
POWERLEVEL9K_RPROMPT_ON_NEWLINE=true
POWERLEVEL9K_MULTILINE_FIRST_PROMPT_PREFIX="%K{white}%k"
POWERLEVEL9K_MULTILINE_LAST_PROMPT_PREFIX="%K{green}%F{black} \uf554 %f%F{green}%k\ue0b0%f "

plugins=( git )

source $ZSH/oh-my-zsh.sh
source /usr/share/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
source /bin/z.sh

neofetch

alias ll="ls -l"
alias la="ls -a"
alias nz="nano ~/.zshrc"
alias sz=". ~/.zshrc"
```

# Windows Terminal

## Establecer Font

## Establecer WSL por defecto
