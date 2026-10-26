# Instrucciones del portafolio

Todo se hace desde el navegador, sin instalar nada. Hay dos partes:

- **Parte A – Configuración inicial** (se hace una sola vez, unos 30 minutos).
- **Parte B – Uso diario**: cómo agregar proyectos, fotos y videos.

> **Privacidad:** en el sitio solo van tu nombre y tus proyectos. Nunca pongas
> dirección, teléfono, colegio, horarios ni fotos donde se vea tu casa por fuera.
> Si quieres un correo de contacto, crea uno solo para el portafolio.

---

## Parte A – Configuración inicial

### A1. Crear la cuenta y el repositorio

1. Crea una cuenta en [github.com](https://github.com). El nombre de usuario
   formará parte de la dirección del sitio, así que elige uno profesional
   (por ejemplo `nombre-apellido`).
2. Arriba a la derecha, pulsa **+ → New repository**.
3. En *Repository name* escribe exactamente: `TU-USUARIO.github.io`
   (con tu usuario real).
4. Márcalo como **Public** y pulsa **Create repository**.

### A2. Subir la plantilla

1. Descomprime el archivo `portafolio.zip` en tu computadora.
2. En el repositorio recién creado, pulsa **uploading an existing file**.
3. Arrastra **el contenido** de la carpeta (no la carpeta misma): los archivos
   y las carpetas `_layouts`, `_proyectos`, `assets`, etc.
   *Truco:* en Windows o Mac, abre la carpeta, selecciona todo (Ctrl+A / Cmd+A)
   y arrástralo.
4. Abajo, pulsa **Commit changes**.

### A3. Activar GitHub Pages

1. En el repositorio, ve a **Settings → Pages**.
2. En *Source* elige **Deploy from a branch**; en *Branch* elige `main` y `/ (root)`.
3. Pulsa **Save**. En 1 o 2 minutos el sitio estará en
   `https://TU-USUARIO.github.io`.

### A4. Poner tus datos

1. Abre el archivo `_config.yml` y pulsa el lápiz ✏️ (editar).
2. Cambia `nombre`, `lema`, `sobre_mi`, `github` y las `habilidades`.
3. Pulsa **Commit changes**. Espera un minuto y recarga el sitio.

### A5. Conectar el dominio propio (opcional, unos 10 a 12 dólares al año)

1. Compra el dominio en **Cloudflare Registrar** o **Porkbun** (precio de costo,
   sin trucos de renovación). Un `.com` con el nombre suele ser lo mejor.
2. En el panel DNS del proveedor, crea estos registros:

   | Tipo | Nombre | Valor |
   |---|---|---|
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |
   | CNAME | www | TU-USUARIO.github.io |

   *En Cloudflare, deja la nube en gris ("DNS only") en estos registros.*
3. En GitHub: **Settings → Pages → Custom domain**, escribe `www.tudominio.com`
   y pulsa **Save**. GitHub crea solo un archivo `CNAME`; no lo borres.
4. Cuando la verificación quede en verde (puede tardar desde minutos hasta
   un día), marca **Enforce HTTPS**.
5. Recomendado: en tu perfil de GitHub, **Settings → Pages → Add a domain**,
   verifica el dominio para que nadie más pueda usarlo.

---

## Parte B – Uso diario

### B1. Agregar un proyecto nuevo

1. Abre la carpeta `_proyectos`, pulsa **Add file → Create new file**.
2. Nombre del archivo: corto, en minúsculas, sin espacios ni acentos y
   terminado en `.md`. Ejemplo: `seguidor-de-linea.md`.
   (Ese nombre será la dirección: `/proyectos/seguidor-de-linea/`.)
3. Abre `PLANTILLA-PROYECTO.md`, copia todo su contenido y pégalo en el archivo nuevo.
4. Llena los datos de arriba (entre las líneas `---`) y escribe las secciones.
5. Pulsa **Commit changes**. En 1 o 2 minutos aparece en la página principal.

> **Importante:** el bloque entre las dos líneas `---` debe conservar el formato:
> `campo: "valor"`. Si el sitio deja de actualizarse, casi siempre es una comilla
> o unos dos puntos que faltan ahí. Revisa la pestaña **Actions** del repositorio:
> si hay una ✗ roja, ábrela y verás en qué línea está el error.

### B2. Subir fotos

1. Ve a `assets/img/proyectos/` y pulsa **Add file → Upload files**.
2. Para crear una carpeta para el proyecto, en lugar de subir, usa
   **Create new file** y escribe `seguidor-de-linea/.gitkeep` (la barra `/`
   crea la carpeta). Después sube las fotos ahí.
3. Usa nombres sin espacios: `portada.jpg`, `cableado.jpg`, `prueba-1.jpg`.
4. Antes de subir, reduce las fotos del celular a unos 1600 px de ancho
   (por ejemplo con [squoosh.app](https://squoosh.app)) para que el sitio cargue rápido.
5. Para mostrar una foto dentro del texto:

   ```markdown
   ![Descripción corta](/assets/img/proyectos/seguidor-de-linea/cableado.jpg)
   *Pie de foto opcional en cursiva.*
   ```

6. Para la foto de la tarjeta, pon su ruta en `imagen:` en los datos de arriba.

### B3. Agregar un video de YouTube

1. Sube el video a YouTube. Si no quieres que aparezca en búsquedas,
   elige visibilidad **No listado**.
2. Copia el código del enlace: en `https://www.youtube.com/watch?v=AbC123xYz`
   el código es `AbC123xYz` (en enlaces `youtu.be/AbC123xYz`, es lo que va
   después de la barra).
3. Ponlo en los datos del proyecto: `video: "AbC123xYz"`. El video aparece solo.

### B4. Enlazar el código

Crea un repositorio aparte por cada proyecto (por ejemplo `brazo-robotico`)
con su código y un `README.md` corto. Luego pon su enlace en
`codigo: "https://github.com/TU-USUARIO/brazo-robotico"`.

### B5. Formato básico de Markdown

| Escribes | Se ve |
|---|---|
| `## Título` | Título de sección |
| `**negrita**` | **negrita** |
| `*cursiva*` | *cursiva* |
| `- elemento` | Lista con viñetas |
| `1. paso` | Lista numerada |
| `[texto](https://enlace.com)` | Enlace |
| `` `código` `` | `código` |

Para ver cómo queda antes de guardar, usa la pestaña **Preview** del editor
de GitHub. (Las fotos y el video solo se ven ya publicados.)

---

## Consejos para un buen portafolio

- **Documenta desde el primer día**: toma fotos de cada paso, aunque algo salga mal.
  Los errores y cómo los resolviste son lo más valioso.
- Es mejor tener 3 proyectos bien explicados que 10 a medias.
- Algunas universidades (MIT, por ejemplo) aceptan un *Maker Portfolio*
  junto con la solicitud; este sitio te sirve de base.
- Para cambiar el color del sitio, edita `--acento` en `assets/css/style.css`.
- El sitio abre en modo oscuro. Para cambiarlo, edita `tema:` en `_config.yml`
  (`"oscuro"`, `"claro"` o `"automatico"`). Los visitantes también pueden
  cambiarlo con el botón de tema (el círculo mitad lleno) y el sitio recuerda su elección.
- Para borrar el proyecto de ejemplo, abre `_proyectos/brazo-robotico.md`,
  menú **···** → **Delete file**.
