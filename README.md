# TikTok Developer — verificación por **URL prefix**

Yo **no puedo** completar la verificación por ti (hace falta tu cuenta TikTok para generar el archivo único). Esto es lo que debes hacer **en orden**.

## 1. Prefijo que vas a usar

Elige ya el prefijo **HTTPS** público donde vivirán Terms, Privacy y el archivo de TikTok.

**Recomendado (GitHub Pages, gratis):**

| Campo | Valor (ejemplo; cámbialo a tu usuario/repo) |
|-------|------------------------------------------------|
| Repositorio | Por ejemplo `tuusuario/openshorts-tiktok-pages` |
| Prefijo para TikTok | `https://tuusuario.github.io/openshorts-tiktok-pages/` |

Importante:

- La barra final **`/`** suele importar: pon en TikTok **exactamente** el mismo prefijo que verás cuando abras la web en el navegador (incluido `http`→`https` y sin puerto).

## 2. Subir esta carpeta a GitHub

1. Crea un repo vacío `tuusuario/openshorts-tiktok-pages`.
2. Copia **todo el contenido** de la carpeta `tiktok-url-prefix-site/` de este proyecto (esta carpeta en el repo) **a la raíz** del nuevo repo (`index.html`, `terms.html`, `privacy.html`, `.nojekyll`, esta `README`).
3. En el repo GitHub → **Settings → Pages** → Source: **Deploy from a branch** → Branch **main**, folder **`/ (root)`** → Save.
4. Espera 1–5 minutos. Abre `https://tuusuario.github.io/openshorts-tiktok-pages/` y comprueba que se ve la página.

## 3. Archivo de firma desde TikTok

El texto “upload to …/index.html/” en TikTok significa **la misma carpeta que tu sitio** (donde está `index.html`), **no** dentro del archivo HTML. El `.txt` va en la **raíz del repo** junto a `index.html`.

Nombre del archivo (ejemplo): `tiktokTx3Ar1zBmQyE3gz42NHKcIeXaex6o2OU.txt` — debe coincidir **exactamente** con el que descargaste (sin “ (1)” que añade macOS). URL de comprobación:

`https://ashutter-media.github.io/autoclipz-tiktok-legal/tiktokTx3Ar1zBmQyE3gz42NHKcIeXaex6o2OU.txt`

En **TikTok for Developers** → tu app → verificación **URL prefix**:

1. Pega el prefijo exacto: `https://tuusuario.github.io/openshorts-tiktok-pages/`
2. TikTok te dará **un nombre de archivo** y **contenido** (o descarga).

Debes subir ese archivo **en la ubicación que indiquen**. Muchas veces es:

- La **raíz del prefijo**, es decir en tu repo junto a `index.html`, con **el mismo nombre** que TikTok muestra.

Si dicen una ruta concreta (por ejemplo bajo `.well-known/`), créala en el repo y súbelo ahí.

```text
openshorts-tiktok-pages/
  index.html
  terms.html
  privacy.html
  tiktok-xxxxx.txt    ← ejemplo; usa el nombre real que te dé TikTok
```

3. Haz commit y push. Espera un minuto y comprueba en el navegador:

`https://tuusuario.github.io/openshorts-tiktok-pages/NOMBRE_EXACTO_DEL_ARCHIVO`

Debe verse el texto/contenido que TikTok espera.

## 4. Confirmar en TikTok

En el portal, botón tipo **Verify**. Si falla: prefijo mal copiado, archivo con otro nombre/ruta o Pages aún sin desplegar.

## 5. URLs para el formulario de la app

Usa estas **después** de que Pages funcione:

| Campo TikTok | URL ejemplo |
|--------------|-------------|
| Privacy Policy URL | `https://tuusuario.github.io/openshorts-tiktok-pages/privacy.html` |
| Terms of Service URL | `https://tuusuario.github.io/openshorts-tiktok-pages/terms.html` |
| Web/Desktop URL | `https://tuusuario.github.io/openshorts-tiktok-pages/` (o `/index.html`) |

---

## Postiz / OAuth redirect

El redirect OAuth de TikTok debe coincidir con lo que registrarás en TikTok Developer **y** lo que soporte tu Postiz (`FRONTEND_URL` etc.). Suele ser tu dominio real de Postiz, **no** esta página estática — esta repo solo sirve para **Terms + Privacy + verificación**, no tiene por qué ser la misma URL donde corre Postiz.

Cuando tengas dominio propio más adelante, puedes migrar estos HTML o redirigir.
