# Café de Amanda — página web

Sitio de una sola página, sin frameworks, sin base de datos y sin costos mensuales.
Se puede publicar gratis en GitHub Pages (o en Cloudflare Pages / Netlify).

```
web/
├── index.html                 ← todo el contenido y los textos
├── styles.css                 ← colores, tipografía, diseño
├── script.js                  ← menú móvil y animaciones
├── libro-de-reclamaciones.html ← formato imprimible (Ley 29571)
└── assets/img/                ← logo y fotos de los platos
```

## Verla en tu compu

Doble clic en `web/index.html`. Se abre en el navegador y funciona completa
(el mapa necesita internet).

## Publicarla gratis en GitHub Pages

### Opción A — desde la web de GitHub (sin instalar nada)

1. Crea una cuenta en <https://github.com> (gratis).
2. Crea un repositorio nuevo llamado `cafe-de-amanda`, **público**.
3. Dentro del repo: **Add file → Upload files** y arrastra **el contenido**
   de la carpeta `web/` (no la carpeta, sino `index.html`, `styles.css`,
   `script.js`, la carpeta `assets` y el libro de reclamaciones).
4. **Commit changes**.
5. Ve a **Settings → Pages**.
6. En *Build and deployment* elige **Deploy from a branch**, rama `main`,
   carpeta `/ (root)`. Guarda.
7. Espera 1–2 minutos. Tu dirección será:

   ```
   https://TU-USUARIO.github.io/cafe-de-amanda/
   ```

Esa URL es gratis y para siempre. Se puede acortar o cambiar de dominio
después sin rehacer nada.

### Opción B — con git (si ya lo usas)

```bash
cd web
git init
git add .
git commit -m "Página de Café de Amanda"
git branch -M main
git remote add origin https://github.com/TU-USUARIO/cafe-de-amanda.git
git push -u origin main
```

Luego activa Pages en **Settings → Pages** como en la opción A.

## Alternativa aún más rápida: Cloudflare Pages

<https://pages.cloudflare.com> permite arrastrar la carpeta `web/` y publicar
sin repositorio ni tarjeta. También es gratis. GitHub Pages tiene la ventaja de
que guarda el historial de cambios.

## Dominio propio (opcional)

No hace falta para empezar. Si más adelante quieres `cafedeamanda.pe`:

- El dominio se paga **una vez al año** (aproximadamente S/ 40–100 según la
  terminación), no es una suscripción mensual.
- En GitHub Pages: **Settings → Pages → Custom domain**, y en el proveedor del
  dominio se configuran los DNS que GitHub indica.
- Mientras tanto, la URL `usuario.github.io/cafe-de-amanda` funciona igual.

## Qué editar y dónde

| Quiero cambiar… | Archivo | Buscar |
|---|---|---|
| Nombre, frase de portada | `index.html` | `<h1>` y `.lede` |
| Platos y descripciones | `index.html` | `class="dish"` |
| Dirección, teléfono, correo | `index.html` | `#visitanos` y `<footer>` |
| Número de WhatsApp | `index.html` | `wa.me/51921752732` (aparece 4 veces) |
| Colores | `styles.css` | bloque `:root` |
| Logo y fotos | `assets/img/` | reemplaza el archivo con el mismo nombre |

### Agregar precios a un plato

Dentro de cada `<div class="dish-body">`, después de la descripción:

```html
<p class="dish-price">S/ 14.00</p>
```

Y en `styles.css`:

```css
.dish-price {
  margin-top: 10px;
  font-family: var(--display);
  font-size: 1.05rem;
  color: var(--terra);
}
```

### Cambiar el aviso de "Próxima apertura"

En `index.html`, busca `hero-note`. Cuando abran, cámbialo por el horario real
o bórralo.

## Antes de publicar — pendientes

- [ ] Confirmar que el **921 752 732** tiene WhatsApp (los botones apuntan ahí).
- [ ] Definir **horario de atención** y reemplazar "Abrimos pronto".
- [ ] Poner **precios** en la carta (hoy no se muestran para no inventarlos).
- [ ] Agregar las **bebidas** (café, infusiones, jugos) cuando estén definidas.
- [ ] Actualizar la URL en las etiquetas `og:` cuando la página esté publicada.
- [ ] Revisar la ubicación exacta en Google Maps (el mapa usa la dirección; si
      el pin no cae bien, reemplazar el `src` del iframe por el enlace
      "Insertar un mapa" de Google Maps).
- [ ] **Libro de Reclamaciones**: INDECOPI exige el libro físico en el local.
      El archivo `libro-de-reclamaciones.html` es el formato imprimible; para
      que sea "virtual" debe permitir registrar el reclamo en línea y generar
      una constancia (se puede hacer más adelante con un formulario).
- [ ] Revisar el texto de "Nosotros": está redactado como borrador, ajústalo a
      la historia real de Amanda.

## Costos

| Concepto | Costo |
|---|---|
| Hosting (GitHub Pages) | S/ 0 |
| Certificado HTTPS | S/ 0 (incluido) |
| Diseño y código | S/ 0 (este proyecto) |
| Dominio propio | opcional, ~S/ 40–100 al año |
| **Total para empezar** | **S/ 0** |
