# Catálogo CasaYourte

Sitio estático, sin dependencias ni build. Tres piezas:

```
index.html        el catálogo (diseño + textos por defecto + editor)
contenido.json    los textos en español y francés, y el alt de cada imagen
img/              17 fotos, nombradas por su lugar en la página
video/            banner.mp4 (loop del encabezado) y banner.jpg (imagen de respaldo)
proceso/          p01.jpg a p12.jpg, los doce momentos de la obra en orden
img/logo.png      el logo, trazo blanco sobre fondo transparente
```

## Publicar en GitHub Pages

1. Crear un repositorio nuevo. Tiene que ser **público** si la cuenta es gratuita.
2. Subir a la raíz: `index.html`, `contenido.json` y la carpeta `img/`.
3. En el repositorio: **Settings → Pages**.
4. En *Source* elegir **Deploy from a branch**, rama `main`, carpeta `/ (root)`. Guardar.
5. En dos o tres minutos el sitio queda en `https://<usuario>.github.io/<repositorio>/`

Ese es el link para compartir.

## Cómo colabora otra persona (por ejemplo Florencia)

Ella no necesita cuenta de GitHub, ni permisos, ni saber qué es un repositorio.
Trabaja sobre el link publicado y te manda los archivos. Vos los registrás.

1. Abre el link y aprieta **Editar** en la barra de abajo.
2. Cambia los textos que quiera haciendo clic encima. Para cambiar una foto usa
   **Cambiar imagen** sobre la imagen misma.
3. Ve todos sus cambios aplicados en pantalla, como van a quedar.
4. Aprieta **Preparar envío**. El contador al lado del botón le dice cuántos cambios
   tiene pendientes.
5. Se le descargan solamente los archivos que cambió: `contenido.json` si tocó
   textos, y las imágenes nuevas ya con el nombre correcto (`hero.jpg`, `int1.jpg`…).
6. Se abre un cartel con la lista y dos botones: avisarte por WhatsApp o abrir el mail,
   con el mensaje ya escrito. Ella adjunta los archivos y listo.

**Lo que hacés vos al recibirlos:** reemplazar `contenido.json` en el repositorio, y
poner cada imagen en `img/` sobre la que tenía el mismo nombre. Nada más.
El sitio se actualiza en un minuto.

Los cambios de ella nunca se publican solos. Nadie más que vos escribe en el sitio.

## Editar vos mismo

Igual que arriba, o directo: abrir `contenido.json` en GitHub, apretar el lápiz,
cambiar el texto y confirmar. Sirve bien para correcciones de una línea.

Aviso: se edita **el idioma que se está viendo**. Para cambiar el francés hay que
pasar a *Français* primero.

## Los nombres de las imágenes

`hero` · `traj1` a `traj5` · `dif1` a `dif8` · `int1` a `int3` · `co` · `ws`

El botón **Todas las imágenes** descarga las 17 con el nombre correcto, por si hace
falta reconstruir la carpeta.

## El video del encabezado

`video/banner.mp4` son 14 segundos sin audio, en loop, tomados del corto nocturno del
skydome iluminado. Está armado como palíndromo — va y vuelve — para que el ciclo de
color no dé un salto al reiniciar. Pesa 730 KB.

No se cambia desde el editor: es un archivo. Para reemplazarlo hay que subir el nuevo
con el mismo nombre, `video/banner.mp4`, y una imagen de respaldo `video/banner.jpg`
del mismo tamaño.

`banner.jpg` se muestra mientras el video carga, y también a quien tenga activada la
opción de reducir animaciones en su sistema.

## El cuadro del proceso

Doce fotogramas sacados del video de obra, en orden de construcción: taller, plancher,
trei, anillo periférico, toono, lonas, techo, doble techo, piezas curvas, equipo,
interior y yurta habitada. **912 KB en total**, y se cargan de a uno según avanza —
nunca las doce juntas.

Avanza solo cada 3,2 segundos, pero únicamente mientras está en pantalla: si el
visitante está leyendo otra parte, se detiene y no gasta datos. Tiene flechas, pausa,
y las doce marcas de abajo son clickeables.

Los textos de cada fotograma son las claves `pr.c1` a `pr.c12` en `contenido.json`,
en los dos idiomas. Se editan como cualquier otro texto.

Para cambiar un fotograma: subir la imagen nueva como `proceso/pNN.jpg` con el mismo
número. Conviene mantener la proporción 16:9.

## El logo

`img/logo.png` es el dibujo del techo en planta con @CasaYourte en el centro, sacado
del video y limpiado: trazo blanco sobre fondo transparente, para que funcione sobre
el encabezado oscuro. Aparece arriba a la izquierda y en el pie.

Si tenés el archivo original del logo en vector, conviene reemplazarlo: un SVG se ve
nítido en cualquier tamaño y pesa una fracción. El PNG actual pesa 70 KB y está
reconstruido de un fotograma, no del original.

## Antes de publicar

- [ ] Completar los precios de la tabla, hoy dicen "a consultar"
- [ ] Confirmar o quitar la fila de dirección del taller
- [ ] Escribir el texto alternativo de cada imagen en modo edición
- [ ] Revisar el francés: está traducido, no corregido por un nativo

Contacto ya configurado: WhatsApp +598 99 696 333 y casayourte@gmail.com,
los dos como enlaces directos.

## No subir a este repositorio

El **documento de enfoque** (`enfoque-yurtour.html`) no va acá. Contiene costos,
márgenes, tarifa horaria y estrategia. Es material interno y el repositorio es público.

## Protocolo de correcciones

Cada entrega de cambios llega como **un solo zip que contiene únicamente los
archivos modificados**, con la estructura de carpetas del repositorio y un
`CAMBIOS.md` adentro que dice qué toca y por qué.

Para aplicar: copiar el contenido del zip sobre la raíz del repositorio. Nada más.

Si hay imágenes modificadas, vienen ya dentro de `img/`, `proceso/` o `video/`
con el nombre exacto que reemplazan, así que no hay que decidir dónde va cada una.
`CAMBIOS.md` siempre las lista.

## Notas técnicas

Abrir `index.html` con doble clic funciona, pero el navegador bloquea la lectura de
`contenido.json` por seguridad. En ese caso se usan los textos incluidos dentro del
propio `index.html`. Servido por http, o publicado en Pages, lee el JSON normalmente.

Las fotos pesan 3 MB en total. GitHub Pages recomienda hasta 1 GB de sitio.

Si más adelante querés un panel de administración con guardado real desde el
navegador, este mismo `contenido.json` es el formato que consume Decap CMS.
