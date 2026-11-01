# Metadatos
## Herramientas web

- **Exif Viewer** — Visor de metadatos EXIF de imágenes online. <http://exif-viewer.com/>
- **ExifData** — Visor de metadatos EXIF online. <http://exifdata.com/>

## Herramientas de terminal / escritorio

- **ExifTool** — Lectura/edición de metadatos de casi cualquier archivo. <https://exiftool.org/>
  ```bash
  exiftool imagen.jpg                 # todos los metadatos
  exiftool -r carpeta/                # recursivo sobre una carpeta
  exiftool -r -T -Creator -Producer carpeta/ | sort | uniq -c | sort -rn   # software
  exiftool -r -T -Author -"Last Modified By" carpeta/ | sort | uniq        # usuarios
  ```
- **MetaDetective** — Scraping de documentos de una web y análisis de metadatos. <https://github.com/franckferman/MetaDetective>
  ```bash
  python3 MetaDetective.py --scraping --scan --url https://sitio/ --extensions pdf doc docx odt
  ```
- **Metagoofil** — Descarga documentos públicos de un dominio y extrae metadatos. <https://github.com/opsdisk/metagoofil>
- **FOCA** — Análisis de metadatos de documentos (escritorio, Windows). <https://github.com/ElevenPaths/FOCA>
