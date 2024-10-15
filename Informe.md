## 1. Título
Implementación de Contenedores con Nginx usando Docker

## 2. Tiempo de duración
15 minutos

## 3. Fundamentos
Docker permite crear contenedores ligeros que contienen aplicaciones y sus dependencias, ofreciendo un entorno aislado y portable. En este caso, utilizamos Docker para desplegar Nginx, un servidor web popular y eficiente, en dos contenedores separados.


El servidor web **Nginx** es conocido por su alto rendimiento y su capacidad para manejar múltiples conexiones simultáneas de manera eficiente. Esta práctica demostrará cómo usar Docker para crear un contenedor que aloje un servidor Nginx, permitiendo una configuración más rápida y sencilla en diferentes entornos de desarrollo.

En esta práctica, se utilizará Docker Playground, una herramienta que permite ejecutar contenedores de Docker en línea sin necesidad de instalar software en el equipo local.

 ![alt text](image-4.png)


**Conceptos clave**:
- **Docker**: Plataforma de contenedores que aísla aplicaciones en entornos controlados y replicables.
- **Nginx**: Servidor web y proxy inverso que optimiza la entrega de contenido estático y dinámico.
- **Contenedores**: Unidades ligeras y portátiles de software que contienen todo lo necesario para ejecutar una aplicación.

## 4. Conocimientos previos
- Comandos básicos en Linux
- Docker y virtualización
- Comandos de Docker

## 5. Objetivos a alcanzar
- Implementar un contenedor con Nginx usando Docker.
- Manipular archivos de configuración dentro del contenedor.
- Exponer un puerto de Docker para acceder al servicio Nginx desde un navegador.

## 6. Equipo necesario
- Computadora con sistema operativo Windows, Linux o Mac.
- Cuenta en Docker Hub para obtener imágenes de contenedores.
- Docker instalado 

## 7. Material de apoyo
- Guía de comandos básicos de Docker.
- "Cheat Sheet" de comandos Linux para una referencia rápida.
- Documentación de Nginx para personalizar la configuración del servidor.


## 8. Procedimiento


### Paso 1: Acceso a Docker Playground
Accede a Docker Playground, crea una cuenta y selecciona la opción para crear una nueva instancia.

### Paso 2: Crear un contenedor de Nginx
Ejecuta el siguiente comando para iniciar un contenedor de Nginx:

![alt text](image-3.png)

```bash
docker run --name sebastian -d -p 8086:80 nginx
```

Este comando descargará la imagen de Nginx y creará un contenedor, exponiendo el puerto 80 dentro del contenedor al puerto 8086 del host.

### Paso 3: Ingresar al contenedor
Ejecuta el siguiente comando para acceder al contenedor y modificar el archivo `index.html`:

```bash
docker exec -it nginx-site /bin/bash
```

Dentro del contenedor, crea un archivo HTML básico para que sea servido por Nginx:

![alt text](image-1.png)

```bash
echo "<html><body><h1>Hola, bienvenido a mi sitio web</h1></body></html>" > /usr/share/nginx/html/index.html
```

### Paso 4: Verificar el sitio web
Abre un navegador y accede a `http://<IP>:8086` (donde `<IP>` es la dirección IP de tu instancia de Docker Playground).

![alt text](image-2.png)

### Paso 5: Finalizar el contenedor
Si ya no es necesario continuar con la práctica, puedes detener y eliminar el contenedor con los siguientes comandos:

```bash
docker stop nginx-site
```



## 9. Resultados esperados

Al finalizar la práctica, deberías poder levantar un servidor Apache dentro de un contenedor de Docker que sirva una página HTML básica. El resultado esperado es que, al acceder a la URL proporcionada por Docker Playground, puedas visualizar correctamente el contenido de la página web servida por el contenedor.

![alt text](image-3.png)

![alt text](image-1.png)

![alt text](image-2.png)



## 10. Bibliografía

Merkel, D. (2014). Docker: Lightweight Linux Containers for Consistent Development and Deployment. Linux Journal, 2014(239), 2.

Kane, A. (2024). Docker in Action, Second Edition. Manning Publications.

Pahl, C., & Brogi, A. (2016). Cloud Container Technologies: A State-of-the-Art Review. IEEE Transactions on Cloud Computing, 5(4), 667-678.