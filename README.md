# Pack Fullstack para Claude Code — muestra pública

> A curated [Claude Code](https://claude.com/claude-code) configuration pack for
> Next.js + TypeScript (in Spanish). **This repository is a public sample** that
> shows the quality of the prompts — the full pack is a paid product.

Configuración curada de Claude Code lista para descomprimir en un proyecto
Next.js + TypeScript: subagentes especializados, slash commands, hooks de
seguridad y plantilla `CLAUDE.md`. Creado por Ariel Alejandro Hidalgo Rodríguez.

## Esto es una muestra

Este repositorio contiene **2 de los 8 subagentes** y **1 de los 5 comandos**
del pack, publicados como ejemplo de la calidad de los prompts. El producto
completo se distribuye por separado.

En [`samples/`](samples/):
- `agents/code-reviewer.md` — revisa diffs marcando BLOCKER / MAJOR / MINOR.
- `agents/commit-writer.md` — Conventional Commits desde el staged.
- `commands/review.md` — lanza la revisión sobre los cambios pendientes.

## Qué incluye el pack completo

### 8 subagentes (auto-invocables)

| Subagente | Modelo | Para qué |
|---|---|---|
| `code-reviewer` | Sonnet | Revisa diffs marcando BLOCKER / MAJOR / MINOR. |
| `test-writer` | Sonnet | Tests Vitest con estructura AAA. |
| `refactor-safe` | Sonnet | Refactoriza garantizando verde → verde. |
| `debugger` | Opus | Reproduce, causa raíz, fix mínimo + test. |
| `migration-writer` | Sonnet | Migraciones Drizzle / Prisma seguras. |
| `api-designer` | Sonnet | Endpoints REST consistentes con validación Zod. |
| `commit-writer` | Haiku | Conventional Commits desde staged. |
| `pr-describer` | Haiku | Título y descripción de PR desde el diff. |

### 5 slash commands

`/review` · `/ship` (typecheck + lint + tests + review + commit + PR) ·
`/tdd <feature>` · `/scaffold <ruta>` · `/explain <símbolo>`.

### Configuración y extras

- Plantilla `CLAUDE.md` con 10 secciones rellenables.
- `settings.json` con 40+ permisos pre-aprobados y bloqueos para comandos peligrosos.
- 2 hooks: bloqueo de comandos destructivos y formateo automático tras editar.
- Documentación completa: instalación, referencia de agentes, personalización y FAQ.

## Conseguir el pack completo

Disponible en Gumroad (enlace próximamente). Para información o early access,
contacto a través de [LinkedIn](https://www.linkedin.com/in/ariel-hidalgo).

## Licencia

Muestra con fines de demostración y portfolio. Ver [NOTICE.md](NOTICE.md).
