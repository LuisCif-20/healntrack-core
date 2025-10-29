# Core Services

Este repositorio contiene los **servicios base** de la plataforma, necesarios para que los microservicios puedan funcionar correctamente.  
Actualmente incluye:

- **Keycloak** → Sistema de autenticación y autorización.
- **Kafka** → Sistema de mensajería y streaming distribuido.

## Requisitos previos

Se necesita tener las siguientes herramientas de forma local:

- **Docker** ≥ 24.x  
- **Docker Compose** ≥ 2.x  

Verifica las versiones con:

```bash
docker --version
docker compose version
```
## Crear la red compartida (Solo si no lo esta)

```bash
docker network create core-network || true
```

## Variables de entorno

Crea un archivo `.env` en la raiz del repositorio siguiendo el formato el archivo `.env.template` y ajusta las variables según tu entorno y otros servicios.

## Levantar los servicios

Una vez creada la red y configuradas las variables de entorno, ejecuta:

```bash
docker compose up -d
```

Esto hará que se levanten **Keycloak y Kafka**, conectados a la red `core-network`.  
Verifica que los contenedores estén corriendo:

```bash
docker ps
```