---
name: os-fim-do-dia
description: Só na raiz do myos. Fecha o dia no myos. Compara o plano com o que foi feito, marca os itens concluídos, anota o que ficou para depois e destaca conquistas para o brag document. Use quando eu disser que estou encerrando o dia ou pedir o fechamento do dia.
---

# Fim do dia

Rápido: 3 a 5 minutos.

## 0. Só na raiz

Compare `pwd` com `git rev-parse --show-toplevel`. Se forem diferentes (ex.: dentro de `areas/<area>/`), não leia nem altere nada: responda numa linha que o `/os-fim-do-dia` roda só na raiz e sugira `/os-area raiz`. Se eu só estiver contando algo que fiz, registre no diário como diz o `AGENTS.md` da raiz, sem fechar o dia.

## 1. Fechar

1. **Ler** o diário de hoje em `diario/AAAA/AAAA-MM-DD.md`. Se não existir, crie-o a partir de `templates/diario.md`, sem plano.
2. **Repositórios externos:** para cada projeto `ativo` com o campo `repositorio:`, veja os commits de hoje (`git -C <repositorio> log --since=midnight --oneline --all`), sem alterar o repositório. Resuma o que não estiver no registro em uma linha por projeto (ex.: "<projeto>: 3 commits, cadastro de categorias") e inclua na pergunta do passo 3 como sugestão de registro.
3. **Perguntar**, numa rodada só: o que foi feito além do que já está no registro, o que travou e se houve alguma decisão ou descoberta importante.
4. **Atualizar:**
   - marque como `[x]`, com a data, os itens concluídos nos projetos e nos `tarefas.md`;
   - anote no registro do projeto as decisões relevantes;
   - preencha a seção "Fechamento" do diário: feito do plano, o que ficou para depois (vira prioridade do `/os-hoje` de amanhã) e uma linha sobre o dia;
   - pendências novas que surgirem: proponha onde anotar (projeto, `tarefas.md` da área ou `inbox.md`).
5. **Conquistas:** se algo feito tiver impacto profissional visível (entrega, reconhecimento, resultado mensurável), proponha registrar no brag document (ex.: `areas/carreira/notes/brag-document.md`), com a data e a evidência. Se ele ainda não existir, pergunte se quero começar um.
6. **Encerrar** em 2 linhas: o que foi feito e o que fica para amanhã. Se o plano não foi cumprido de novo pelo mesmo motivo, aponte o padrão, sem sermão.
7. **Versionar:** proponha o commit e o push das mudanças do dia (ver "Versionamento" no `AGENTS.md` da raiz).
