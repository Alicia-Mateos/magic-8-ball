# Bola Mágica 8

App web estática (HTML/CSS/JS) estilo “Magic 8 Ball” para hacer una pregunta y obtener una respuesta aleatoria.

## Accesibilidad (WCAG)

Incluye mejoras orientadas a WCAG 2.1/2.2:

- **Estructura y semántica**: `lang="es"`, uso de `main` y `h1`, botón real (`<button>`) para la bola.
- **Navegación por teclado**: enlace “Saltar al contenido principal”.
- **Foco visible**:
  - Ring visible para navegación con teclado.
  - El `input` **solo** muestra ring al navegar con `Tab` (evita ring al hacer click para escribir).
- **Anuncios para lector de pantalla**: región viva que anuncia errores (pregunta vacía) y respuestas.
- **Motion**: respeta `prefers-reduced-motion`.
- **Zoom/Reflow**: no se bloquea el zoom del navegador y se permite scroll al ampliar.

## Cómo usar (local)

No necesitas instalar nada.

### Opción A: abrir el archivo

Abre `index.html` en tu navegador.

### Opción B (recomendado): servidor local

Con Python:

```bash
python3 -m http.server 5173
```

Luego abre `http://localhost:5173`.

## Cómo usar la app

- Escribe una pregunta de **sí/no** en el campo.
- Pulsa la bola (click) o con teclado:
  - Tab hasta la bola, luego `Enter` o `Espacio`.
- Si estás en móvil y das permiso, también puedes agitar el dispositivo.

## Despliegue en Vercel

Esta app es **estática**, así que Vercel la despliega sin build.

### Desde GitHub (recomendado)

1. Sube el proyecto a GitHub.
2. En Vercel, **New Project** → importa el repositorio.
3. Configuración:
   - **Framework Preset**: “Other”
   - **Build Command**: vacío
   - **Output Directory**: `.` (raíz)
4. Deploy.

### Alternativa: Vercel CLI

```bash
npm i -g vercel
vercel
```

Cuando pregunte:
- **Framework**: Other
- **Build**: No
- **Output**: `.`

## Test rápido de accesibilidad (manual)

- **Teclado**: `Tab` → “Saltar al contenido” → input → bola; activar con `Enter/Espacio`.
- **Zoom**: 200–400% sin perder contenido; con scroll si hace falta.
- **Lector de pantalla**: el error de “pregunta vacía” y la “Respuesta: …” deben anunciarse.

