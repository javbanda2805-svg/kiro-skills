# kiro-skills

Colección de skills para [Kiro](https://kiro.dev), en el layout que Kiro carga automáticamente.

Al clonar este repo como workspace, los 15 skills de `.kiro/skills/` quedan disponibles
como skills de proyecto sin ningún paso extra.

## Contenido

### superpowers (14 skills)

Portados de [obra/superpowers](https://github.com/obra/superpowers) v6.3.0, por Jesse Vincent.

| Skill | Cuándo se activa |
|---|---|
| `brainstorming` | Antes de trabajo creativo: explora intención y diseño antes de implementar |
| `dispatching-parallel-agents` | 2+ tareas independientes sin estado compartido |
| `executing-plans` | Ejecutar un plan escrito con checkpoints de revisión |
| `finishing-a-development-branch` | Implementación lista, decidir cómo integrar |
| `receiving-code-review` | Recibir feedback de revisión con rigor técnico |
| `requesting-code-review` | Verificar que el trabajo cumple los requisitos |
| `subagent-driven-development` | Planes con tareas independientes en la sesión actual |
| `systematic-debugging` | Cualquier bug o fallo de test, antes de proponer arreglos |
| `test-driven-development` | Implementar feature o bugfix, antes del código |
| `using-git-worktrees` | Trabajo que necesita aislamiento del workspace |
| `using-superpowers` | Cómo encontrar y usar los demás skills |
| `verification-before-completion` | Antes de afirmar que algo está listo: evidencia primero |
| `writing-plans` | Spec o requisitos para una tarea multi-paso |
| `writing-skills` | Crear, editar o verificar skills |

### resume-builder (1 skill)

Portado de [dabydat/resume-builder-skill](https://github.com/dabydat/resume-builder-skill).
Construcción de CV siguiendo estándares de Harvard Career Services y buenas prácticas de ATS.

## Instalación

**Como skills de proyecto** — clona el repo y usa la carpeta como workspace.

**Como skills globales** (IDE y CLI; no aplica en Web):

```bash
git clone https://github.com/<tu-usuario>/kiro-skills.git
cp -r kiro-skills/.kiro/skills/. ~/.kiro/skills/
```

**Como skills personales en Kiro Web** — comprime cada carpeta individualmente
(el nombre del zip debe coincidir con el campo `name` del frontmatter) y súbela
en Settings > Skills.

Los skills se cargan al inicio de la sesión: abre una sesión nueva después de instalarlos.

## Diferencias respecto a los plugins originales de Claude Code

`obra/superpowers` se distribuye como plugin de Claude Code. Al portarlo a Kiro se
queda fuera lo que depende de ese runtime:

- **`hooks/session-start`** — inyectaba el contexto de `using-superpowers` en cada
  sesión. Sin el hook, ese skill se activa por su descripción como cualquier otro.
- **Comandos `/brainstorm`, `/write-plan`, `/execute-plan`** — los generaba el runtime
  de plugins. En Kiro se invocan por el nombre del skill: `/brainstorming`,
  `/writing-plans`, `/executing-plans`.
- **`skills-search`** — herramienta del plugin, sin equivalente.

Los `SKILL.md` en sí no se modificaron: el formato de frontmatter (`name` + `description`)
es compatible entre Claude Code y Kiro.

## Licencias

Cada skill conserva la licencia de su proyecto de origen. Ver los repositorios
enlazados arriba. Este repo solo reorganiza los archivos en el layout de Kiro.
