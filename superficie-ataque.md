# Superficie de ataque (attack surface mapping)

Descubrimiento de activos externos de una organización: subdominios, IPs, ASN y rangos de red (UD1-6, Apartado 2).

## Herramientas web

- *(sin herramientas web específicas en este método)*

## Herramientas de terminal / escritorio

- **OWASP Amass** — Mapeo de superficie de ataque y enumeración de activos. <https://github.com/owasp-amass/amass>
  ```bash
  sudo apt install amass
  amass enum -passive -d dominio.com            # pasivo (no toca al objetivo)
  amass enum -active -brute -d dominio.com       # activo + fuerza bruta
  amass viz -d3 -d dominio.com                   # genera amass.html (grafo)
  ```
