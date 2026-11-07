# Academia Jaime Gallardo - Docker

## Descripcion
Proyecto de base de datos PostgreSQL 18 dockerizada para el sistema Academia Jaime Gallardo.

## Tecnologias
- Docker
- Docker Compose
- PostgreSQL 18
- DBeaver
- Git y GitHub

## Base de datos
Nombre: academia_jaime_gallardo

Tablas:
- asistencia
- curso
- docente
- estudiante
- evaluacion
- horario
- inscripcion
- pago
- rol
- transaccion
- usuario

Total de registros recuperados: 126.

## Configuracion

1. Clonar el repositorio.
2. Crear el archivo .env copiando .env.example.
3. Configurar una contraseña privada en .env.
4. Iniciar Docker:

docker compose up -d

## Conexion desde DBeaver

Host: localhost
Puerto: 5434
Base de datos: academia_jaime_gallardo

## Restauracion del respaldo

El respaldo debe obtenerse por un medio privado, ya que no se incluye en GitHub por contener datos personales.

Copiar el respaldo al contenedor:

docker compose cp academia_jaime_gallardo2.sql postgres:/tmp/academia.backup

Restaurar:

docker compose exec postgres pg_restore -U admin_academia -d academia_jaime_gallardo --no-owner --no-privileges /tmp/academia.backup

## Almacenamiento

Los datos se conservan mediante un volumen persistente de Docker.
