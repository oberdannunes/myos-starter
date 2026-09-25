---
name: os-revisao
description: Faz a revisão semanal do myos. Revisa o andamento dos projetos e pendências, faz a triagem da inbox, arquiva o que terminou, define o foco da próxima semana e registra em reviews/. Também dispara a revisão trimestral das prioridades quando ela estiver vencida. Use quando eu pedir revisão semanal, retrospectiva ou planejamento da semana.
---

# Revisão semanal

## 1. Escopo

- Na raiz do myos: revisão **global** (todas as pastas em `areas/`, exceto `_modelo`, triagem da `inbox.md` e de `fontes/inbox/`).
- Dentro de `areas/<area>/`: revisão **só daquela área** (sem inbox).

## 2. Coletar

- Leia `prioridades.md` e a revisão mais recente em `reviews/`, para comparar com o foco da semana anterior.
- Leia os diários da semana em `diario/AAAA/`: planos, registros e fechamentos. É a principal fonte do que foi feito.
- Leia os projetos `ativo` e `pausado` em `projetos/` (na revisão de área, só os com `area:` igual à área) e as pendências de `areas/*/tarefas.md` no escopo.
- Projetos com **repositório externo** (campo `repositorio:`): veja o andamento no repositório (tarefas, `git log`), sem alterá-lo, e compare com as metas pessoais do projeto.
- Ideias com decisão `depois` cuja data `revisitar_em` já passou.

## 3. Conversar

Mostre primeiro o que os diários já dizem que foi feito. Depois, uma rodada só, curta:
- Falta algo que não está nos diários?
- O que travou?
- Mudou alguma prioridade?

Atualize os checkboxes e os registros dos projetos conforme as respostas.

## 4. Analisar

- Andamento de cada projeto e se o próximo passo está claro. Projeto sem próximo passo: proponha um.
- Projetos parados há 2 semanas ou mais: sugira retomar com um passo pequeno, pausar ou concluir.
- Itens adiados em vários dias seguidos nos diários: aponte o padrão e o que parece estar sendo evitado.
- O foco da semana anterior foi cumprido? Se não, por quê?
- Carga em relação à capacidade de `prioridades.md`. Seja direto se estiver acima.
- Áreas sem nenhuma atividade no mês: pergunte se está tudo bem assim ou se merecem um passo na próxima semana.
- Ideias para revisitar: traga-as para decisão.

## 5. Triagem da inbox (só na revisão global)

Para cada item da `inbox.md`, proponha: próximo passo de um projeto, pendência em `tarefas.md` de uma área, novo projeto (`/os-novo-projeto`), ideia para pensar (`/os-avaliar`), nota em `areas/<area>/notes/` ou descarte. Aplique após minha confirmação e limpe os itens triados.

Liste também os arquivos pendentes em `fontes/inbox/` (exceto `.gitkeep`) e sugira processá-los com `/os-ingerir`.

**Destaque os itens envelhecidos:** itens da `inbox.md` com data de mais de 14 dias e arquivos em `fontes/inbox/` modificados há mais de 14 dias. Para eles, a decisão é agora: encaixar em algum lugar ou descartar.

## 6. Arquivar

- Projetos `concluido`, ou `pausado` sem atividade há mais de 2 meses: proponha mover de `projetos/` para `arquivo/`. Ao mover, anote a data e o motivo no registro do projeto.
- Nada é apagado: o arquivo existe para consultar depois (ex.: brag document, currículo, projetos parecidos).

## 7. Revisão trimestral

Se a data de `_Última revisão_` em `prioridades.md` tiver mais de 90 dias, avise e ofereça fazer a revisão trimestral agora ou marcar para a próxima semana. Nela:
- releia valores, prioridades do momento e capacidade, comparando com o que os últimos três meses de revisões mostram;
- para cada prioridade: manter, reescrever ou retirar;
- revise se as áreas continuam fazendo sentido (alguma a criar ou a encerrar?);
- atualize `prioridades.md` e a data de `_Última revisão_`.

## 8. Registrar

- Crie `reviews/AAAA-Www.md` (semana ISO atual) a partir de `templates/review.md`. Na revisão de área, use `reviews/AAAA-Www-<area>.md`.
- Defina **no máximo 3** focos para a próxima semana, cada um ligado a um passo concreto.
- Se as prioridades mudaram, proponha o ajuste em `prioridades.md`.

## 9. Encerrar

Mostre um resumo curto: o que foi feito, alertas e os 3 focos da semana.
