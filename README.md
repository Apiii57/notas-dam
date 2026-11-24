# Notas DAM

App web sencilla (un solo `index.html`) para calcular la media de las notas de 1º DAM.

## Equipo y roles

| Rol | Persona |
|---|---|
| Product Owner (PO) | Dani |
| Scrum Master (SM) | Jose Luis |
| Dev | Rafael Graciano |
| Dev | Pablo García |

Todos somos Devs: pedimos código a la IA y lo probamos.

## Historias de usuario

1. Como estudiante, quiero escribir mis notas de cada módulo para no tener que calcular a mano.
2. Como estudiante, quiero ver mi nota media al momento para saber cómo voy.
3. Como estudiante, quiero ver en rojo los módulos suspensos para saber cuáles tengo que recuperar.
4. Como estudiante, quiero que mis notas se guarden al cerrar la página para no tener que meterlas otra vez.
5. Como estudiante, quiero que se vea bien en el móvil para consultarla en clase.

## Archivos

- `index.html` → la app (abrir con doble clic en el navegador).
- `kanban.html` → nuestro tablero Kanban (POR HACER / HACIENDO / HECHO).
  Se guarda en el navegador de cada uno, así que lo usa una persona (el SM) y lo enseña en clase.

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
