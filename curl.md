<h1 align="center">Entendiendo Curl</h1>

<img width="100%" src="https://curl.haxx.se/logo/curl-logo.svg">

<p align="center">Curl es una gran herramienta para hacer peticiones y enviar datos usando HTTP. Sirve perfectamente para probar las APIs que creadas en cualquier lenguaje de programación con el paradigma REST.</p>

# Tabla de Contenido

- [Introducción](#introduction)
- [Guía General](#features)
- [Guía para Organizadores](#feedback)

# 1. Peticiones

## Obtener HTML de una página

```bash
curl https://www.parzibyte.me
```

## Obtener un JSON

Este ejemplo de JSON se realizó con [JSON Placeholder](#).

```bash
curl https://jsonplaceholder.typicode.com/posts/1
```

# 2. Especificar la salida

Si se desea guardar la salida en un archivo en vez de mostrarla en la terminal.

## Redirigir la salida

En este ejemplo guardamos la salida en un archivo `post.json`.
```bash
url https://jsonplaceholder.typicode.com/posts/1 > post.json
```

## Opción -o

Este es un método que ofrece curl.

```bash
curl -o post.json https://jsonplaceholder.typicode.com/posts/1
```

Estos métodos funcionan para HTML y cualquier otra salida.

# 3. Enviar datos con POST

Para enviar datos se especifica la opción `--data`(su modo abreviado es `-d`) seguido de los datos a enviar.

```bash
curl --data "nombre=Luis&alias=parzibyte" localhost/probar_curl.php
```

+ Note que no fue necesario especificar el método POST. 
+ Si no enviamos datos entonces supone que el método es GET.
+ Si los enviamos sin especificar el verbo, supone que es POST.

Los datos envíados son de tipo `form`.

# 4. Especificar otro verbo HTTP

+ La opción `-X` de curl indica el verbo que queremos usar. 

```bash
curl -X PUT --data "nombre=Luis&alias=parzibyte" localhost/probar_curl.php
```

Así podemos hacerlo para DELETE, PATCH, HEAD y otros.

# 5. Encabezados


https://parzibyte.me/blog/2019/05/14/aprende-a-usar-curl/
https://maslinux.es/aprendiendo-curl-con-algunos-ejemplos/
https://maslinux.es/como-usar-el-comando-curl-para-subir-y-descargar-archivos-sin-interaccion-del-usuario/
https://www.hostinger.es/tutoriales/comando-curl/
