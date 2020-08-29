<h1 align="center"> Introducción a la línea de Comandos</h1>

# Tabla de Contenido

+ 1. [Instalar WSL]()
+ 2. [Instalar Ubuntu]()
+ Instalar la shell ZSH
+ Instalar Oh-My-ZSH
+ Instalar el tema Powerlevel10k
+ Instalar Plugins

En este tutorial vamos a:

+ Instalar la shell **ZSH** sobre Ubuntu como Subsistema de Windows **(WSL)**.
+ Personalizar la shell **ZSH** con el framework **Oh-My-ZSH**.
+ Personalizar la shell con el tema **Powerlevel10k**.

# Objetivos 

+ Aumentar las capacidades de configuración de la shell y terminal de Ubuntu.
+ Personalizar el prompt de nuestra terminal utilizando la shell **ZSH** y el programa **oh-my-zsh**.

# Requerimientos

+ Windows 10 Anniversary Update build 14316 o superior.


# 1. Instalar WSL

En 2017 Microsoft presentó **WSL**, siglas de **Windows Susbystem for Linux**.
La terminal de Ubuntu nos ofrece posibilidades muy interesantes que merece la pena tener a mano.

Lógicamente, no es perfecto. Tal y como explicaremos a continuación, habrá algunas tareas que no podamos realizer, en parte porque lo que vamos a instalar y usar es solo la terminal, es decir, una ventana en la que introduciremos las líneas de comandos para hacer lo que necesitemos.

## 1.1. Método 1: Usando la Powershell

```bash
powershell -command Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

## 1.2. Método 2: Manualmente


1. Habilitar el Modo Programador:
```
> Configuración 
> Actualización y Seguridad 
> Para Programadores 
> Modo de Programador
```
2. Habilitar WSL:

```
> Panel de Control 
> Programas 
> Activar o desactivar características de Windows 
> Subsistema de Windows para Linux 
> Permitir reinicio
```

<img src="https://i.imgur.com/6pMKiyu.png">

3. Instalar Ubuntu desde la Microsoft Store:

```
> Microsoft Store 
> Ubuntu
```
<img src="https://i.imgur.com/FngJJSE.png">

4. Actualizar la lista de programas de Ubuntu:
```bash
sudo apt update
```
5. 
```bash
sudo apt upgrade
```

# 3. ¿Qué podemos y no podemos hacer con WSL?

+ Podemos instalar cualquier programa que esté disponible en los repositorios de Ubuntu. 
+ No podremos lanzar aquellos programas que hagan uso de una GUI. 
+ No podremos seguir, por ejemplo, este tutorial para grabar la pantalla con **ffmpeg**. Si introducimos el comando y presionamos Intro, empezará la tarea, pero parará cuando se dé cuenta de que *no hay ningún monitor disponible*.

# 4. Rutas en Windows y Linux

+ Las rutas en **Windows** y **Linux** no se reconocen de la misma forma.
+ La ruta de **Windows** `C:\Users\Pablo\Destktop\` en **Linux** sería `/mnt/c/Users/Pablo/Desktop`.


## 1.2. Instalar extensión Remote - WSL para VSCode

Esta es una extensión para **Windows Subsystem for Linux**.

<img src="https://i.imgur.com/IdXTApj.png">


## 1.3. Instalar Neofetch

Neofetch es un programa de terminal que nos muestra información del sistema instalado.

1. Instalar neofetch:
```bash
sudo apt install neofetch
```
2. Ver información de nuestro sistema:
```bash
neofetch
```

<img src="https://i.imgur.com/peEdv25.png">

## 1.4. Instalar nodejs

1. 
```bash
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
```
2.  
```bash
sudo apt-get install gcc g++ make
```
3. 
```bash
sudo apt-get install -y nodejs
```
**-sL:**

+ **-s:** (--silent) modo silencioso: no muestra la barra de progreso ni los mensajes de error.

+ **-L:** (--location) si el server informa que la página se ha movido, esta opción hará que curl rehaga la solicitud en el nuevo lugar.


**-E:** forma corta de ejecutar un script (como root) sin tener que guardar el archivo y luego ejecutarlo.


## Instalar zsh shell sobre Linux

**zsh** es un shell compatible con bash, pero que añade varias funcionalidades. Una de las más interesantes es su integración con git.

1. Instalar zsh:
```bash
sudo apt install zsh
```

2. Verificar instalación:
```bash
zsh --version
```

3. Establecer zsh como shell por defecto:
```bash
chsh -s $(which zsh)
```

4. Reiniciar la terminal y verificar que imprima `/usr/bin/zsh` al ejecutar:
```bash
echo $SHELL
```

## Instalar Oh-My-ZSH

 **Oh-My-ZSH** es un proyecto de código abierto que nos ayudará a configurar el shell utilizando un sin número de plugins que tendremos a nuestra disposición. 

1. Instalar oh-my-zsh:
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
---

Abri el archivo de configuración de bash:
```bash
code .bashrc
```
Añadir lo siguiente después del primer comentario:
```bash
if test -t 1; then
exec zsh
fi
```

# 1.5. Instalar el tema Powerlevel10k para Oh-My-ZSH


## Compatibilidad con Powerlevel9k

Este tema entiende todos los parámetros de configuración de **Powerlevel9k**.

<img src="https://raw.githubusercontent.com/romkatv/powerlevel10k-media/master/9k-compatibility.gif">

1. Clonar el respositorio en la carpeta de temas personalizados:
```bash
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```

2. Abrir el archivo de configuración de zsh:
```bash
code .zshrc
```
3. Añadir el siguiente código para establecer **Powerlevel10k** como tema por defecto:
```bash
ZSH_THEME="powerlevel10k/powerlevel10k"
```

Para la configuración correcta de los iconos, no es compatible cualquier fuente. Existen dos opciones para el correcto funcionamiento de los iconos.

# [Opción 1] Instalar Fuentes Powerline

Para que el tema**Powerlevel10k** se renderice correctamente será necesario la instalación de las fuentes **Powerline** y **Awesone-Powerline**. se necesita una fuente que tenga los iconos **Powerline**. Estos se usan al principio y final de los segmentos para producir la apariencia **Powerline**.

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


# [Opción 2] Instalar Nerd Fonts
---
Descargar e Instalar la fuente **FuraMono Nerd Font**. Para Ubuntu necesitará la fuente **FiraMono**, de lo contrario, es posible que la terminal no muestre la fuente. Basta con descargar e instalar la versión regular de la fuente deseada, pero si en alguna terminal configuramos la fuente en negrita o cursiva esta no se mostrará correctamente por lo que se recomienda instalar el paquete de fuente completo.
---


https://github.com/ryanoasis/nerd-fonts/blob/master/readme_es.md#option-3-install-script

Nerd Fonts es un proyecto que parcha las fuentes que un desarrollador va a usar con un gran número de iconos. Especificamente añade iconos extra de algunas **fuentes de iconos** como **Font Awesome**, **Devicons**, **Octicons**, y otras.

Si bien Nerd Fonts toma algunas fuentes populares de desarrollo y les añade una cantidad de iconos, también hay un [parchador]() de fuentes disponible si tu fuente preferida no ha sido parchada previamente.

En la siguiente imagen se puede ver el conjunto de iconos incluidos.

<img src="https://raw.githubusercontent.com/ryanoasis/nerd-fonts/master/images/sankey-glyphs-combined-diagram.svg?sanitize=true">


Existen varios formas de instalar las fuentes **Nerd Fonts**. En este artículo se mostrarán solo algunos métodos.

## 3.1. Método 1: Curl

El primer método consiste en clonar el repositorio y luego ejecutar el sript install.sh el cual nos instalaría todo el paquete de fuentes incluidas en el repositorio. Esto significa que el proceso tomaría mucho tiempo y espacio en nuestra unidad de almacenamiento. Este proceso se ejecutaría de la siguiente forma:

```bash
git clone https://github.com/ryanoasis/nerd-fonts.git
cd nerd-fonts
sudo ./install.sh
```
En el caso de obtener algún error durante la ejecución del último comando, revisar que el archivo install.sh cuenta con los permisos de ejecución, o lo que es lo mismo, se los asignamos directamente de la siguiente manera:
```bash
chmod +x install.sh
```


## 3.2. Método 2: Descarga Manual

Descargar rápidamente una fuente individual, descargar desde el [directorio patched-fonts/](https://github.com/ryanoasis/nerd-fonts#patched-fonts).
---
Descargar un paquete **font family** de variaciones (negrita, cursiva, etc).

Seleccione la **font family** y luego seleccione el directorio `complete`.
+ Si esta en Windows elija la fuente con el súfijo `Windows Compatible`.
    - Esta incluye ajustes específicos para garantizar que la fuente funciones en Windows, en particular la identificación del monoespaciado y las limitaciones en el nombre de la fuente.
+ Si esta limitado a fuentes monoespaciadas (debido a su terminal u otros) elija una fuente con el sufijo `Mono`.
    - Esta denota que los iconos de Nerd Font serán monoespaciados, no necesariamente que toda la fuente será monoespaciada.

---

El segundo método consiste en instalar solo las fuentes necesarias, en este caso estamos hablando de Share Tech Mono Nerd Font Complete Mono y Shure Tech Mono Nerd Font Complete. Estas fuentes han sido ya parchadas por lo cual no es necesario que hagamos ningún procedimiento adicional. Solo debemos descargar la fuentes de este enlace y copiarlas en el directorio en donde se encuentran instaladas las fuentes en su sistema operativo, en la mayoria de los casos en la carpeta `~/.fonts`.

Una vez instaladas las fuentes solo necesitamos decirle al terminal que debe usar estas fuentes por defecto para así poder contar con los glyghs de este paquete así como la fuente en si. 

Para esto hacemos una vez click con el botón derecho del ratón sobre algún punto dentro de la ventana de Terminatro y seleccionamos Preferencias del menú desplegable, luego cambiamos las fuentes que aparecen por defecto en la pestaña llamada Global, seleccionamos ShureTechMono Nerd Font y hacemos lo propio en la pestaña Profile -> General.

Por último vamos a necesitar un archivo de configuración .zshrc, este es un archivo el cual debe incluir una serie de instrucciones dirigidas a seleccionar los diferentes iconos que aparecerán en el Terminal así como el arreglo en el cual estarán dispuestos.

Ejemplos de archivos de configuración pueden ser encontrados en este [enlace](https://github.com/tonylambiris/dotfiles/blob/master/dot.tmux.conf). Adicional les puedo dejar el archivo de configuración de mi Terminal la cual está basada en los archivos de configuración a los que hago previa referencia. Dichos archivos de configuración los podrán encontrar en el siguiente [enlace](https://github.com/jdelacruz26/misccode/tree/zsh-config).


 son dos archivos relevantes los cuales tendrán que copiar en su directorio personal como archivos ocultos,
 
 ```bash
cd misccode
cp my.zshrc ~/.zshrc
cp my.inputrc ~/.inputrc
 ```

me he limitado a escoger algunos paquetes de fuentes parcheadas más populares – posiblemente no son las tipografías que ustedes querrían –. Para que se entienda la diferencia entre manual y archivo de descarga, mientras el primero el usuario escoge un solo tipo de tipografía por ejemplo: Hack regular, el archivo de descarga baja el conjunto completo de Hack, es decir: Hack regular/bold/itálica etc.

Una vez que hayas descargado algunas o todas las fuentes en algún lugar de tu carpeta personal el siguiente paso es descomprimirlas y copiarlas a la ubicación ~/.local/share/fonts. En caso de no existir la carpeta fonts la creamos de la siguiente forma:

Una vez copiadas las fuentes en la carpeta mencionada refrescamos la cache:
```bash 
fc-cache -fv ~/.local/share/fonts
```


Abrir el archivo de configuración de **ZHS**:
```bash
code .zshrc
```
Añadir la siguiente linea para utilizar las **Nerd Fonts**:
```bash
POWERLEVEL9K_MODE="nerdfont-complete"
```
Por ello vamos al [repositorio de Nerd Fonts](https://github.com/ryanoasis/nerd-fonts,), descargamos la fuente deseada y la instalamos en el sistema.

## Método 3: Curl
Ejecutar la siguiente linea donde: DroidSansMono hace referencia a la fuente que en este caso se desea descargar.

```bash
cd ~/.local/share/fonts && curl -fLo "Droid Sans Mono for Powerline Nerd Font \Complete.otf" https://github.com/ryanoasis/nerd-fonts/raw/master/patched-fonts/\DroidSansMono/complete/Droid%20Sans%20Mono%20Nerd%20Font%20Complete.otf
```
---

A continuación una vista previa de las Nerd Fonts.

**MesloLGS NF:**
<img src="https://i.imgur.com/FOp76KU.png">
<img src="https://i.imgur.com/KKQLOpP.png">

**[Firacode Nerd Font Mono](https://github.com/ryanoasis/nerd-fonts/tree/master/patched-fonts/FiraMono):**
<img src="https://i.imgur.com/3Z7BU7A.png">

## 3.1. Establecer fuente en la terminal de Ubuntu

## 3.2. Establecer fuente en la terminal de VSCode

1. Ir al icono **Settings**.
2. Buscar **terminal.integrated.fontFamily**.
3. Establecer la fuente deseada. Por ejemplo, **MesloLGS NF**.

<img src="https://miro.medium.com/max/1345/1*DdS1YVBRVq1oCI-YKjqB0Q.png">

## Configurar el tema Powerlevel10k

Ejecutar:
```bash
p10k configure
```
Solo seguir los pasos que se vean en la terminal.
En la último paso de configuración selecionar la opción 3 correspondiente a `verbose` y luego poner `Y`.




## 1.8. Plugins para ZSH

1. Instalar plugins deseados.

**autosuggestion**:
```bash
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```

**zsh-syntax-highlighting**:
```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

2. Abrir el archivo de configuración de zsh:
```bash
code .zshrc
```
3. Añadir plugins al archivo de configuración de **ZSH**. Para ello hacer scroll hasta encontrar:
```bash
plugins=(git)
```
4. Añadir los plugins descargados:
```bash
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

```bash
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

<img src="https://miro.medium.com/max/2220/1*FKrcKH675zHiAHb78WHP3Q.png">

Una vez instalado y ejecutado deberías ver la shell Powershell. Necesitas ir a las configuraciones clickeando el dropdown.

<img src="https://miro.medium.com/max/1813/1*7pn49RXDcs8R-GbI3RIuvQ.png">

Esto abrirá un archivo de configuración JSON en el notepad. Aquí deberemos hacer scroll hasta encontrar `"name": "Ubuntu"` y establecer la fuente deseada añadiendo la siguiente línea:

```
"fontFace": "FuraMono Nerd Font",
```

<img src="https://miro.medium.com/max/1893/1*N3l6QFszAp428eU-p1gS0A.png">

<img src="">

## Establecer Font

## Establecer WSL por defecto


# Conclusiones

En este pequeño instructivo su pudo mostrar como actualizar nuestra terminal por defecto en Ubuntu, instalando una nueva llamada Terminator. Esta terminal nos permitió dividir la ventana principal en subventanas además de la opción de agrupar las subventanas para realizar un Broadcast entre ellas.

Por último, pudimos ver cómo instalando la shell ZSH y el programa oh-my-zsh, acompañado de otros paquetes de fuentes como Powerline y Nerd Fonts, lográbamos configurar el prompt de nuestra terminal dándole un aspecto más atractivo que nos permitiera !echarle más ganas durante nuestras horas de trabajo o diversión!
