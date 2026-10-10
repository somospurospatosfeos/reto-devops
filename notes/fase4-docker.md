# Fase 4 - Docker

## Dockerfile usado
FROM python:3.11-slim
WORKDIR /app
COPY app/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY app/ app/
EXPOSE 5000
ENV PORT=5000
CMD ["python", "app/app.py"]

## Comandos
- docker build -t reto-devops:fase4 .
  -> Successfully built 485adc270014
- docker run -d --name reto-fase4 -p 5000:5000 reto-devops:fase4
- docker ps -> muestra contenedor UP
- docker logs reto-fase4 -> Running on all addresses (0.0.0.0)
- curl localhost:5000 -> Hola desde Fase 1
- docker stop reto-fase4 && docker rm reto-fase4 (borrar y recrear)

## Por qué funciona
La app escucha en 0.0.0.0:5000 (no 127.0.0.1) por eso funciona dentro del contenedor.
Publicamos puerto con -p 5000:5000 -> Windows Chrome -> WSL -> Docker.

## Reproducibilidad
git clone https://github.com/somospurospatosfeos/reto-devops.git
docker build -t reto-devops .
docker run -p 5000:5000 reto-devops
