---
publish: true
created: 2026-03-08T21:27:09.656+01:00
modified: 2026-03-08T21:28:49.966+01:00
cssclasses: ""
---

### **Session Management**

- **Start named session:** `tmux new -s [session_name]`
    
- **Detach (Keep programs running):** `Ctrl` + `b`, then tap `d`
    
- **List all sessions:** `tmux ls`
    
- **Reattach to last session:** `tmux attach`
    
- **Reattach to specific session:** `tmux attach -t [name]`
    
- **Kill a specific session:** `tmux kill-session -t [name]`
    

### **Navigation inside tmux**

- **Create new window:** `Ctrl` + `b`, then `c`
    
- **Switch windows:** `Ctrl` + `b`, then `[number]` (0-9)
    
- **Split vertically:** `Ctrl` + `b`, then `%`
    
- **Split horizontally:** `Ctrl` + `b`, then `"`