# Mapa de Revisão do Projeto Mobile

## Arquivos mais importantes para a migração

### 1. `mobile/.env`
Problema atual:
- aponta para domínio remoto

Ação:
- substituir por configuração neutra
- ou remover dependência obrigatória

---

### 2. `mobile/hooks/useApiBase.ts`
Problema provável:
- escolhe uma base de API remota automaticamente

Ação:
- criar fallback local/offline
- nunca depender de Replit por padrão

---

### 3. `mobile/context/AppContext.tsx`
Problema provável:
- centraliza ações que podem chamar backend remoto

Ação:
- mapear funções dependentes de API
- isolar modo local

---

### 4. `mobile/components/Terminal.tsx`
Problema provável:
- terminal depende de sessão remota

Ação:
- desativar temporariamente ou substituir por modo local futuro

---

### 5. `mobile/components/PreviewPanel.tsx`
Problema provável:
- preview de servidor depende de rota remota

Ação:
- manter apenas preview local/HTML quando possível

---

### 6. `mobile/components/SystemStatus.tsx`
Problema provável:
- mede saúde de serviços remotos

Ação:
- adaptar para modo local
- exibir “recurso desativado” em vez de erro

---

### 7. `mobile/app/(tabs)/terminal.tsx`
Problema provável:
- tela assume que existe terminal Linux remoto

Ação:
- esconder ou adaptar
- mostrar mensagem clara no modo local

---

### 8. `mobile/app/(tabs)/plugins.tsx`
Problema provável:
- catálogo oferece instalações que dependem de backend/servidor

Ação:
- limitar para modo informativo
- marcar o que só funciona em Termux/local futuro

---

### 9. `mobile/app/(tabs)/settings.tsx`
Problema provável:
- pode permitir configurações que ainda usam backend remoto

Ação:
- criar sessão “modo local”
- separar recursos locais e remotos

---

## Regra de ouro
Na primeira fase, o objetivo não é manter 100% dos recursos.
O objetivo é:
- o app abrir
- funcionar bem
- não depender do Replit
- estar pronto para APK