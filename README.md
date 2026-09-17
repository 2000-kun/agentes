# 🤖 Agentes OpenCode

Colección de agentes personalizados para OpenCode v2.

## Agentes Disponibles

| Agente | Modo | Descripción | Temp |
|--------|------|-------------|------|
| `arquitecto-codigo` | subagent | Transforma bocetos/diagramas en código producción | 0.2 |
| `orquestador` | all | Descompone proyectos y delega tareas a agentes | 0.2 |
| `devops-backend` | subagent | Backend, APIs, infraestructura, CI/CD | 0.2 |
| `qa-testing` | subagent | Testing unitario, integración, E2E | 0.1 |
| `seguridad-app` | subagent | Auditoría de seguridad, vulnerabilidades | 0.1 |
| `revisor-ui` | subagent | Auditoría frontend, estilos, diseño | 0.1 |
| `base-datos-dba` | subagent | DBA, queries, esquemas, rendimiento | 0.1 |
| `digitalizador` | subagent | OCR, documentos a formato estructurado | 0.0 |
| `auditor-financiero` | subagent | Análisis financiero, reportes métricos | 0.2 |
| `redactor-multimodal` | subagent | Copywriting, contenido visual persuasivo | 0.7 |
| `documentador` | subagent | README, guías, documentación técnica | 0.1 |
| `estudiante-visual` | subagent | Tutor académico, guías de estudio | 0.3 |
| `desarrollador-movil` | subagent | React Native, Flutter, Swift, Kotlin | 0.2 |
| `visionario` | all | Multimodal: imágenes, vídeos, código | 0.1 |

## Instalación

1. Clona este repositorio
2. Copia `opencode.jsonc` a tu configuración global:
   ```
   ~/.config/opencode/opencode.jsonc
   ```
3. Reinicia OpenCode

## Uso

Cambia de agente con `Shift+Tab` o usa `Ctrl+P` → `agent.list`.

## Personalización

- **Modo `subagent`**: El agente se ejecuta en una sesión hija
- **Modo `all`**: El agente puede ejecutar cualquier tool
- **Temperature**: Controla la creatividad (0.0 = preciso, 1.0 = creativo)

## Licencia

MIT
