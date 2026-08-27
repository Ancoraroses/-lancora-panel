# L'Àncora — Panel de Tesorería

Landing estática que visualiza categorías de gasto recurrente y semáforos,
generada a partir de Era + extractos bancarios. No necesita servidor: es
HTML puro que lee `data.json`.

## Publicarlo en 5 minutos (sin necesidad de dar ningún token a Claude)

1. Ve a **github.com/new** y crea un repositorio nuevo.
   - Nombre sugerido: `lancora-panel`
   - Puede ser público o privado (si es privado, GitHub Pages requiere
     plan de pago para servirlo; si no quieres pagar, hazlo público —
     no hay datos personales sensibles, solo importes agregados).
   - No marques "Add a README" (ya tienes uno).

2. En la página del repo recién creado, verás un enlace
   **"uploading an existing file"**. Haz clic y arrastra los 3 archivos
   de esta carpeta (`index.html`, `data.json`, `README.md`). Confirma
   el commit ("Commit changes").

3. Ve a **Settings → Pages** (menú lateral izquierdo).
   - En "Source", elige **Deploy from a branch**.
   - Branch: **main**, carpeta: **/ (root)**. Guarda.
   - En 1-2 minutos GitHub te da una URL tipo
     `https://TU-USUARIO.github.io/lancora-panel/`

4. Abre esa URL — ya tienes el panel visible desde cualquier dispositivo.

## Cómo se actualiza

Cada vez que hablemos y actualice los datos (Era, categorías, saldos),
te doy un `data.json` nuevo. Solo tienes que:
1. Ir al repo en github.com
2. Clic en `data.json` → icono de lápiz (editar) → pegar el contenido
   nuevo → "Commit changes"
3. La landing se actualiza sola en unos segundos (no hay que tocar
   `index.html`).

Si en algún momento prefieres que yo suba los cambios directamente
(sin que tengas que copiar/pegar), puedes darme un **token de acceso
personal (fine-grained, con permiso limitado solo a este repo)** desde
GitHub → Settings → Developer settings → Personal access tokens.
No es obligatorio — el flujo manual de arriba funciona perfectamente
y no expone ninguna credencial.

## Estructura de `data.json`

```json
{
  "actualizado": "2026-08-27",
  "cobertura": "01/09/2025 – 26/08/2026",
  "tesoreria": { "bbva": 25182.86, "caixa": 4166.29, "bbvaNominas": 7435.42 },
  "categorias": [
    { "categoria": "...", "total": 0, "mediaMensual": 0, "mesesActivo": 12,
      "semaforo": "verde|ambar|rojo|sin-datos", "meses": [12 valores] }
  ]
}
```
