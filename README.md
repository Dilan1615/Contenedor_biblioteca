================================================================================
                                LIBRIS
            Sistema de Microservicios de Biblioteca
================================================================================

Descripción
--------------------------------------------------------------------------------
Sistema de gestión de biblioteca basado en microservicios Django:

  - auth_service : Manejo de usuarios y autenticación
  - Backend      : Manejo de materiales y registros de lectura

Ambos servicios se comunican mediante JWT y se ejecutan con Docker.

================================================================================
                              INICIO RÁPIDO
--------------------------------------------------------------------------------

1. Clonar el repositorio
   ---------------------
   git clone https://github.com/Dilan1615/Contenedor_biblioteca.git
   cd Contenedor_biblioteca

2. Construir y levantar los contenedores
   --------------------------------------
   docker compose build
   docker compose up -d

3. Verificar que los servicios estén corriendo
   -------------------------------------------
   docker ps
   docker logs -f auth_service_libris
   docker logs -f lectura_api_libris

================================================================================
                                   PUERTOS
--------------------------------------------------------------------------------

  auth_service : 8001 -> 8000
  lectura_api  : 8003 -> 8002

================================================================================
                           VARIABLES DE ENTORNO
--------------------------------------------------------------------------------

  - SECRET_KEY : Clave secreta de Django
  - AUTH_URL   : URL interna del servicio de login
                 (ej: http://auth_service_libris:8000)

  Se recomienda crear un archivo `.env` y NO subirlo al repositorio.

================================================================================
                           ESTRUCTURA DEL PROYECTO
--------------------------------------------------------------------------------

LibraryV1/
├── auth_service/         # Código Django de login
├── Backend/              # Código Django de biblioteca y lectura
│   ├── Backend/
│   ├── Dockerfile
│   └── manage.py
└── docker-compose.yml

================================================================================
