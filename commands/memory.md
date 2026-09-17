---
description: Manage session memory - save, load, list, or delete sessions
agent: build
---

# Memory Management

You are helping the user manage their session memory.

## Available Actions

Based on the user's input ($ARGUMENTS), perform one of these actions:

### If no arguments or "menu":
Show the session menu by running:
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action menu"
```

### If argument is "list" or "ls":
List all saved sessions:
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action list"
```

### If argument is "history" or "log":
Show full history:
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action history"
```

### If argument is "save":
Save the current session:
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action save"
```

### If argument is "discard" or "delete":
Discard the current session:
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action discard"
```

### If argument is "summary" or "resume":
Show summary and ask to save:
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action summary"
```

### If argument starts with "log ":
Save the message (remove "log " prefix):
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action log -Message 'THE_MESSAGE'"
```

### If argument is "quick":
Quick session selector:
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action quick"
```

## Instructions

1. Parse the user's input ($ARGUMENTS)
2. Execute the appropriate command
3. Show the output to the user
4. If creating a new session, help the user choose a descriptive name
5. If saving a log entry, confirm it was saved
6. At the end of a conversation, remind the user to save their session

## Examples

User types: `/memory` → Show menu
User types: `/memory list` → List sessions
User types: `/memory save` → Save current session
User types: `/memory log "aprendí hooks"` → Save message
User types: `/memory history` → Show history
