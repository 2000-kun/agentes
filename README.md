# 🤖 Agentes OpenCode

Colección de **122 agentes** personalizados para OpenCode v2.

## Estructura

```
agents/
├── *.md              ← 55 agentes de stack/infraestructura
└── lang/             ← 67 agentes de lenguajes de programación
    ├── python.md
    ├── typescript.md
    ├── rust.md
    └── ... (67 lenguajes)
opencode.jsonc        ← config global (permisos, tool_output, agents)
```

## Configuración de modos (importante)

| Agentes | Modo | ¿Aparece en Shift+Tab? |
|---------|------|------------------------|
| `orquestador` | `primary` | ✅ Sí |
| `plan` (builtin) | `primary` | ✅ Sí |
| `build` (builtin) | `primary` | ✅ Sí |
| Todo lo demás (stack + `lang/*`) | `subagent` | ❌ No (solo delegación) |

En Shift+Tab solo aparecen **orquestador, plan y build**. El orquestador controla y delega al resto.

## Familias de agentes

### 1. Stack / infraestructura (`agents/*.md`)
Frontend, backend, BD, cloud, DevOps, QA, seguridad, mobile, IA, contenido.

| Categoría | Agentes |
|-----------|---------|
| Frontend | `arquitecto-codigo`, `react-frontend`, `vue-frontend`, `angular-frontend`, `svelte-frontend`, `revisor-ui`, `tailwind-specialist`, `threejs-webgl`, `accessibility-testing` |
| Backend | `devops-backend`, `nodejs-backend`, `python-backend`, `golang-backend`, `rust-backend`, `java-backend`, `dotnet-backend`, `php-laravel`, `graphql-specialist` |
| Bases de datos | `base-datos-dba`, `postgres-specialist`, `mongodb-specialist`, `redis-specialist` |
| Cloud/Infra | `aws-specialist`, `gcp-specialist`, `azure-specialist`, `kubernetes-expert`, `terraform-expert`, `docker-expert`, `linux-admin` |
| DevOps | `github-actions`, `gitlab-ci`, `jenkins-ci`, `observability-specialist` |
| QA | `qa-testing`, `cypress-e2e`, `playwright-e2e`, `k6-performance` |
| Seguridad | `seguridad-app`, `pentester`, `cloud-security` |
| Mobile | `desarrollador-movil`, `react-native-expert`, `flutter-expert`, `swift-ios`, `kotlin-android` |
| IA/Data | `ml-engineer` |
| Blockchain | `solidity-web3` |
| Coordinación | `orquestador`, `coordinador` |
| Otros | `documentador`, `digitalizador`, `auditor-financiero`, `estudiante-visual`, `redactor-multimodal`, `office-reader`, `visionario` |

### 2. Lenguajes (`agents/lang/*.md`) — 67 agentes
`lang/python` · `lang/javascript` · `lang/typescript` · `lang/java` · `lang/csharp` · `lang/cpp` · `lang/c` · `lang/go` · `lang/rust` · `lang/ruby` · `lang/php` · `lang/swift` · `lang/kotlin` · `lang/scala` · `lang/dart` · `lang/r` · `lang/julia` · `lang/matlab` · `lang/perl` · `lang/lua` · `lang/bash` · `lang/powershell` · `lang/haskell` · `lang/elixir` · `lang/erlang` · `lang/clojure` · `lang/fsharp` · `lang/ocaml` · `lang/elm` · `lang/scheme` · `lang/lisp` · `lang/prolog` · `lang/sql` · `lang/html` · `lang/css` · `lang/zig` · `lang/nim` · `lang/crystal` · `lang/v` · `lang/odin` · `lang/haxe` · `lang/solidity` · `lang/vyper` · `lang/verilog` · `lang/vhdl` · `lang/asm` · `lang/fortran` · `lang/cobol` · `lang/pascal` · `lang/vb` · `lang/vba` · `lang/abap` · `lang/groovy` · `lang/objectivec` · `lang/ada` · `lang/apex` · `lang/gdscript` · `lang/applescript` · `lang/autohotkey` · `lang/smalltalk` · `lang/awk` · `lang/tcl` · `lang/hack` · `lang/sas` · `lang/stata` · `lang/batch` · `lang/cairo`

## Instalación

```powershell
# 1. Copia los agentes a tu config global
Copy-Item -Recurse agents "$env:USERPROFILE\.config\opencode\agents"

# 2. Fusiona opencode.jsonc con tu config global
#    ~/.config/opencode/opencode.jsonc

# 3. Reinicia OpenCode
```

## Ahorro de créditos

El orquestador incluye un **Protocolo de Ahorro de Créditos**:
- No delega tareas triviales (< 20 líneas → lo hace él mismo)
- Máximo 3 subagentes simultáneos
- Contexto mínimo por delegación (rutas, no archivos enteros)
- Un solo re-intento si un agente falla
- Reportes de ≤ 15 líneas

Configuración asociada en `opencode.jsonc`:
- `tool_output.max_lines`: 2000 / `max_bytes`: 65536
- `compaction.keep.tokens`: 12000
- `media.image.max_base64_bytes`: 2MB

## Uso

- **Shift+Tab** → cicla entre `orquestador`, `plan`, `build`
- El orquestador descompone la tarea y delega al agente correcto
- Los subagentes no aparecen en Shift+Tab: se lanzan solo por delegación

## Licencia

MIT
