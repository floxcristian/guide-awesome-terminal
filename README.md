# 1. Introducción a la línea de Comandos

## 1.1. Instalación de Ubuntu Bash en Windows

Configuración
Actualización y Seguridad
Para Programadores
Modo de Programador

Panel de Control
Programs
Activar o desactivar características de Windows
Subsistema de Windows para Linux
Permitir reinicio

Ir a Microsoft Store
Instalar Ubuntu

Instalar extensión `Remote - WSL`

## 1.2. Instalar nodejs

```
sudo apt update
```


```
curl -sL https://deb.nodesource.com/setup_12.x -o nodesource_setup.sh
```

otra forma de instalarlo:
```
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
```

**-sL:**

+ **-s:** (--silent) modo silencioso: no muestra la barra de progreso ni los mensajes de error.

+ **-L:** (--location) si el server informa que la página se ha movido, esta opción hará que curl rehaga la solicitud en el nuevo lugar.


**-E:** forma corta de ejecutar un script (como root) sin tener que guardar el archivo y luego ejecutarlo.

-o:
-E

<img src="https://i.imgur.com/2vSDiE6.png">

<img src="https://i.imgur.com/Ia2DRNl.png">

<img src="https://i.imgur.com/JK8VPcH.png">