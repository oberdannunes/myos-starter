---
name: os-novo-projeto
description: Cria um projeto pessoal no myos com objetivo e próximos passos, a partir de uma conversa curta. Use quando eu quiser começar um projeto, meta ou objetivo com vários passos ("quero começar...", "vou fazer...", "me ajuda a organizar o projeto X").
argument-hint: "[descrição do projeto]"
---

# Novo projeto

Argumento recebido (o texto digitado após o comando, se houver): `$ARGUMENTS`

Conversa curta, não um formulário. O objetivo é sair com um arquivo útil e o primeiro passo claro.

1. **Área:** use a área atual se estiver dentro de `areas/<area>/`. Na raiz, sugira a área mais provável e confirme. Se o projeto tiver um repositório externo (ex.: software), preencha o campo `repositorio:`: o trabalho técnico fica lá, e aqui entram só metas pessoais, tempo e passos não técnicos.
2. **Contexto:** leia `prioridades.md`, o `AGENTS.md` da área, os projetos da área em `projetos/` e, se existir, a ideia correspondente em `areas/<area>/ideias/`.
3. **Perguntar o que faltar**, em uma rodada, no máximo 3 perguntas: o que quero alcançar, como sei que terminou e se há prazo. Se eu já disse, não pergunte de novo.
4. **Capacidade:** conte os projetos `ativo` em `projetos/`. Se o limite de `prioridades.md` estiver cheio, avise e pergunte se o novo entra como `pausado` ou se outro será pausado.
5. **Criar** `projetos/<slug>.md` a partir de `templates/projeto.md`, com o campo `area:` preenchido: objetivo, de 3 a 5 próximos passos pequenos e concretos (começando com verbo), pendências conhecidas e a linha de criação no registro. Preencha o plano só se o projeto for longo ou se eu pedir.
6. **Encerrar:** mostre o caminho do arquivo e o primeiro passo, com algo que dá para fazer em 15 minutos.
