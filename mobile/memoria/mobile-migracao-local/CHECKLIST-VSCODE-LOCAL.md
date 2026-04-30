# Checklist — VS Code local / code-server local

## Primeiro entender
- [ ] O VS Code atual do projeto depende do backend
- [ ] Sem backend remoto, ele provavelmente para
- [ ] Editor local simples continua viável

## Fase 1 — modo seguro
- [ ] manter editor local
- [ ] ocultar code-server remoto
- [ ] evitar erro de tela vermelha
- [ ] revisar `VSCodeView.tsx`

## Fase 2 — arquitetura local
- [ ] decidir se vai usar Termux
- [ ] decidir se vai subir servidor local
- [ ] definir porta local
- [ ] testar `127.0.0.1`

## Fase 3 — se quiser code-server real
- [ ] instalar code-server no ambiente local
- [ ] manter processo ativo
- [ ] testar acesso por navegador
- [ ] testar acesso por WebView
- [ ] revisar autenticação

## Regra prática
Sem processo servindo o code-server, não existe code-server funcionando.