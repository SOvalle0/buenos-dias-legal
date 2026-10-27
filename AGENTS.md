# Trabajar en buenos-dias-legal

Lee primero el [perfil de Sebastián](/Users/sebastian/Projects/Memoria/PERFIL-SEBASTIAN.md) y el [mapa de proyectos](/Users/sebastian/Projects/CLAUDE.md).

Este repo es la web pública de Buenos Días en `buenosdiasapp.com` (GitHub Pages, repo público): la portada y las páginas de privacidad, términos y ayuda. El estado y las decisiones legales están en [Memoria/Buenos Dias/Legal](/Users/sebastian/Projects/Memoria/Buenos%20Dias/Legal/README.md). Cómo debe verse la web y qué hereda de la marca: [Canales/Web](/Users/sebastian/Projects/Memoria/Buenos%20Dias/Marketing/Canales/Web/README.md).

## Qué leer y dónde vive cada cosa

- `index.html` y `assets/`: la portada. Es HTML sin encabezado de Jekyll y con su propio `assets/site.css`, que repite los valores del [sistema de diseño](/Users/sebastian/Projects/Aplicaciones/propias/Mini-apps/BuenosDias-Design-System/tokens/colors.css) que usa. Dos valores se cambian al final del archivo: `STORE_URL` (el enlace del App Store, hoy vacío) y `FORM_URL` (el formulario de la lista; vacío esconde el botón «Quiero probarla»).
- `privacidad.md`, `terminos.md`, `ayuda.md`: páginas con el tema `jekyll-theme-primer` y su ruta pública en `permalink`. Su texto sale de [Memoria/Buenos Dias/Legal](/Users/sebastian/Projects/Memoria/Buenos%20Dias/Legal/README.md): se contrasta con la [política](/Users/sebastian/Projects/Memoria/Buenos%20Dias/Legal/Pol%C3%ADtica%20de%20privacidad.md) y los [términos](/Users/sebastian/Projects/Memoria/Buenos%20Dias/Legal/T%C3%A9rminos%20de%20servicio.md) antes de proponer cambios.
- `_config.yml` y `CNAME`: configuración de Jekyll y dominio. Un cambio en `CNAME` o en el DNS tira la web entera: se avisa antes.

## Límites

- **Sin analítica, píxeles, cookies ni nada cargado de otra empresa** (letras, íconos, scripts). La política de privacidad dice que no se usan. Poner el píxel de Meta obliga a cambiar la política y la ficha de privacidad de Apple, y lo decide Sebastián con Legal.
- **Sin promesas de salud:** la app no diagnostica ni trata. Es para mayores de 18 años. «Gratis» se revisa con Legal si cambia el precio.
- **Texto nuevo que promete algo o habla de datos** lo revisa Legal y privacidad antes de juntarse. No conviertas un borrador en promesa pública.
- **Publicar** es juntar a `main`: cada junta reconstruye el sitio en vivo. Un cambio que espera a Sebastián queda en un PR en borrador, sin juntar.
- Los enlaces del pie van a `/privacidad/`, `/terminos/` y `/ayuda/`, con barra final.

## Cómo comprobar un cambio

No hay script de build ni de pruebas. Desde la carpeta del repo: `cd <ruta del repo> && python3 -m http.server` y abre `http://localhost:8000`. En local solo se ve la portada: las páginas `.md` necesitan Jekyll y salen con su permalink recién en GitHub Pages. Mira la portada en celular y en computador, que no tenga scroll horizontal y que los enlaces del pie y del menú existan.

Después de publicar, comprueba con `curl -I https://buenosdiasapp.com/` y las otras tres rutas que respondan 200 con certificado válido. Si tu Mac aún ve la dirección vieja del dominio, `curl --resolve buenosdiasapp.com:443:185.199.108.153` consulta GitHub directo. Una comprobación de enlaces no valida el contenido jurídico ni confirma que algo esté publicado.

Los mensajes a personas siguen las autorizaciones del perfil.
