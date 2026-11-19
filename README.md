# 🎵 LRCLIB Explorer

Buscador de letras de canciones, **con letras sincronizadas (LRC)**, sobre la API abierta de [LRCLIB](https://lrclib.net). Sin registro ni API key.

**▶ En vivo:** https://jpm70.github.io/lyricexplorer/

Parte del proyecto [Un Fantasma en el Sistema](https://www.unfantasmaenelsistema.com).

## Modos
| Modo | Endpoint | Para qué |
|---|---|---|
| **Buscar** | `/api/search` | Búsqueda general por título, artista o álbum |
| **Obtener exacto** | `/api/get` | Identificar una canción con título, artista, álbum y duración (si no está en la base interna, LRCLIB la busca en fuentes externas) |
| **Caché** | `/api/get-cached` | Consulta rápida solo en la base interna |

Cada resultado abre la letra en dos pestañas: **sincronizada** (con marca de tiempo por línea) y **texto plano**. También indica si la pista es instrumental.

## Notas de uso
- En *Obtener exacto* y *Caché* los cuatro campos son obligatorios y la duración va en **segundos**; LRCLIB admite unos ±2 s de diferencia.
- En *Buscar*, si rellenas título y además artista o álbum, se filtra por ambos; con solo el artista o el álbum se hace una búsqueda general por ese texto.

## Desarrollo local
Es un único `index.html` estático que llama a `https://lrclib.net/api` desde el navegador:

```bash
python -m http.server 8000
```

## Créditos
Datos y API de [LRCLIB](https://lrclib.net). Las letras pertenecen a sus autores; esta página solo las muestra tal como las devuelve la API. Proyecto educativo y sin ánimo de lucro.
