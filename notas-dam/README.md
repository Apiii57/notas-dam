# Sistema Solar DAM

Simulador **3D** del sistema solar en un solo `index.html`: el Sol, los 8 planetas, las lunas principales de cada planeta, sus movimientos, el cinturón de asteroides y dos cometas (Halley y Encke).

> Usa la librería **Three.js** (WebGL), que se descarga de internet al abrir la página: **hace falta conexión a internet**.

## Equipo y roles

| Rol | Persona |
|---|---|
| Product Owner (PO) | Dani |
| Scrum Master (SM) | Jose Luis |
| Dev | Rafael Graciano |
| Dev | Pablo García |

Todos somos Devs: pedimos código a la IA y lo probamos.

## Historias de usuario

1. Como estudiante, quiero ver el Sol y los planetas girando para entender cómo se mueve el sistema solar.
2. Como estudiante, quiero ver las lunas de cada planeta girando a su alrededor para saber cuántas tiene y cómo se mueven.
3. Como estudiante, quiero ver un cometa con su órbita alargada y su cola para entender en qué se diferencia de un planeta.
4. Como estudiante, quiero acelerar, parar o invertir el tiempo para ver movimientos que en la realidad tardan años.
5. Como estudiante, quiero pulsar en un astro y ver su ficha con datos reales para aprender sobre él.
6. Como estudiante, quiero hacer zoom y moverme por el mapa, también en el móvil, para verlo desde cualquier sitio.

## Qué tiene la app

- **3D real** con Three.js: se puede girar la cámara alrededor de cualquier astro, y la cámara viaja hasta él y lo sigue.
- **Diseños de los planetas**: la Tierra y la Luna usan fotos reales de satélite (con nubes, océanos que brillan y luces de las ciudades en la cara de noche). El resto se dibuja por código con ruido procedural: las bandas y la Gran Mancha Roja de Júpiter, los casquetes y el cañón de Marte, las nubes de Venus, los cráteres de Mercurio y de las lunas, los volcanes de Ío, las grietas de Europa, las dos caras de Jápeto…
- **Sol animado** (shader con plasma, granulación y manchas solares) con efecto de brillo (bloom).
- **Atmósferas** que brillan en el borde, y **anillos de Saturno** con la sombra del planeta encima.
- **Ejes inclinados** reales: Urano gira tumbado y sus lunas y anillos están en vertical; Venus gira al revés.
- **Cinturón de asteroides** con 3 000 rocas.
- **10 naves y satélites** con modelos 3D: ISS, Hubble, GPS, un satélite geoestacionario y el James Webb (en el punto L2) alrededor de la Tierra; MRO en Marte; la Parker Solar Probe rozando el Sol; y las Voyager 1 y 2 y New Horizons saliendo del sistema solar en su dirección real, con su distancia y el tiempo que tarda su señal.
- **🕳️ Agujero negro TON 618**: simulación por trazado de rayos en la tarjeta gráfica. La luz se curva con la ecuación real de la relatividad general (métrica de Schwarzschild), así que aparecen solos la sombra, el anillo de fotones, el disco de acreción doblado por encima y por debajo, el efecto Doppler relativista y la lente gravitacional de las estrellas. Se puede activar o quitar cada efecto para comparar, y tiene chorros (jets) opcionales y calidad automática.
- **Planetas** con sus periodos reales (un año de Neptuno = 164,8 años de la Tierra), colocados en la posición aproximada de la fecha de hoy.
- **22 lunas**: la Luna; Fobos y Deimos; las 4 galileanas de Júpiter; 7 de Saturno; 5 de Urano (con las órbitas casi de canto por la inclinación de Urano); Proteo, Tritón (gira al revés) y Nereida (órbita muy alargada) de Neptuno.
- **Cometas Halley y Encke**: órbitas elípticas e inclinadas en 3D calculadas con la ecuación de Kepler. Van más rápido cerca del Sol y tienen dos colas de partículas (gas azul y polvo amarillento) que siempre apuntan en sentido contrario al Sol.
- **Controles**: pausa, invertir el tiempo, velocidad (de horas a años por segundo), botón "Hoy" y mostrar u ocultar órbitas, nombres, cometas y asteroides.
- **Ficha de cada astro** al pulsarlo: la cámara lo sigue y hace zoom.
- Se puede abrir directamente un astro con la dirección: `index.html#Saturno`, una nave (`index.html#ISS`) o el agujero negro (`index.html#TON618`).

> Las distancias están comprimidas y los tamaños, exagerados: a escala real los planetas serían puntos invisibles.

## Cómo se usa

Abrir `index.html` con doble clic (con internet). Arrastrar = girar la cámara, clic derecho = moverla, rueda = zoom, clic en un astro o en su nombre = viajar hasta él, Espacio = pausa, Esc = vista general. En el móvil: un dedo gira y dos dedos hacen zoom.

## Archivos

- `index.html` → la app.
- `kanban.html` → nuestro tablero Kanban (POR HACER / HACIENDO / HECHO).
  Se guarda en el navegador de cada uno, así que lo usa una persona (el SM) y lo enseña en clase.
- `kanban-notion.csv` → las tareas para importar en Notion.
- `PROGRESO.md` → dónde estamos y qué toca hacer.

## Cómo trabajar con Git

Antes de empezar cada día:

```
git pull
```

Después de hacer un cambio que funcione:

```
git add .
git commit -m "Qué he cambiado"
git push
```

Reglas:
- Siempre `git pull` antes de empezar.
- No tocar la misma parte del archivo dos personas a la vez.
- Máximo 1 tarea en HACIENDO por persona.
