# OSINT / Recopilación de información
## Herramientas web

### Buscadores y Google Hacking (dorks)
- **Google búsqueda avanzada** — Operadores para acotar resultados. <https://www.google.es/advanced_search>
  ```text
  site:dominio.com
  site:dominio.com filetype:pdf
  intitle:"index of"
  "@dominio.com" -site:dominio.com
  ```
- **Google Alerts** — Avisos automáticos por término. <https://www.google.es/alerts>
- **Shodan** — Buscador de dispositivos y servicios expuestos. <https://www.shodan.io/> · <https://exposure.shodan.io/>
- **Censys** — Buscador de hosts, certificados y servicios. <https://search.censys.io/>
- **Wayback Machine (archive.org)** — Histórico de versiones de una web. <https://archive.org/>
- **CachedView** — Versiones cacheadas de páginas. <https://cachedview.com/>
- **robots.txt** — Archivo del sitio que revela rutas/directorios (`https://sitio/robots.txt`).

### Dominios, DNS y subdominios
- **DNSDumpster** — Mapa DNS, subdominios y servicios de un dominio. <https://dnsdumpster.com/>
- **Robtex** — Información DNS, IP y red de un dominio. <https://www.robtex.com/>
- **osint.sh (subdomain)** — Enumeración de subdominios online. <https://osint.sh/subdomain>
- **crt.sh** — Subdominios vía Certificate Transparency. <https://crt.sh/>
- **WhoisXML Subdomains** — Descubrimiento de subdominios. <https://subdomains.whoisxmlapi.com/>

### Correos y brechas de datos
- **HaveIBeenPwned** — Comprueba si un correo aparece en filtraciones. <https://haveibeenpwned.com/>
- **LeakCheck.io** — Comprobación de credenciales filtradas. <https://leakcheck.io/>
- **Dehashed** — Buscador en bases de datos filtradas. <https://dehashed.com/>
- **Ontelx (ontelx.io)** — Cuentas y archivos en filtraciones. <https://ontelx.io/>
- **Mozilla Monitor** — Avisos de filtraciones de un correo. <https://monitor.mozilla.org/>
- **Hunter.io** — Correos y patrón de correo de un dominio. <https://hunter.io/>
- **IntelX** — Datos filtrados, leaks y pastes. <https://intelx.io/>
- **Pastebin** — Textos públicos donde a veces aparecen filtraciones. <https://pastebin.com/>

### Personas e identidades
- **OSINT Framework** — Directorio de recursos OSINT por categoría. <https://osintframework.com/>
- **Fingerprint (fingerprint.to)** — Perfiles y redes a partir de un correo/usuario. <https://fingerprint.to/>
- **FamilyTreeNow** — Registros de personas y familiares. <https://www.familytreenow.com/>
- **FamilySearch** — Registros genealógicos. <https://www.familysearch.org/>
- **Ancestry** — Registros genealógicos. <https://www.ancestry.com/>
- **GenealogyBank** — Archivos y registros históricos. <https://www.genealogybank.com/>
- **I Know Where Your Cat Lives** — Ejemplo de geolocalización por metadatos de fotos. <https://iknowwhereyourcatlives.com/>
- **Reddit r/OSINT** — Comunidad y recursos OSINT. <https://www.reddit.com/r/OSINT/>

## Herramientas de terminal / escritorio

### Dominios y DNS
- **nslookup / dig / whois** — Consultas DNS y datos de registro.
  ```bash
  nslookup dominio.com
  nslookup -type=mx dominio.com      # servidores de correo
  nslookup -type=ns dominio.com      # servidores DNS
  dig +short -t AXFR dominio.com @ns1.dns.com   # prueba de transferencia de zona
  whois dominio.com
  ```
- **dnsrecon** — Enumeración DNS y fuerza bruta de subdominios. <https://github.com/darkoperator/dnsrecon>
  ```bash
  dnsrecon -d dominio.com -t brt -D /usr/share/seclists/Discovery/DNS/subdomains-top1million-5000.txt
  ```
- **Fierce** — Escáner DNS para localizar hosts/subdominios. <https://github.com/mschwager/fierce>

### Correos y cuentas
- **theHarvester** — Correos, subdominios y hosts de un dominio. <https://github.com/laramies/theHarvester>
  ```bash
  theHarvester -d dominio.com -b all -l 500 -f salida
  theHarvester -d dominio.com -b hunter -l 500    # con fuentes concretas
  ```
- **h8mail** — Busca correos en filtraciones. <https://github.com/khast3x/h8mail>
  ```bash
  h8mail --gen-config                 # genera config (token de hunter.io)
  h8mail -t correos.txt -c h8mail_config.ini
  ```
- **holehe** — Servicios donde está registrado un correo. <https://github.com/megadose/holehe>
- **ignorant** — Equivalente a holehe para números de teléfono. <https://github.com/megadose/ignorant>

### Diccionarios / wordlists
- **SecLists** — Colección de diccionarios (DNS, usuarios, contraseñas…). <https://github.com/danielmiessler/SecLists>
- **dnspop** — Listas de subdominios más comunes. <https://github.com/bitquark/dnspop>

### Automatización
- **SpiderFoot** — Framework de OSINT automatizado multi-fuente con interfaz web. <https://github.com/smicallef/spiderfoot>

### Todo en uno
- **Mr.Holmes** - <https://github.com/Lucksi/Mr.Holmes>
```bash
  git clone https://github.com/Lucksi/Mr.Holmes
  cd Mr.Holmes
  sudo apt-get update
  sudo chmod +x install.sh
  sudo bash install.sh
```
