# Simulador UNISEINS-PNP — versión app para Android

Esta carpeta contiene tu simulador convertido en **PWA** (app web instalable): mismo
banco de 1,500 preguntas, pero ahora con ícono, se puede instalar en el celular y
funciona sin internet una vez instalada.

Archivos:
- `index.html` — el simulador completo (idéntico al que ya tenías, con las mejoras de PWA).
- `manifest.json` — la "ficha de identidad" de la app (nombre, ícono, colores).
- `service-worker.js` — permite que funcione sin internet.
- `icons/` — los íconos generados a partir de tu logo.

**No abras `index.html` haciendo doble clic para esto** — para que Android la reconozca
como app instalable, tiene que estar en una dirección web (https://...), no en tu PC.

---

## Paso 1 — Subir la carpeta a GitHub Pages (gratis)

1. Crea una cuenta gratis en https://github.com (si no tienes una).
2. Arriba a la derecha, clic en el "+" → "New repository".
   - Nombre: `simulador-pnp` (o el que prefieras).
   - Marca "Public". Clic en "Create repository".
3. En la página del repositorio, clic en "uploading an existing file".
4. Arrastra **todo el contenido de esta carpeta** (index.html, manifest.json,
   service-worker.js, y la carpeta icons completa). Clic en "Commit changes".
5. Ve a la pestaña **Settings** del repositorio → en el menú izquierdo, **Pages**.
6. En "Branch", elige `main` y carpeta `/ (root)`. Clic en **Save**.
7. Espera 1-2 minutos. GitHub te mostrará tu URL, algo como:
   `https://tu-usuario.github.io/simulador-pnp/`
8. Abre esa URL en el celular (Chrome) — ya deberías poder instalarla con
   "Agregar a pantalla de inicio".

## Paso 2 — Generar el APK con PWABuilder

1. Entra a **https://www.pwabuilder.com** desde tu PC.
2. Pega la URL de GitHub Pages del paso 1 y presiona "Start".
3. Espera a que analice tu app (revisa que el manifest e ícono se detecten bien,
   deberían salir en verde).
4. Clic en **"Package for stores"** → elige **Android**.
5. Deja las opciones por defecto y genera el paquete. Descarga el `.zip`.
6. Dentro del `.zip` vas a encontrar un archivo `.apk` (para instalar directo)
   y un `.aab` (solo necesario si algún día publicas en Play Store).

## Paso 3 — Instalar el APK en tu celular

1. Pasa el archivo `.apk` a tu teléfono (cable USB, WhatsApp, Google Drive, etc.).
2. Ábrelo desde el celular. Si Android bloquea la instalación, ve a
   Ajustes → Seguridad → permite "Instalar apps desconocidas" para la app que
   uses para abrirlo (Archivos, Chrome, etc.), solo para esta instalación.
3. Instala. Ya tienes el ícono del simulador en tu pantalla de inicio, como
   cualquier otra app — funciona sin internet.

---

### Actualizaciones futuras

Cada vez que quieras una nueva versión (más preguntas, cambios de diseño, etc.),
solo reemplaza `index.html` en GitHub (Paso 1.4) y quienes ya instalaron la app
recibirán la actualización automáticamente la próxima vez que abran con internet.
Si generas un APK nuevo para repartir de cero, repite el Paso 2.
