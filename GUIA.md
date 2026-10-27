# Muebles en realidad aumentada: guía rápida

## Qué hay en esta carpeta

```
ra-muebles/
├── index.html          ← visor RA (sirve para todos los muebles)
├── fichas-qr.html      ← generador de fichas imprimibles con QR
├── GUIA.md             ← esta guía
└── modelos/
    └── mesilla-ejemplo.glb   ← modelo de prueba (450 × 400 × 550 mm)
```

## 1. Exportar desde SketchUp

1. Modela en milímetros, con el mueble apoyado en el suelo (eje azul = 0).
2. Agrupa el mueble y elimina todo lo que sobre (personas, ejes, cotas).
3. Exporta a **.glb (glTF binario)**. Si tu versión de SketchUp no lo tiene de serie, instala una extensión gratuita de exportación glTF desde el Extension Warehouse.
4. Nombra el archivo sin espacios ni tildes: `mesilla-lucia.glb`, `banco-grupo2.glb`.
5. Intenta que pese menos de 10–15 MB. Evita tornillería y texturas muy pesadas.

El visor muestra las medidas que lee del archivo. Si no coinciden con el diseño, la exportación tiene mal las unidades.

## 2. Publicar gratis con GitHub Pages

La realidad aumentada solo funciona si la página está en internet con `https://`. Abrir el archivo desde el ordenador no basta.

1. Crea una cuenta gratuita en github.com.
2. Crea un repositorio público llamado `ra-muebles`.
3. Pulsa «Add file → Upload files» y arrastra `index.html` y la carpeta `modelos` con los .glb.
4. Ve a «Settings → Pages», elige la rama `main` y la carpeta raíz, y guarda.
5. En un par de minutos tendrás la dirección: `https://TU-USUARIO.github.io/ra-muebles/`

Prueba primero con la mesilla de ejemplo: abre esa dirección en el móvil y pulsa el botón amarillo.

Para añadir muebles nuevos, sube solo los .glb a la carpeta `modelos`. No hace falta tocar el visor.

## 3. Imprimir las fichas

1. Abre `fichas-qr.html` en el ordenador (con conexión a internet).
2. Pega la dirección de GitHub Pages en «Dirección del visor».
3. Rellena un bloque por mueble. En «Archivo» pon solo el nombre: `mesilla-lucia.glb`.
4. Pulsa «Imprimir fichas». Salen dos por folio A4.

Los datos se guardan en el navegador, así que puedes cerrar y seguir otro día.

Si algún alumno publica en Sketchfab en lugar de GitHub, pega su enlace completo en «Archivo» y el QR irá directamente allí.

## 4. Antes de la sesión, comprueba

- Que la mesilla de ejemplo se ve en al menos un Android y un iPhone del grupo.
- Que el suelo del aula tiene algo de textura y buena luz (los suelos brillantes cuestan más).
- Que hay un metro a mano para comparar una cota real con la virtual.

## Problemas frecuentes

| Lo que pasa | Causa probable |
|---|---|
| «No se encuentra el modelo» | El nombre del QR no coincide con el archivo (mayúsculas, tildes, espacios). |
| El mueble aparece gigante o diminuto | Unidades mal exportadas desde SketchUp. El visor lo avisa. |
| Flota o se hunde en el suelo | El modelo no estaba apoyado en el eje azul = 0. |
| No sale el botón de RA | Móvil sin soporte de RA o página abierta sin `https://`. |
| Se ve negro o sin color | Materiales sin color asignado; aplica colores sencillos en SketchUp. |

## 5. QR para la documentación técnica

Abre `generador-qr.html` en el ordenador, arrastra el .glb y comprueba las medidas. Escribe la dirección del visor, descarga el PNG y pégalo en la memoria o los planos del proyecto (3–4 cm de ancho). Sube después el .glb a `modelos/` con el nombre que indica la herramienta.

## 6. Anclaje a una lámina impresa

Con `anclaje.html` el mueble aparece de pie sobre una imagen impresa, a la escala del plano (por defecto 1:10). Un botón permite verlo a tamaño real.

**Preparar el marcador (una sola vez):**

1. Abre el compilador gratuito de MindAR: https://hiukim.github.io/mind-ar-js-doc/tools/compile
2. Sube `marcadores/marcador.png` (o tu propia imagen) y pulsa «Start».
3. Descarga el resultado, llámalo `marcador.mind` y súbelo a la carpeta `marcadores/` de GitHub.
4. Imprime `marcador.png` exactamente a **150 mm de ancho** (o indica otro ancho en el generador).

Un mismo marcador sirve para todos los proyectos: el QR decide qué mueble se ve.

**Buenas imágenes marcador:** mucho contraste, muchas esquinas y formas distintas, sin repeticiones ni simetrías. Un QR, un logotipo simple o un plano con mucho blanco funcionan mal. Imprime en papel mate.

**Generar el QR:** en `generador-qr.html` marca «Anclar a una lámina impresa», revisa marcador, escala y ancho, y descarga el PNG. En la documentación, coloca el QR y la lámina en la misma hoja.
