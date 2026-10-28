# Guía Legal Policial · Costa Rica

Aplicación web progresiva (PWA) de consulta rápida sobre facultades, límites y protocolos de actuación policial en Costa Rica, organizada por leyes en pestañas. Funciona sin conexión una vez instalada.

> ⚠️ **Aviso importante**
> Este proyecto es material de consulta y apoyo educativo. **No sustituye** el texto oficial de las leyes, los protocolos y directrices vigentes de su institución, ni la asesoría legal o del Ministerio Público. Varios artículos están marcados como **«verificar»** porque su número exacto debe confirmarse en el [SCIJ](https://www.pgrweb.go.cr/scij/) antes de usarse en servicio.

## Características

- 10 pestañas por norma: Constitución, Ley 8204, VIFA (Ley 7586), Ley 8589, Código Procesal Penal (7594), Ley 7530, Ley 9078, Ley 7451 y reforma 9458, Ley 9028, y otras (Ley 7410, Ley 7576).
- Cada tema muestra: **puede / debe**, **no puede**, **pasos y buenas prácticas** y **base legal**.
- Buscador en tiempo real en todas las secciones (por ejemplo: `flagrancia`, `allanamiento`, `decomiso`).
- Enlace a la fuente oficial al final de cada ley.
- Diseño móvil, con modo claro y oscuro automático.
- Funciona offline mediante *service worker* y caché local.
- Sin dependencias ni librerías externas (HTML, CSS y JavaScript puros).

## Estructura

```
.
├── index.html      # Interfaz, estilos y contenido (arreglo D)
├── sw.js           # Service worker (caché offline)
├── manifest.json   # Datos de instalación de la PWA
├── icon.svg        # Ícono de la app
└── README.md
```

## Publicar con GitHub Pages

1. Suba los archivos a la raíz del repositorio.
2. Vaya a **Settings → Pages**.
3. En **Source** elija la rama (por ejemplo `main`) y la carpeta `/ (root)`.
4. Guarde y espere unos minutos. La app quedará en `https://SU-USUARIO.github.io/NOMBRE-REPO/`.

Las PWA requieren **HTTPS**; GitHub Pages ya lo incluye.

## Instalar en el celular

Abra la dirección en Chrome (Android) y use **Instalar app** o **Añadir a pantalla de inicio**. Abra la app una vez con internet para que se guarde en caché.

## Cómo agregar o editar contenido

El contenido está en el arreglo `D` dentro de `index.html`. Cada ley es un objeto y cada tema se crea con la función `I()`:

```js
{id:"ley", t:"Pestaña", u:"https://enlace-oficial", ul:"Nombre de la fuente", sub:"Descripción corta", items:[
  I("Título del tema",
    ["Base legal 1","Base legal 2"],          // base legal
    ["Lo que SÍ puede hacer"],                // puede / debe
    ["Lo que NO puede hacer"],                // no puede
    ["Paso 1","Paso 2"])                      // pasos y buenas prácticas
]}
```

Cuando cambie archivos ya publicados, suba la versión del caché en `sw.js` (por ejemplo, de `guia-policial-v1` a `guia-policial-v2`) para que los dispositivos descarguen la actualización.

## Pendientes y limitaciones

- Confirmar en el SCIJ los artículos marcados como «verificar» (Código Procesal Penal, Leyes 8204, 7530, 9078 y 9028, y el reglamento de la Ley 9028).
- Los enlaces oficiales apuntan a la página principal del SCIJ; falta reemplazarlos por enlaces directos a cada ley.
- El contenido es resumido y no reemplaza la lectura del texto completo de cada norma.
- Revisar el contenido contra los protocolos vigentes del Ministerio de Seguridad Pública.

## Contribuir

Las correcciones son bienvenidas, sobre todo con la cita del artículo y el enlace a la fuente oficial. Abra un *issue* o un *pull request* indicando la norma, el artículo y la fuente.

## Licencia

Pendiente de definir por la persona autora del repositorio (por ejemplo, MIT para el código).
