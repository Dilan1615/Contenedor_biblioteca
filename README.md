Libris - Microservicios de Biblioteca

Sistema de gestión de biblioteca con dos microservicios Django:
- auth_service: manejo de usuarios y autenticación
- Backend: manejo de materiales y registros de lectura
Se comunican internamente mediante JWT y se ejecutan en Docker.

⚡ Inicio Rápido (1 minuto)

1. Clonar el repositorio
git clone https://github.com/Dilan1615/Contenedor_biblioteca.git
cd Contenedor_biblioteca

2. Construir y levantar los contenedores
docker compose build
docker compose up -d

3. Verificar que estén corriendo
docker ps
docker logs -f auth_service_libris
docker logs -f lectura_api_libris

🎯 Puertos
auth_service: 8001 -> 8000
lectura_api: 8003 -> 8002

🛠️ Configuración y Variables de Entorno
- SECRET_KEY: clave secreta de Django
- AUTH_URL: URL interna del servicio de login (ej: http://auth_service_libris:8000)
- Se recomienda crear un archivo .env y NO subirlo al repositorio

📦 Estructura del Proyecto
LibraryV1/
├── auth_service/         # Código Django de login
├── Backend/              # Código Django de biblioteca y lectura
│   ├── Backend/
│   ├── Dockerfile
│   └── manage.py
└── docker-compose.yml

🔧 Comandos útiles
- Reiniciar un contenedor: docker compose restart <nombre_contenedor>
- Detener y eliminar contenedores: docker compose down
- Migrar base de datos: docker compose exec <contenedor> python manage.py migrate
- Crear superusuario: docker compose exec <contenedor> python manage.py createsuperuser


