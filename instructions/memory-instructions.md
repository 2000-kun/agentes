# Memory System Instructions

## CRITICAL: Always follow this workflow at conversation start

When you START a new conversation, you MUST:

1. **Check for existing sessions** by running this command:
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action list"
```

2. **Ask the user** if they want to:
   - Continue an existing session (if any exist)
   - Create a new session with a descriptive name

3. **At the END of EVERY conversation**, you MUST:
   - Run the summary command to show session stats
   - Ask the user if they want to save or discard the session

## Memory Commands Reference

Use these PowerShell commands:

### List sessions
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action list"
```

### Show menu
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action menu"
```

### Save message to current session
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action log -Message 'YOUR_MESSAGE'"
```

### Save current session
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action save"
```

### Discard current session
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action discard"
```

### Show summary and ask to save
```powershell
powershell -ExecutionPolicy Bypass -Command "& 'C:\Users\juan\AppData\Local\Temp\opencode\opencode-memory.ps1' -Action summary"
```

## Session Naming Rules
- Use lowercase, numbers, hyphens, underscores only
- Max 50 characters
- Examples: `react-hooks-intro`, `python-basics-dia2`

## During the Conversation
- When important information is discussed, save it with the log command
- Use descriptive messages

## IMPORTANT
- Always run the list command at conversation start
- Always ask about saving at conversation end
- This is mandatory, not optional
