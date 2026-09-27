---
name: os-onboarding
description: Só na raiz do myos. Primeiro uso do myos. Apresenta o sistema, preenche as prioridades, cria as áreas e os primeiros projetos. Roda uma única vez; depois, o arquivo .onboarding-concluido bloqueia novas execuções. Use quando eu digitar /os-onboarding ou quando o myos ainda não tiver sido configurado.
---

# Onboarding

## 0. Verificar a pasta e a flag

Compare `pwd` com `git rev-parse --show-toplevel`. Se forem diferentes, responda numa linha que o `/os-onboarding` roda só na raiz e sugira `/os-area raiz`.

Se o arquivo `.onboarding-concluido` existir na raiz do repositório (`git rev-parse --show-toplevel`), **não rode o onboarding**. Responda numa linha com a data registrada nele e diga que áreas novas e revisão de prioridades ficam no `/os-configurar`. Se eu insistir em refazer, explique que basta apagar `.onboarding-concluido`, mas não apague por mim.

Se não existir, siga os passos abaixo como uma conversa leve, com poucas perguntas por vez.

## 1. Boas-vindas

Em até 6 linhas, explique:
- o myos é um assistente pessoal em arquivos Markdown: projetos, pendências, ideias, diário e revisões;
- método PARA: **área** é uma responsabilidade contínua; **projeto** tem objetivo e termina, e pertence a uma área;
- a rotina: `/os-hoje` de manhã, `/os-fim-do-dia` ao encerrar, `/os-revisao` uma vez por semana;
- o onboarding leva uns 15 minutos, e dá para parar e continuar depois (o que já foi gravado fica).

## 2. Sobre você

Pergunte meu nome e se quero ajustar algo no jeito do assistente (idioma, tom, quanto deve cobrar). Grave no `AGENTS.md` da raiz: o nome na frase de abertura ("o seu sistema pessoal" → "o sistema pessoal de <nome>") e os ajustes na seção "Seu papel".

## 3. Prioridades, áreas e repositórios externos

Siga os passos **2 (Prioridades)**, **3 (Áreas)** e **4 (Repositórios externos)** de `.claude/skills/os-configurar/SKILL.md`.

## 4. O que já está em andamento

Pergunte o que ocupa a minha cabeça hoje: projetos em curso, pendências, ideias.
- Objetivo com vários passos → crie o projeto como no `/os-novo-projeto`, respeitando o limite de projetos ativos de `prioridades.md`. No máximo 3 agora; o resto vai para o `inbox.md`.
- Pendência avulsa → `areas/<area>/tarefas.md`.
- Ideia incerta ou solta → `inbox.md`, com a data de hoje, para a primeira `/os-revisao`.

## 5. Privacidade

Rode `git remote -v`. Se o remote ainda apontar para o repositório do template, ou se `gh repo view --json visibility` indicar `PUBLIC`, avise: o myos guarda diário, saúde e carreira, e deve ficar num repositório **privado**. Não altere o remote por mim.

## 6. Concluir

1. Crie `.onboarding-concluido` na raiz com o conteúdo:
   ```
   Onboarding concluído em AAAA-MM-DD.
   Este arquivo impede que o /os-onboarding rode de novo. Para áreas novas ou revisar prioridades, use /os-configurar.
   ```
2. Mostre um resumo curto: prioridades, áreas criadas, projetos criados e o que foi para a inbox.
3. Sugira o próximo passo concreto: rodar `/os-hoje` agora (ou amanhã cedo) e marcar a primeira `/os-revisao` no fim da semana.
