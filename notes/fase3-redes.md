# Fase 3 - Redes

- App escucha en 0.0.0.0:5000 (no en 127.0.0.1)
- ss -tlnp muestra LISTEN 0.0.0.0:5000 pid 4079
- curl 5000 OK, curl 9999 Connection refused
- Recorrido: Chrome Windows -> WSL2 NAT -> WSL eth0 172.20.84.45 -> Flask 0.0.0.0:5000
- localhost en PC = WSL, localhost en contenedor = solo contenedor aislado, necesita 0.0.0.0
