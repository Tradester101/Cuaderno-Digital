# 📓 Cuaderno Digital v3 — Primaria

Cuaderno digital para niños de 2do a 6to grado. Practican operaciones en hoja cuadriculada, lógica y lengua por rondas cortas. Al completar cada ronda se desbloquea un video educativo aprobado por los padres.

Es una sola página web (HTML + CSS + JavaScript puro). No usa frameworks ni librerías y funciona sin internet, salvo los videos.

## Módulos (11)

| Área | Módulos |
|---|---|
| 📐 Cuaderno | Sumas con llevadas · Restas con préstamo · Multiplicación de 1 y 2 cifras (con parciales) · **División larga 100 % manual** (formato de galera latinoamericano: cociente → multiplicar → restar → bajar cifra) |
| 🧩 Lógica | Valor posicional · Redondeo (con recta numérica) · Propiedades conmutativa y asociativa |
| 📖 Lengua | Lectura comprensiva (10 textos) · Ortografía de letras confusas (b/d, p/q, s/z/c, v/b) · Entrenador visual 5×5 |

## Funciones

- **Ronda mixta**: intercala matemáticas y lengua (3, 5, 7 o 10 ejercicios por ronda).
- **Pausa de video**: al terminar la ronda se reproduce un video de YouTube de la lista permitida, con temporizador de descanso.
- **Cronómetro de estudio** configurable.
- **Pistas pedagógicas** que guían sin dar la respuesta.
- **Modo Padres** con PIN (por defecto `1234`): estadísticas por módulo, gestión de videos y ajustes de edad, grado, tiempos y tamaño de ronda.
- **Instalable como app (PWA)**: en Android, Chrome → menú → *Agregar a pantalla principal*.
- Todo el progreso se guarda en el dispositivo (`localStorage`). No hay cuentas ni servidor.

## Estructura

```
index.html             La app completa
manifest.json          Datos para instalarla como app
sw.js                  Service worker (uso sin internet)
icon.svg / icon-*.png  Íconos
vercel.json            Encabezados para Vercel
```

## Ejecutar en local

```bash
npx serve .
# o
python3 -m http.server 8000
```

Luego abre `http://localhost:8000`. El service worker solo se activa en `localhost` o bajo HTTPS.

## Despliegue en Vercel

Es un sitio estático, así que no necesita build:

1. En Vercel: **Add New → Project** e importa este repositorio.
2. Framework Preset: **Other**. Build Command y Output Directory se dejan vacíos.
3. **Deploy**.

Cada push a `main` publica una versión nueva automáticamente.

> Si cambias los íconos o el manifest, sube `CACHE_VERSION` en `sw.js` para que los dispositivos ya instalados descarguen la versión nueva.
