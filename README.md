# FUNDAMENTOS DE DOCkER
## RETO SEMANA 2

Tareas a realizar:
-Crear nuestro volumen
-Crear nuestra red
-Crear contenedor BACKEND
-Crear contenedor FRONTEND
-Conectar contentenedores a la red
-Comprobación en el navegador

### CREAR NUESTRO VOLUMEN
COMANDOS A UTILIZAR:
        
        $docker volume create pgdata
        $docker run --name postgres -e POSTGRES_PASSWORD=12345 -d -p 5432:5432 -v  pgdata:/var/lib/postgresql/data postgres

### CREAR NUESTRA RED
COMANDOS A UTILIZAR:

        $docker network create teemii-network -d bridge
        
### Crear contenedor BACKEND
COMANDOS A UTILIZAR:

        $docker run --name= teemii-backend --env=POSTGRES_HOST=postgres --env=POSTGRES_USER=postgres
        --env=POSTGRES_PASSWORD=12345
        --env=POSTGRES_DB=postgres -p 3000:3000 -d dokkaner/teemii-backend:develop

### Crear contenedor BACKEND
COMANDOS A UTILIZAR:

        $docker run --name= teemii-backend -p 8080:80 -d dokkaner/teemii-frontend:develop
        
### Conectar contenedores a la red
COMANDOS A UTILIZAR:

        $docker network connect teemii-network postgres
        $docker network connect teemii-network teemii-backend
        $docker network connect teemii-network teemii-frontend

### COMPROBACIÓN EN EL NAVEGADOR
Nos vamos a cualquier navegador, y colocamos en la barra de busquedas localhost:8080

Deberías de ver lo siguiente:

https://github.com/OscarAstua29/Fundamentos_docker/blob/main/Resultado%20Reto%202.png

Listo, ya tienes listo tu aplicación web desplegada.
