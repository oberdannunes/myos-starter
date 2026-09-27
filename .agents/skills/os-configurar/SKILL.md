---
name: os-configurar
description: Configuração do myos depois do onboarding. Cria novas áreas, revisa as prioridades e registra repositórios externos. Use quando eu quiser criar ou reorganizar áreas, revisar prioridades.md fora da revisão trimestral ou ligar um projeto a um repositório externo.
---

# Configurar o myos

Conduza como uma conversa leve, em prosa, com poucas perguntas por vez. Não é um formulário.

## 1. Detectar o estado

- Se `.onboarding-concluido` não existir na raiz: sugira rodar `/os-onboarding` primeiro e pare, a menos que eu peça só uma parte específica.
- Senão: pergunte se quero **criar uma área nova** (passo 3), **revisar as prioridades** (passo 2) ou **ligar um repositório externo** (passo 4).

## 2. Prioridades

Entreviste-me em até 3 rodadas curtas:
1. **Valores:** o que é inegociável (família, saúde, descanso, crescimento...)?
2. **Prioridades:** quais assuntos importam mais neste trimestre, em ordem?
3. **Capacidade:** quantas horas por semana tenho, de verdade, para estudo e projetos pessoais? Há horários protegidos? Quantos projetos ativos ao mesmo tempo?

Proponha o texto preenchido, confirme comigo e grave `prioridades.md` com a data de hoje em `_Última revisão_`. Seja realista: se a capacidade informada parecer otimista, diga isso.

## 3. Áreas

- Lembre a diferença (método PARA): **área** é uma responsabilidade contínua, sem fim (ex.: `saude`, `carreira`, `familia`); **projeto** tem objetivo e termina, e fica em `projetos/`.
- A partir das prioridades, proponha áreas (nome curto em kebab-case; no onboarding, de 2 a 4) e o **papel** que você deve assumir em cada uma.
- Para cada área confirmada: copie `areas/_modelo/` para `areas/<nome>/` (o `CLAUDE.md` da área só importa o `AGENTS.md`; não o edite) e preencha o `AGENTS.md` e o título do `tarefas.md` da área com o que conversamos, deixando `TODO` onde faltar informação.
- Atualize a tabela de áreas no `AGENTS.md` da raiz e no `README.md` (removendo a linha de exemplo, se ainda estiver lá).

## 4. Repositórios externos

Pergunte se algum projeto vive num repositório externo (ex.: software). Se sim, dê acesso a ele na ferramenta em uso (no Claude Code, o caminho absoluto em `additionalDirectories` de `.claude/settings.json`; no Antigravity e no Gemini CLI, abra o repositório como pasta adicional do workspace), preencha o campo `repositorio:` do projeto e avise que a permissão vale a partir da próxima sessão.

## 5. Encerrar

Mostre um resumo curto do que mudou.
