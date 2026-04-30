# O que precisa ser feito no projeto atual

## Arquivos/pastas que precisam ser revisados primeiro

### Pasta `mobile/`
#### Arquivos principais
- `mobile/.env`
- `mobile/app.json`
- `mobile/hooks/useApiBase.ts`
- `mobile/context/AppContext.tsx`

#### Telas/componentes que provavelmente dependem de backend
- `mobile/components/Terminal.tsx`
- `mobile/components/PreviewPanel.tsx`
- `mobile/components/SystemStatus.tsx`
- `mobile/components/VSCodeView.tsx`
- `mobile/components/GitHubModal.tsx`
- `mobile/components/LibrarySearch.tsx`
- `mobile/components/AIChat.tsx`
- `mobile/components/FloatingAI.tsx`

#### Telas
- `mobile/app/(tabs)/terminal.tsx`
- `mobile/app/(tabs)/plugins.tsx`
- `mobile/app/(tabs)/settings.tsx`
- `mobile/app/(tabs)/editor.tsx`

---

### Pasta `api-server/`
Se a meta é não depender do servidor remoto, estes arquivos deixam de ser obrigatórios no APK puro, mas precisam ser estudados para substituição:

- `api-server/src/routes/terminal.ts`
- `api-server/src/routes/preview.ts`
- `api-server/src/routes/search.ts`
- `api-server/src/routes/github.ts`
- `api-server/src/routes/db.ts`
- `api-server/src/routes/ai-proxy.ts`
- `api-server/src/lib/codeServer.ts`

---

## Decisões que você precisa tomar
### 1. Terminal
- desativar no APK local?
- integrar com Termux?
- criar backend local futuro?

### 2. VS Code / code-server
- esconder?
- substituir por editor local?
- abrir code-server local no futuro?

### 3. IA
- usar proxy remoto?
- usar chave direta do provedor?

### 4. Banco
- remoto?
- SQLite local?
- sem banco por enquanto?

### 5. GitHub
- direto da API?
- via backend?
- desativado por enquanto?

---

## Recomendação objetiva
### Agora
- manter editor local
- manter projetos e tarefas
- manter configurações
- reduzir dependência remota

### Depois
- terminal local
- preview local avançado
- code-server local
- integrações extras