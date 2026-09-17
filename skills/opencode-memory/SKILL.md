---
name: opencode-memory
description: Use when the user starts a new session, asks to save memory, wants to see session history, or mentions "memoria", "sesion", "guardar sesion", "historial". Also use at the beginning of every conversation to check for existing sessions.
---

# openCode Memory System

You have access to a persistent memory system that saves session histories.

## Location
All memory files are stored in: `C:\Users\juan\AppData\Local\Temp\opencode\`

## Commands Available

Use these PowerShell commands to interact with the memory system:

### Show Session Menu (at conversation start)
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action menu"
```

### Quick Session Selector
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action quick"
```

### Save a Message to Current Session
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action log -Message 'YOUR_MESSAGE_HERE'"
```

### Save Current Session
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action save"
```

### Discard Current Session
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action discard"
```

### Show Summary and Ask to Save
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action summary"
```

### List All Saved Sessions
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action list"
```

### Show Full History
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action history"
```

## Workflow Instructions

### At the START of every conversation:
1. Run the `menu` command to show available sessions
2. Ask the user if they want to:
   - Create a new session (provide a descriptive name)
   - Continue an existing session
3. If creating new, use a descriptive name like `react-componentes-dia1` or `python-api-rest`

### DURING the conversation:
- When important information is discussed, save it with the `log` command
- Use descriptive messages that capture the key point
- Example: `log "Expliqué la diferencia entre hooks useState y useEffect"`

### At the END of every conversation:
1. Run the `summary` command
2. Ask the user if they want to save the session
3. If yes, run `save`
4. If no, run `discard`

## Session Naming Rules
- Use lowercase letters, numbers, hyphens, and underscores only
- Max 50 characters
- Examples: `react-hooks-intro`, `python-basics-dia2`, `api-rest-node`

## Important Notes
- Sessions are stored as JSON files in `sessions/` folder
- The `memory.log` file contains the complete history of all sessions
- Current session is temporarily stored in `current_session.json`
- All times are relative (e.g., "hace 2 dias")
