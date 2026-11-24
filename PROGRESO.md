# PROGRESO · Notas DAM

Archivo para retomar el trabajo cada día. **Leedlo al empezar y actualizadlo al terminar.**

---

## Contexto del proyecto

- **Asignatura:** 1º DAM · Proyecto "De Cero a App Web: SCRUM + Kanban + IA + Git".
- **Regla de oro (la pizza margarita):** primero 1 pantalla sencilla que funcione y después mejoras en micro-fases. Nosotros dirigimos y la IA escribe el código.
- **Requisito:** la app tiene que funcionar en un único `index.html`, sin servidores ni bases de datos.

## Equipo y roles

| Rol | Persona |
|---|---|
| Product Owner (PO): decide prioridades | Dani |
| Scrum Master (SM): tiempos, bloqueos y regla de 1 tarea en HACIENDO | Jose Luis |
| Dev | Rafael Graciano |
| Dev | Pablo García |

Todos somos Devs. Los roles se pueden cambiar si el grupo lo decide.

## Idea elegida: Calculadora de notas de 1º DAM

Escribes la nota de cada módulo y la app calcula la media, marca los suspensos y dice si apruebas.

Módulos: Programación, Bases de Datos, Sistemas Informáticos, Entornos de Desarrollo, Lenguajes de Marcas e IPE I.

### Historias de usuario
1. Como estudiante, quiero escribir mis notas de cada módulo para no tener que calcular a mano.
2. Como estudiante, quiero ver mi nota media al momento para saber cómo voy.
3. Como estudiante, quiero ver en rojo los módulos suspensos para saber cuáles tengo que recuperar.
4. Como estudiante, quiero que mis notas se guarden al cerrar la página para no tener que meterlas otra vez.
5. Como estudiante, quiero que se vea bien en el móvil para consultarla en clase.

## Archivos de la carpeta

| Archivo | Qué es |
|---|---|
| `index.html` | La app. Se abre con doble clic. |
| `kanban.html` | Tablero Kanban en HTML (plan B, solo guarda en el navegador de quien lo usa). |
| `kanban-notion.csv` | Tareas para importar en Notion y crear el tablero Kanban. |
| `README.md` | Presentación del proyecto y reglas de Git. |
| `PROGRESO.md` | Este archivo: dónde estamos y qué toca. |

---

## Estado del Día 1 (24/11/2026)

### ✅ Hecho
- Roles asignados (propuesta).
- Idea de app elegida y 5 historias de usuario.
- Primera pantalla (`index.html`): lista de módulos con casillas de nota y botón "Calcular media".
- Tablero Kanban en HTML y CSV preparado para Notion.
- README con las reglas de trabajo.

### ⏳ Pendiente del Día 1
- [ ] **Confirmar en grupo** los roles y la idea de app.
- [ ] **Abrir `index.html` y `kanban.html` en el navegador** para comprobar que funcionan (aún no se han probado).
- [ ] **Crear el tablero en Notion**: Importar → CSV (`kanban-notion.csv`) → Añadir vista Tablero → Agrupar por "Estado" → Compartir con los 4.
- [x] **Git instalado** en el PC de Dani (versión 2.56.1).
- [x] **Repositorio local creado** (`git init`) con el primer commit.
- [ ] **Crear el repo `notas-dam` en GitHub** (vacío, sin README) y añadir a los otros 3 como colaboradores.
- [ ] **Subir la carpeta** (desde dentro de `notas-dam`):
  ```
  git remote add origin https://github.com/USUARIO/notas-dam.git
  git push -u origin main
  ```
- [ ] Los demás hacen `git clone https://github.com/USUARIO/notas-dam.git`.

---

## Siguientes tareas (por prioridad)

1. **Poner en rojo los suspensos**: si una nota es menor que 5, la fila se marca en rojo.
2. **Decir si apruebas el curso**: mensaje "Apruebas todo 🎉" o "Tienes que recuperar: …".
3. **Guardar notas**: usar `localStorage` para que las notas sigan ahí al recargar la página.
4. **Estilos y versión móvil**: mejorar el aspecto y comprobarlo en el móvil.

Ideas para más adelante (solo si sobra tiempo): media ponderada por horas de cada módulo, botón "borrar notas" y modo oscuro.

---

## Cómo trabajar cada día

1. `git pull` antes de tocar nada.
2. Cada uno coge **1 tarea** del Kanban y la mueve a HACIENDO.
3. Se pide el código a la IA, se prueba en el navegador y, si funciona, se hace commit:
   ```
   git add .
   git commit -m "Qué he cambiado"
   git push
   ```
4. La tarea se mueve a HECHO.
5. **Al terminar el día, se actualiza este archivo** (qué se hizo, qué toca y qué bloqueos hay).

## Bloqueos / dudas abiertas

- Falta crear el repo en GitHub y hacer el primer `git push`.
- Falta confirmar los roles y la idea con todo el grupo.

---

## Registro diario

### Día 1 · 24/11/2026
Montamos la base del proyecto: roles, idea, historias de usuario, primera pantalla y Kanban. Falta conectar Git y crear el tablero en Notion.

### Día 2 · __/__/____
_(rellenar)_
