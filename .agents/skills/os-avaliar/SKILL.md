---
name: os-avaliar
description: Só na raiz do myos. Ajuda a pensar uma ideia antes de assumir um compromisso: vale a pena agora, depois ou nunca? Registra a decisão em areas/<area>/ideias/. Use quando eu tiver uma ideia, vontade ou oportunidade nova ("estou pensando em...", "vale a pena...?") ou na triagem de ideias da inbox.
argument-hint: "[ideia]"
---

# Avaliar ideia

Argumento recebido (o texto digitado após o comando, se houver): `$ARGUMENTS`

Uma conversa franca, não uma análise formal. Descartar ou adiar com o motivo registrado é um bom resultado: evita reabrir a mesma discussão depois.

## 0. Só na raiz

Compare `pwd` com `git rev-parse --show-toplevel`. Se forem diferentes (ex.: dentro de `areas/<area>/`), não leia nem altere nada: responda numa linha que o `/os-avaliar` roda só na raiz e sugira `/os-area raiz`. Se eu estiver descrevendo um projeto ou ideia novo, ofereça anotá-lo no `inbox.md` com a data, para decidir depois na raiz.

## 1. Avaliar

1. **Contexto:** sugira a área e confirme. Leia `prioridades.md`, o `AGENTS.md` da área e os projetos `ativo` em `projetos/`. Se `areas/<area>/ideias/<slug>.md` já existir, continue a partir dele.
2. **Pensar junto**, em prosa:
   - o que eu ganho e o que custa (tempo, dinheiro, energia);
   - o que teria que pausar para caber;
   - qual é a menor versão possível para testar;
   - o que parece suposição e o que tem evidência. Questione, não só concorde.
3. **Sugerir uma decisão:** `seguir`, `depois` (com data para revisitar) ou `descartar`, com o motivo em uma linha.
4. **Registrar** em `areas/<area>/ideias/<slug>.md` a partir de `templates/ideia.md`, depois da minha confirmação. Ideia pequena demais para arquivo: registre só a decisão numa linha em `tarefas.md` ou descarte.
5. **Se for seguir:** ofereça `/os-novo-projeto` (que liga a ideia ao projeto pelos campos `ideia:` e `projeto:`), ou uma tarefa em projeto existente se for pequena.
