**Libris - Sistema de Microservicios de Biblioteca**

Sistema de gestión de biblioteca basado en microservicios Django:

- auth_service : manejo de usuarios y autenticación
- Backend      : manejo de materiales y registros de lectura

Ambos servicios se comunican mediante JWT y se ejecutan con Docker.

-------------------------------------------------
** Indicaciones **
-------------------------------------------------

### 1. Clonar el repositorio
git clone https://github.com/Dilan1615/Contenedor_biblioteca.git
cd Contenedor_biblioteca

### 2. Construir y levantar los contenedores
docker compose build
docker compose up -d

### 3. Verificar que los servicios estén corriendo
* docker ps
* docker logs -f auth_service_libris
* docker logs -f lectura_api_libris

-------------------------------------------------
**Puertos**
-------------------------------------------------

* auth_service : 8001 -> 8000
* lectura_api  : 8003 -> 8002

-------------------------------------------------
**Variables de Entorno**
-------------------------------------------------

- SECRET_KEY : clave secreta de Django
- AUTH_URL   : URL interna del servicio de login (ej: http://auth_service_libris:8000)

Se recomienda crear un archivo `.env` y NO subirlo al repositorio.

-------------------------------------------------
**Estructura del Proyecto**
-------------------------------------------------

LibraryV1/
├── auth_service/         # Código Django de login
├── Backend/              # Código Django de biblioteca y lectura
│   ├── Backend/          # Código principal de la app Backend
│   ├── Dockerfile        # Dockerfile del servicio Backend
│   └── manage.py         # Comando principal de Django
└── docker-compose.yml    # Archivo de orquestación de Docker
