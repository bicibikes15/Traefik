<div align="center">
  <img src="https://raw.githubusercontent.com/traefik/traefik/v3.0/docs/content/assets/img/traefik.logo.png" alt="Traefik Logo" width="180"/>
  <h1 align="center">Traefik Docker Stack by DigitAllFran</h1>
  <p>
    <img src="https://img.shields.io/badge/Traefik-v3-blueviolet?style=for-the-badge&logo=traefikproxy&logoColor=white" alt="Traefik v3"/>
    <img src="https://img.shields.io/badge/Docker-2496ED?style=for-the-badge&logo=docker&logoColor=white" alt="Docker"/>
    <img src="https://img.shields.io/badge/Let's%20Encrypt-003A70?style=for-the-badge&logo=letsencrypt&logoColor=yellow" alt="Let's Encrypt"/>
    <img src="https://img.shields.io/badge/Ubuntu-22.04+-E95420?style=for-the-badge&logo=ubuntu&logoColor=white" alt="Ubuntu"/>
  </p>
</div>

> [!NOTE]
> **Stack listo para producción**  
> Traefik v3 asegurado con autenticación básica y certificados SSL automáticos vía Let's Encrypt. Seguro, robusto y fácil de entender.

> [!TIP]
> **Requisitos previos**  
> - **Servidor Linux** (Ubuntu 22.04+ recomendado)  
> - **Docker & Docker Compose** instalados  
> - **Un dominio** apuntando a la IP de tu servidor

> [!IMPORTANT]
> **El Ritual de Invocación (Instalación)**
> 1. **Clona el repositorio:**
>    ```
>    git clone https://github.com/bicibikes15/Traefik.git
>    cd Traefik
>    ```
> 2. **Crea la red externa:**
>    ```
>    docker network create digitallfran_net
>    ```
> 3. **Copia la plantilla de variables de entorno:**
>    ```
>    cp .env.example .env
>    ```
> 4. **Edita tu archivo `.env`:**
>    - `DOMINIO`: tu dashboard (ej. traefik.tudominio.com)
>    - `CORREO`: email real para notificaciones SSL
>    - `CLAVE_AUTH`: credenciales seguras.  
>      Genera con:
>      ```
>      echo $(htpasswd -nb TU_USUARIO TU_CLAVE_SECRETA)
>      ```
>      (o usa un generador online con APR1 MD5)
> 5. **Despliega el stack:**
>    ```
>    docker compose up -d
>    ```

> [!WARNING]
> **Verificación y acceso**  
> Espera ~1 minuto para que el contenedor inicie y genere el certificado.  
> Abre la URL definida en `DOMINIO`.  
> Ingresa con el usuario y clave del paso 4 para acceder al dashboard de Traefik.

> [!NOTE]
> **¿Listo?**  
> Si ves el dashboard tras loguearte, ¡misión cumplida!  
> Has desplegado una fortaleza digital con Traefik, Docker y Let's Encrypt.

---

¿Quieres agregar ejemplos de servicios detrás de Traefik, tips de seguridad o automatización extra? Avísame y te lo dejo aún más pro.
