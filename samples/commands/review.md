---
description: Revisa los cambios actuales (staged, unstaged o vs main) con el subagente code-reviewer.
argument-hint: [ruta opcional]
allowed-tools: Bash, Read, Grep, Glob, Agent
---

Lanza una revisión de código sobre $ARGUMENTS si se ha pasado una ruta, o sobre los cambios pendientes si no hay argumentos.

## Procedimiento

1. **Determina el alcance:**
   - Si `$ARGUMENTS` no está vacío → revisa esa ruta (archivo o directorio).
   - Si está vacío → en este orden:
     - `git diff --staged --stat` — si hay cambios staged, esos son el alcance.
     - `git diff --stat` — si no hay staged pero sí unstaged, esos.
     - `git diff origin/main...HEAD --stat` — si la rama tiene commits sobre main.
     - Si todo vacío → para y avisa: "No hay nada que revisar."

2. **Delega al subagente `code-reviewer`** pasándole el alcance detectado y el comando que produjo el diff. NO hagas la revisión tú directamente — el subagente está afinado para esto.

3. **Si el code-reviewer marca BLOCKER o MAJOR:** muestra la salida tal cual y para. No intentes arreglarlos en este comando.

4. **Si está limpio:** muestra el "Listo para mergear" del subagente y sugiere siguiente paso (`/ship` para preparar PR, o `commit-writer` para mensaje de commit).

## Notas

- Este comando es solo lectura. Nunca edita archivos.
- Si el repo no tiene rama `origin/main`, prueba `origin/master` y luego `origin/develop`.
