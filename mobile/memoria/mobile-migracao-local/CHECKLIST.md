# Checklist de Migração para APK Local

## 1. Limpeza inicial
- [ ] Remover `mockup-sandbox/`
- [ ] Remover `mobile/.expo/`
- [ ] Remover `api-server/dist/`

## 2. Limpeza de vínculo com Replit
- [ ] Revisar `.replit-artifact/`
- [ ] Revisar `EXPO_PUBLIC_DOMAIN`
- [ ] Procurar `replit`, `kirk.replit.dev`, `REPLIT_`
- [ ] Remover domínio remoto padrão

## 3. Modo local/offline
- [ ] Ajustar `mobile/hooks/useApiBase.ts`
- [ ] Criar fallback sem servidor
- [ ] Evitar crash quando API estiver indisponível
- [ ] Mostrar aviso amigável quando recurso remoto estiver desligado

## 4. Áreas que precisam revisão
- [ ] Terminal
- [ ] Preview servidor
- [ ] IA via proxy
- [ ] GitHub via backend
- [ ] Banco remoto
- [ ] Busca web via backend
- [ ] Status do sistema

## 5. Recursos que devem continuar funcionando
- [ ] Projetos
- [ ] Editor
- [ ] Tarefas
- [ ] Configurações
- [ ] Estrutura visual do app
- [ ] Importação/exportação local, se já existir

## 6. Build
- [ ] Revisar `app.json`
- [ ] Revisar permissões Android
- [ ] Validar EAS config
- [ ] Gerar APK
- [ ] Testar em aparelho real

## 7. Pós-migração
- [ ] Decidir se vai integrar Termux
- [ ] Decidir se vai usar SQLite local
- [ ] Decidir se a IA será direta por API key
- [ ] Reativar recursos aos poucos