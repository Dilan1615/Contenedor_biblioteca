Libris Microservicios
=====================

Proyecto con dos microservicios Django (auth_service y Backend) usando Docker y JWT para autenticación.

-----------------------------------------------------
1. Clonar el repositorio
-----------------------------------------------------
git clone https://github.com/Dilan1615/Contenedor_biblioteca.git
cd Contenedor_biblioteca

-----------------------------------------------------
2. Construir y levantar los contenedores
-----------------------------------------------------
docker compose build
docker compose up -d

- Servicios en la misma red interna de Docker.
- Puertos host → contenedor:
  - auth_service: 8001 -> 8000
  - lectura_api: 8003 -> 8002

-----------------------------------------------------
3. Verificar que estén corriendo
-----------------------------------------------------
docker ps
docker logs -f auth_service_libris
docker logs -f lectura_api_libris

-----------------------------------------------------
Notas
-----------------------------------------------------
- Variables sensibles (SECRET_KEY, AUTH_URL) deben estar en un archivo .env y NO subir a GitHub.
- Para reiniciar contenedores: docker compose restart <nombre_contenedor>
- Para detener y eliminar contenedores: docker compose down
