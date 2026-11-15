[README.md](https://github.com/user-attachments/files/34881699/README.md)
# Conciencia Digital

Página web educativa sobre fraude digital: engaños en redes sociales y mensajería,
ingeniería social y el papel de la IA en los ataques y en la defensa.

Estática, sin dependencias, sin rastreadores y sin build. Solo HTML, CSS y JavaScript.

## Contenido

- **Anatomía del engaño** — las seis palancas psicológicas y la regla de las tres preguntas.
- **Simulador** — ocho mensajes ficticios (estafa o legítimo) con señales razonadas.
- **Test** — diez preguntas con explicación inmediata y puntuación final.
- **IA** — qué automatiza la IA en manos de un estafador y qué puede hacer por ti.
- **Checklist** — diecisiete medidas con progreso guardado en `localStorage`.
- **Plan de choque** — qué hacer en la primera hora si ya has caído.
- **Recursos** — INCIBE (017), CCN-CERT, AEPD, OSI.

## Estructura

```
.
├── index.html
├── assets/
│   ├── css/styles.css
│   ├── js/
│   │   ├── app.js          # tema, menú, progreso de lectura, animaciones
│   │   ├── simulator.js    # simulador de phishing
│   │   ├── quiz.js         # test de autoevaluación
│   │   └── checklist.js    # checklist con persistencia local
│   └── favicon.svg
├── .nojekyll
└── README.md
```

## Ver en local

Basta con abrir `index.html` en el navegador. Si prefieres servirlo por HTTP:

```bash
python3 -m http.server 8000
# http://localhost:8000
```

## Publicar en GitHub Pages

1. Crea un repositorio vacío llamado `ciberseguridad` (sin README ni licencia).
2. Desde esta carpeta:

```bash
git init -b main
git add .
git commit -m "Página inicial: concienciación sobre fraude digital"
git remote add origin https://github.com/TU-USUARIO/ciberseguridad.git
git push -u origin main
```

3. En GitHub: **Settings → Pages → Build and deployment**
   - Source: `Deploy from a branch`
   - Branch: `main` · carpeta `/ (root)`
4. La web quedará en `https://TU-USUARIO.github.io/ciberseguridad/`.

El archivo `.nojekyll` evita que GitHub Pages procese el sitio con Jekyll.

### Con GitHub CLI (alternativa)

```bash
gh repo create ciberseguridad --public --source=. --remote=origin --push
```

## Personalizar

- **Paleta**: variables CSS al inicio de `assets/css/styles.css` (`:root` y `html[data-theme="light"]`).
- **Mensajes del simulador**: array `scenarios` en `assets/js/simulator.js`.
- **Preguntas del test**: array `questions` en `assets/js/quiz.js`.
- **Checklist**: bloques `<fieldset>` en `index.html`; cada ítem necesita un `data-check` único.
- **Recursos**: sección `#recursos` de `index.html`.

## Accesibilidad y privacidad

- Navegación por teclado, `skip link`, estados `aria-*` y foco visible.
- Respeta `prefers-reduced-motion` y `prefers-color-scheme`.
- Sin cookies, sin analítica, sin peticiones externas. El progreso del checklist nunca sale del navegador.

## Aviso

Material educativo independiente. Los nombres, dominios y números de los ejemplos son ficticios.
No sustituye el asesoramiento de tu banco, de un profesional legal ni de las autoridades.
