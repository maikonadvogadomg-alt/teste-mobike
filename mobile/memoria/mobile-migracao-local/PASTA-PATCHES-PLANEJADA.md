# Pasta de patches planejada

## Objetivo
Esta pasta não aplica mudanças automaticamente.
Ela diz quais arquivos reescrever primeiro no projeto.

## Ordem recomendada dos patches

### Patch 1 — Ambiente local
Arquivos:
- `mobile/.env`
- `mobile/hooks/useApiBase.ts`

Objetivo:
- remover domínio fixo do Replit
- criar fallback local/offline

---

### Patch 2 — Modo local no app
Arquivos:
- `mobile/context/AppContext.tsx`
- `mobile/components/SystemStatus.tsx`

Objetivo:
- identificar quando backend não existe
- não deixar o app quebrar
- exibir mensagens claras

---

### Patch 3 — Desativação elegante do terminal remoto
Arquivos:
- `mobile/components/Terminal.tsx`
- `mobile/app/(tabs)/terminal.tsx`

Objetivo:
- evitar erro vermelho
- mostrar estado “recurso local futuro” ou “modo remoto desligado”

---

### Patch 4 — VS Code / Preview
Arquivos:
- `mobile/components/VSCodeView.tsx`
- `mobile/components/PreviewPanel.tsx`

Objetivo:
- remover dependência dura de code-server remoto
- manter versão simplificada

---

### Patch 5 — Recursos remotos opcionais
Arquivos:
- `mobile/components/GitHubModal.tsx`
- `mobile/components/LibrarySearch.tsx`
- `mobile/components/AIChat.tsx`
- `mobile/app/(tabs)/plugins.tsx`
- `mobile/app/(tabs)/settings.tsx`

Objetivo:
- separar o que é local e o que é remoto
- evitar falhas quando não houver servidor