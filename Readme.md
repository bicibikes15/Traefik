# Traefik Docker Stack by DigitalLFRAN

Stack de Traefik v3 listo para producción, asegurado con autenticación básica y configurado para usar Let's Encrypt para certificados SSL automáticos. Este proyecto está diseñado para ser seguro, robusto y fácil de entender.

## Requisitos del Dojo

-   **Servidor Linux** (Ubuntu 22.04+ recomendado).
-   **Docker y Docker Compose** instalados.
-   **Un dominio** apuntando a la IP de tu servidor.

## El Ritual de Invocación (Instalación)

Sigue estos pasos en orden para desplegar tu fortaleza digital.

**1. Clonar el Repositorio**

Reemplaza `tu-github` y `tu-repositorio` con tu información real. Esto creará una carpeta local con el nombre de tu repositorio.

```bash
git clone [https://github.com/tu-github/tu-repositorio.git](https://github.com/tu-github/tu-repositorio.git)
cd tu-repositorio

2. Crear la Red Externa

Traefik necesita una red dedicada para comunicarse con otros contenedores de forma segura. Por defecto, este stack usa digitallfran_net.

Bash

docker network create digitallfran_net
3. Crear tu Archivo de Secretos (.env)

Este es el paso de seguridad más importante. Copiarás la plantilla env.example para crear tu propio archivo de configuración local .env.

El archivo .env es ignorado por Git y NUNCA debe hacerse público.

Bash

cp .env.example .env

4. Editar tu Archivo .env

Abre tu nuevo archivo .env con un editor de texto (ej. VS Code, Nano, etc.) y personaliza las siguientes variables:

DOMINIO: El dominio para tu dashboard (ej. traefik.tudominio.com).

CORREO: Tu email real para notificaciones sobre tus certificados SSL.

CLAVE_AUTH: Genera tus credenciales seguras usando una de estas opciones:

Opción A (Recomendado: Linux, macOS, o Git Bash en Windows):
Abre una terminal y ejecuta el siguiente comando. Git Bash, que viene con Git para Windows, incluye esta herramienta. Reemplaza TU_USUARIO y TU_CLAVE_SECRETA con los valores que desees.

Bash

echo $(htpasswd -nb TU_USUARIO TU_CLAVE_SECRETA)
Opción B (Alternativa para Windows):
Si no usas Git Bash, puedes usar un generador online de confianza. Busca en Google "htpasswd generator" y asegúrate de que use encriptación APR1 MD5. Introduce tu usuario y clave para generar la cadena.

Copia toda la línea resultante (ej. TU_USUARIO:$apr1$.....) y pégala como el valor para CLAVE_AUTH.

5. Desplegar el Stack

Con tu archivo .env listo y guardado, invoca el jutsu final para construir y ejecutar Traefik.

Bash

docker compose up -d
Verificación
Espera aproximadamente un minuto para que el contenedor se inicie y genere el certificado SSL. Luego, visita la URL que definiste en la variable DOMINIO.

Deberías ver una ventana de autenticación. Usa el usuario y la contraseña que creaste en el paso 4 para acceder al dashboard de Traefik.

¡Misión cumplida! Has desplegado una fortaleza.