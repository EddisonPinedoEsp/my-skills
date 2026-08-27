---
name: commit-message-writer
description: >
  Genera mensajes de commit con formato Conventional Commits.
  Úsame cuando quieras escribir un commit, hacer commit de tus cambios,
  o resumir tu diff staged. Se activa con frases como "escribe un mensaje
  de commit", "commitea mis cambios" o "resume mi diff staged".
---

## Formato de output

Usa la especificación Conventional Commits:

type(scope): descripción corta

[cuerpo opcional]

[footer opcional]

## Tipos permitidos

- `feat` — nueva funcionalidad
- `fix` — corrección de bug
- `docs` — cambios en documentación
- `refactor` — refactorización sin cambio de comportamiento
- `test` — agregar o corregir tests
- `chore` — tareas de mantenimiento

## Reglas

1. La descripción corta debe estar en modo imperativo (ej: "add", no "added")
2. Máximo 72 caracteres en la primera línea
3. Genera el output directamente, sin hacer preguntas
4. Nunca uses lenguaje vago como "update stuff" o "fix things"
5. Si hay cambios en archivos no relacionados, agrupa por tipo de cambio
