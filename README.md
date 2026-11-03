# Cordobeses-en-Alerta-Exposici-n-2

Exposición «División de Frecuencia» en su versión corta, de la Dirección Monitoreo Cordobeses en Alerta (Policía de la Provincia de Córdoba): las 8 frecuencias RugGear según la UT y cómo figuran en el RugGear. No incluye las funciones de cabina y radio, la medición de tiempos ni los ejemplos de carga en el SAE WEB; esa es la versión completa, en el repositorio `exposicion-division-de-frecuencia`.

Publicada en https://cordobeses-en-alerta-exposicion-2.vercel.app (la guía del público está en `/guia.html`).

Abrí `index.html` en el navegador. Se avanza con ← → (o deslizando en pantallas táctiles) y la tecla F pone la pantalla completa. En celulares las láminas pasan a ser una página con scroll y las animaciones arrancan solas al llegar a cada una.

## Láminas

1. Portada (con el QR de la guía)
2. División de frecuencia (mapa animado de los 234 barrios)
3. RugGear: cómo figuran las frecuencias
4. ¡Muchas gracias! (descarga del PDF)

## Contenido

| Archivo | Qué es |
|---|---|
| `index.html` | La presentación del expositor, con el QR de la portada y el emisor de la guía en vivo. |
| `guia.html` | La guía del público para el celular: una tarjeta conceptual por lámina que sigue al expositor. |
| `config-vivo.js` | Supabase y las claves de la guía en vivo. Esta versión usa su propio canal (`dmca-division-frecuencia-carga`, definido en `index.html` y `guia.html`). |
| `Division de Frecuencia - Frecuencias RugGear.pdf` | El material para descargar (2 hojas). |
| `print/material.html` | El HTML del que sale el PDF, con sus imágenes en `print/img/`. |
| `print/afiche-qr.html` | El afiche A4 en blanco y negro con el QR de la guía, que da `print/afiche-qr-bn.pdf`. |
| `media/`, `vendor/` | Mapa de barrios, RugGear, logo, foto de la portada, Supabase JS y qrcode-generator. |


## Guía en vivo

- Quien expone toca **Activar guía en vivo** (o la tecla G) y escribe la contraseña **Cordobeses**. Queda guardada en esa computadora.
- Cada cambio de lámina y de paso se manda por Supabase Realtime firmado con ECDSA P-256; la guía solo acepta mensajes firmados. La clave sin cifrar vive en `_privado/`, que no se versiona ni se publica.
- `VER` tiene que ser igual en `index.html` y `guia.html`; hay que subirla si cambian las láminas.
- El proyecto de Supabase (plan gratis) se pausa tras unos 7 días sin uso: reactivarlo antes de exponer.

Las piezas reutilizables están documentadas en el `REUTILIZAR.md` de la versión completa.

## Publicar

```bash
vercel deploy --prod --yes
```
