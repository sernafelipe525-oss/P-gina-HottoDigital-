# Web de Luis Felipe Serna

Web de consultoría con asistente de IA integrado para agendar valoraciones
(por videollamada o presencial en Madrid).

## Archivos

- `index.html` — la web pública. El asistente ya está incrustado dentro de
  este mismo archivo (widget de chat flotante, sin dependencias externas).
  Los 3 botones "Agenda tu valoración" abren el chat directamente.
- `panel-valoraciones.html` — panel privado para ver y gestionar las citas
  agendadas por el asistente, y editar horario/dirección/duración de la
  valoración. Clave de acceso: `valoracion2026`.

## Backend

El asistente llama a un backend que vive en un repositorio aparte
(`hottodigital-assistant`, desplegado en Railway junto con el asistente
de Hotto), en el endpoint:

```
https://buss-production.up.railway.app/api/chat-valoraciones
```

Si ese backend cambia de URL, hay que actualizar la constante `API_URL`
dentro del `<script>` al final de `index.html`.

## Publicar esta web

Para que quede accesible con una URL propia, sube este repo a GitHub y
activa **GitHub Pages**:

1. Sube `index.html` y `panel-valoraciones.html` a un repositorio nuevo.
2. Repositorio → **Settings → Pages**.
3. En "Source", selecciona la rama principal (main) y carpeta `/ (root)`.
4. Guarda. GitHub te dará una URL tipo
   `https://tu-usuario.github.io/nombre-repo/`.

El panel quedaría accesible en
`https://tu-usuario.github.io/nombre-repo/panel-valoraciones.html`
(no lo enlaces desde la web pública, solo úsalo tú directamente).
