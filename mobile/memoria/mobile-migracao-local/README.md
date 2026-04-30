# Migração do DevMobile para APK Local (sem depender do servidor Replit)

Este pacote foi criado para ajudar na limpeza e migração do projeto `mobile` para uma versão que funcione no celular sem depender do servidor remoto.

## Objetivo
Transformar o app em um APK mais limpo, preparado para EAS Build, reduzindo ou removendo a dependência de:
- servidor Replit
- domínio remoto fixo
- rotas backend obrigatórias
- recursos que só funcionam com API externa ligada

---

## Estratégia recomendada

### Etapa 1 — Limpeza estrutural
Pode remover do projeto principal:
- `mockup-sandbox/`
- `mobile/.expo/`
- `api-server/dist/`

Depois revisar para possível remoção:
- `.replit-artifact/`
- referências a `replit`
- variáveis `REPLIT_*`
- previews e rotas que só fazem sentido no servidor remoto

---

### Etapa 2 — Desacoplar do servidor remoto
Revisar estes arquivos:
- `mobile/.env`
- `mobile/hooks/useApiBase.ts`
- `mobile/context/AppContext.tsx`
- `mobile/components/SystemStatus.tsx`
- `mobile/components/Terminal.tsx`
- `mobile/components/PreviewPanel.tsx`
- `mobile/app/(tabs)/terminal.tsx`
- `mobile/app/(tabs)/plugins.tsx`
- `mobile/app/(tabs)/settings.tsx`

Objetivo:
- impedir que o app dependa de um domínio remoto por padrão
- permitir modo local/offline
- esconder recursos indisponíveis quando não houver backend

---

### Etapa 3 — Modo local
O app deve funcionar minimamente com:
- projetos
- editor
- tarefas
- configurações
- importação/exportação local
- interface da IA (mesmo que parte dos recursos remotos fiquem desativados)

Recursos que podem precisar ser desativados ou adaptados:
- terminal remoto
- preview de servidor remoto
- GitHub via backend
- banco remoto
- busca web via backend
- proxy de IA via servidor

---

### Etapa 4 — Preparar para build APK
Revisar:
- `mobile/app.json`
- permissões Android
- nome do app
- ícone
- variáveis de ambiente
- dependências que exigem backend remoto

Depois:
- gerar build com EAS
- testar em Android real
- só então decidir o que será reativado localmente com Termux ou API local

---

## Resultado esperado
Ao final da primeira migração, você terá:
- um app mais limpo
- menos dependência do servidor remoto
- base pronta para APK
- espaço para futura integração local com Termux ou SQLite

---

## Observação importante
Se o app ainda estiver usando `api-server` como ponte para terminal, preview, GitHub, busca e IA, então o APK pode abrir normalmente, mas esses recursos precisam ser:
- desligados temporariamente
- ou substituídos por soluções locais

---

## Ordem prática sugerida
1. limpar estrutura
2. remover domínio remoto fixo
3. criar modo local/offline
4. esconder módulos que exigem backend
5. ajustar build EAS
6. testar APK
7. reativar recursos locais aos poucos

---

## Arquivos deste pacote
- `README.md` → visão geral
- `CHECKLIST.md` → lista de execução
- `plano-migracao.json` → plano estruturado
- `env.local.exemplo` → exemplo de configuração limpa
- `MAPA-REVISAO.md` → onde mexer no projeto
- `package-base-exemplo.json` → exemplo de referência para reorganização

Use este pacote como guia dentro do outro app/editor.