# PROGRESO · Sistema Solar DAM

Archivo para retomar el trabajo cada día. **Leedlo al empezar y actualizadlo al terminar.**

---

## Contexto del proyecto

- **Asignatura:** 1º DAM · Proyecto "De Cero a App Web: SCRUM + Kanban + IA + Git".
- **Regla de oro (la pizza margarita):** primero 1 pantalla sencilla que funcione y después mejoras en micro-fases. Nosotros dirigimos y la IA escribe el código.
- **Requisito:** la app tiene que funcionar en un único `index.html`, sin servidores ni bases de datos.
- **Desde el Día 2 la app es 3D** con la librería Three.js, que se carga de internet (CDN jsDelivr). Sin conexión sale un aviso.

## Equipo y roles

| Rol | Persona |
|---|---|
| Product Owner (PO): decide prioridades | Dani |
| Scrum Master (SM): tiempos, bloqueos y regla de 1 tarea en HACIENDO | Jose Luis |
| Dev | Rafael Graciano |
| Dev | Pablo García |

Todos somos Devs. Los roles se pueden cambiar si el grupo lo decide.

## Idea elegida: Simulador del Sistema Solar

> **Cambio de idea (25/11/2026):** la primera idea era una calculadora de notas medias. El PO decidió cambiarla por un simulador del sistema solar con las lunas de cada planeta, sus movimientos y cometas. El repositorio y la carpeta siguen llamándose `notas-dam` para no romper el enlace de GitHub.

Una página que muestra el Sol, los 8 planetas girando con sus periodos reales, las lunas principales de cada planeta y los cometas Halley y Encke. Se puede acelerar el tiempo, hacer zoom y pulsar cada astro para ver su ficha.

### Historias de usuario
1. Como estudiante, quiero ver el Sol y los planetas girando para entender cómo se mueve el sistema solar.
2. Como estudiante, quiero ver las lunas de cada planeta girando a su alrededor para saber cuántas tiene y cómo se mueven.
3. Como estudiante, quiero ver un cometa con su órbita alargada y su cola para entender en qué se diferencia de un planeta.
4. Como estudiante, quiero acelerar, parar o invertir el tiempo para ver movimientos que en la realidad tardan años.
5. Como estudiante, quiero pulsar en un astro y ver su ficha con datos reales para aprender sobre él.
6. Como estudiante, quiero hacer zoom y moverme por el mapa, también en el móvil, para verlo desde cualquier sitio.

## Archivos de la carpeta

| Archivo | Qué es |
|---|---|
| `index.html` | La app. Se abre con doble clic. |
| `kanban.html` | Tablero Kanban en HTML (plan B, solo guarda en el navegador de quien lo usa). |
| `kanban-notion.csv` | Tareas para importar en Notion y crear el tablero Kanban. |
| `README.md` | Presentación del proyecto y reglas de Git. |
| `PROGRESO.md` | Este archivo: dónde estamos y qué toca. |

## Cómo está hecho `index.html` (para explicarlo en clase)

El código está dividido en 9 bloques numerados:

1. **Datos**: arrays `PLANETAS` y `COMETAS` con valores reales (periodos, diámetros, inclinaciones, órbitas). Para añadir una luna basta con una línea.
2. **Física**: `t` = días desde el 1/1/2000. Planetas y lunas: ángulo = inicial + 360° × t / periodo. Cometas y Nereida: **ecuación de Kepler** (`M = E − e·sen E`) resuelta con el método de Newton. `posicionOrbital` coloca cada punto en 3D según la inclinación y el nodo de su órbita.
3. **Ruido procedural**: ruido *simplex* 3D y `fbm` (varias capas de ruido) para crear superficies aleatorias pero naturales.
4. **Diseños**: una función por planeta y luna que decide el color de cada punto de la esfera (bandas, manchas, cráteres, casquetes…).
5. **Shaders** (programas de la tarjeta gráfica): superficie animada del Sol, brillo de las atmósferas y anillos con sombra.
6. **Escena 3D**: cámara, luz del Sol, estrellas y Vía Láctea, planetas, lunas, cometas (partículas) y cinturón de asteroides.
7. **Actualizar**: en cada fotograma se recalculan las posiciones según la fecha.
8. **Cámara y controles**: OrbitControls, viaje suave hasta el astro elegido y ficha de información.
9. **Arranque**: pantalla de carga, descarga de las fotos de la Tierra y la Luna, y bucle principal.
10. **Agujero negro TON 618**: un shader que lanza un rayo por píxel y lo curva paso a paso con la ecuación de la luz en la métrica de Schwarzschild (`aceleración = −1,5·h²·r/|r|⁵`, con el radio del horizonte = 1). Cuando el rayo cruza el plano del disco se suma el color del gas (temperatura según la distancia + efecto Doppler + corrimiento al rojo gravitatorio); si cae dentro del horizonte queda negro; si escapa, se pinta el fondo de estrellas.

11. **Sorpresa del eclipse** 👻: en cuanto colocas la cámara para que la Luna tape el Sol, sale del eclipse un bicho en 3D que se lanza contra la pantalla gritando (≈2 s). La cabeza es una esfera deformada vértice a vértice (cuencas, pómulos, mandíbula desencajada con *morph targets*), con doble fila de dientes, globos oculares inyectados en sangre que miran a la cámara, pelo y dos manos huesudas que se lanzan hacia la pantalla. Se acerca a saltos, con tirones de cabeza, grano de película y un gruñido grave bajo el grito; se dibuja en una escena aparte encima del sistema solar. El grito se sintetiza con Web Audio (no hay archivos). Para el realismo: sombras suaves (solo la luz del bicho las proyecta), mapa de rugosidad (ojos y boca húmedos), pelo hecho de cintas finas en mechones, dientes con encía y raíz manchada, y una pasada de postprocesado "cámara real" (aberración cromática, distorsión de lente, viñeta, grano y tono frío) que solo se activa durante el susto. Se vuelve a activar 15 s después de salir del eclipse. Detección: `eclipseTotal()`.

Las naves están en el array `SATELITES` y sus modelos 3D en `MODELOS` (hechos con cajas, cilindros y antenas).

**Escala:** distancia en pantalla = `30 + 75 × √(distancia en UA)`, y los planetas se dibujan mucho más grandes de lo real. Si no, no se vería nada.

---

## Estado del Día 1 (24/11/2026)

### ✅ Hecho
- Roles asignados (propuesta).
- Primera idea (calculadora de notas), primera pantalla, Kanban y README.
- Git instalado, repositorio creado y subido: https://github.com/Apiii57/notas-dam

## Estado del Día 2 (25/11/2026)

### ✅ Hecho
- **Cambio de idea:** simulador del sistema solar. Historias de usuario nuevas.
- `index.html` rehecho entero:
  - Sol y 8 planetas con periodos reales, en su posición aproximada de hoy.
  - 22 lunas: Luna; Fobos y Deimos; Ío, Europa, Ganímedes y Calisto; Mimas, Encélado, Tetis, Dione, Rea, Titán y Jápeto; Miranda, Ariel, Umbriel, Titania y Oberón (órbitas casi de canto por la inclinación de Urano); Proteo, Tritón (retrógrada) y Nereida (muy excéntrica).
  - Cometas Halley (retrógrado, 75 años) y Encke (3,3 años) con cola de polvo y cola de iones que apuntan en sentido contrario al Sol.
  - Controles: pausa, invertir el tiempo, velocidad, botón "Hoy", mostrar u ocultar órbitas, nombres y cometas.
  - Zoom con la rueda o pellizcando, arrastrar para moverse, clic en un astro para seguirlo y ver su ficha.
- README, Kanban (`kanban.html`) y CSV de Notion actualizados con las tareas nuevas.
- **Versión 3D profesional** con Three.js:
  - Tierra y Luna con fotos reales (nubes, brillo del océano, luces nocturnas); resto de planetas y lunas con texturas procedurales detalladas.
  - Sol animado con bloom, atmósferas, anillos de Saturno con sombra, anillos de Urano, ejes inclinados reales.
  - Colas de cometa con partículas, cinturón de asteroides, estrellas y Vía Láctea.
  - Cámara que viaja al astro, lo sigue y se coloca en su lado iluminado. Enlaces directos tipo `index.html#Saturno`.
  - Probada en Chrome: carga sin errores en la consola.
- **Naves y satélites**: ISS, Hubble, GPS, geoestacionario, James Webb (L2), MRO (Marte), Parker Solar Probe, Voyager 1 y 2 y New Horizons, con modelos 3D y fichas.
- **Modo agujero negro TON 618** con trazado de rayos relativista (sombra, anillo de fotones, disco doblado, Doppler, lente gravitacional, chorros opcionales). Botón arriba a la derecha.

- **Sorpresa del eclipse** (sección 11 de `index.html`), probada en Chrome.

### ⏳ Pendiente
- [ ] **Confirmar en grupo** el cambio de idea y los roles.
- [ ] **Probar `index.html`** en el navegador del PC y en el móvil.
- [ ] **Subir los cambios a GitHub** (`git add .`, `git commit`, `git push`).
- [ ] **Crear o actualizar el tablero en Notion**: Importar → CSV (`kanban-notion.csv`) → vista Tablero → Agrupar por "Estado".
- [ ] **Añadir colaboradores** en GitHub (Settings → Collaborators): Jose Luis, Rafael y Pablo.
- [ ] Los demás hacen `git clone https://github.com/Apiii57/notas-dam.git`.

---

## Siguientes tareas (por prioridad)

1. **Probar en el móvil** y corregir lo que se vea mal.
2. **Planetas enanos**: Plutón (con Caronte) y Ceres.
3. **Modo escala real**: un botón para ver las distancias reales y darse cuenta de lo vacío que está el espacio.
4. **Versión sin internet**: guardar Three.js dentro de la carpeta para que funcione sin conexión.

Ideas para más adelante (solo si sobra tiempo): más cometas, rastro de la órbita al moverse, sonido, y un modo "quiz" con preguntas sobre los planetas.
