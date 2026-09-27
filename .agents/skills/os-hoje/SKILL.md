---
name: os-hoje
description: Só na raiz do myos. Planejamento do dia no myos. Escolhe de 1 a 3 coisas concretas entre os projetos ativos e as tarefas avulsas, alinhadas ao foco da semana e ao tempo disponível hoje, e abre o diário do dia. Use quando eu perguntar o que fazer hoje, pedir o plano do dia, disser "bom dia" pedindo planejamento ou disser que tenho X horas livres.
---

# Hoje

Responda rápido: é um ritual de 2 minutos, não uma revisão.

## 0. Só na raiz

Compare `pwd` com `git rev-parse --show-toplevel`. Se forem diferentes (ex.: dentro de `areas/<area>/`), não leia nem altere nada: responda numa linha que o `/os-hoje` roda só na raiz e sugira `/os-area raiz`.

## 1. Planejar

1. **Ler:**
   - o foco da semana na revisão mais recente em `reviews/`;
   - o diário do último dia registrado em `diario/`: o que ficou para depois e o que não foi fechado;
   - os próximos passos pendentes (`[ ]` e `[~]`) dos projetos `ativo` em `projetos/` e as pendências de `areas/*/tarefas.md`, de todas as áreas. Para projetos com repositório externo (campo `repositorio:`), veja as tarefas em andamento no repositório;
   - a seção `## Recorrentes` do `AGENTS.md` de cada área: o que vence hoje ou nos próximos 7 dias e os hábitos da semana.
2. Se eu não disse quanto tempo tenho hoje, pergunte (uma única pergunta).
3. Sugira **de 1 a 3 itens**, nesta ordem de prioridade: o que ficou para depois ontem, o que está `[~]` em andamento, o foco da semana, o que tem prazo próximo (`(prazo: AAAA-MM-DD)` nas tarefas, `prazo:` nos projetos) e pendências que bloqueiam outras coisas. Recorrentes que vencem hoje entram como lembrete, fora da conta dos 3 itens, a menos que tomem tempo relevante. Respeite o tempo informado. Se eu estiver enchendo o dia além do que cabe ou adiando a mesma coisa há dias, diga.
4. Para cada item: de onde vem (projeto ou tarefas da área), o que é "feito" e um primeiro passo de 5 minutos.
5. Depois da minha confirmação, crie `diario/AAAA/AAAA-MM-DD.md` a partir de `templates/diario.md` com o plano. Se o arquivo já existir, só atualize a seção "Plano".
6. Se não houver revisão desta semana, sugira rodar `/os-revisao`.
