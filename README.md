# reto-devops - por Marcello

Fase 1: App Flask corriendo localmente en Linux con venv.
Fase 2: Versionado con Git.

## Como correr
source venv/bin/activate
python app/app.py

Endpoints:
- / -> Hola
- /health -> ok

## Fase 4 - Docker
docker build -t reto-devops:fase4 .
docker run -p 5000:5000 reto-devops:fase4
# http://localhost:5000
