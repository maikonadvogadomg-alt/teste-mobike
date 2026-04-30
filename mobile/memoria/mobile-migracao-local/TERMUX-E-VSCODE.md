# Termux, VS Code e rodar tudo localmente no celular

## Objetivo
Explicar como pensar a arquitetura local sem depender do Replit.

---

## Opção 1 — App local + Termux separado
### Como funciona
- o APK é a interface
- o Termux é o terminal real
- o app conversa com o Termux de forma indireta

### Formas de integração
- abrir Termux via intent
- compartilhar comandos
- usar arquivos intermediários
- usar servidor local HTTP dentro do Termux
- usar porta localhost (127.0.0.1)

### Vantagem
Mais realista no Android.

### Desvantagem
Exige configuração extra.

---

## Opção 2 — App local + servidor local no próprio celular
### Como funciona
- você sobe um processo local no celular
- esse processo oferece rotas HTTP
- o app mobile consome `http://127.0.0.1:PORTA`

### Exemplo
- backend Node rodando no Termux
- code-server rodando localmente
- app acessando por localhost

### Problemas comuns
- porta errada
- app não consegue acessar localhost da forma esperada
- Android mata processo em background
- permissões/restrições de rede local

---

## Opção 3 — Editor local sem terminal real
### Como funciona
- o app mantém editor, arquivos, tarefas, IA direta
- terminal fica apenas informativo ou desativado
- preview fica limitado

### Vantagem
Muito mais estável.

### Desvantagem
Menos poderoso.

---

## Sobre localhost no Android
Dependendo da forma do app rodar:
- `localhost`
- `127.0.0.1`
- IP da interface local
podem se comportar diferente.

Quando o app está empacotado, nem sempre o que funciona no navegador funciona igual dentro do app.

---

## Sobre code-server
O `code-server` normalmente precisa de:
- processo rodando
- porta aberta
- senha/token
- acesso WebView ou navegador

Então ele pode funcionar localmente **se** houver um servidor local de verdade.

Sem isso, não funciona.

---

## Sobre VS Code embutido no projeto atual
Como existe `api-server/src/lib/codeServer.ts`, isso é um sinal forte de que o “VS Code” atual depende de backend.

Então, sem o backend:
- ou você desativa essa função
- ou recria uma versão local simplificada
- ou sobe um code-server local no celular

---

## Caminho mais recomendado
### Fase 1
- desativar dependência do code-server remoto
- manter só editor local

### Fase 2
- integrar Termux

### Fase 3
- testar backend local em `127.0.0.1`

### Fase 4
- só então tentar code-server local