# myos

Um assistente pessoal para acompanhar projetos, pendências, ideias e estudos, organizado por áreas, com o [Claude Code](https://claude.com/claude-code). Tudo fica em arquivos Markdown nesta pasta; o agente lê e escreve esses arquivos seguindo as regras do [CLAUDE.md](CLAUDE.md).

A organização segue o método **PARA**: uma **área** é uma responsabilidade contínua (saúde, carreira, família...); um **projeto** tem objetivo e termina, e pertence a uma área.

## Comece aqui

1. **Crie o seu repositório a partir deste template**, de preferência **privado**: ele vai guardar informação pessoal.
2. **Abra a pasta no Claude Code** e digite `/os-onboarding`. O agente apresenta o sistema e conversa com você para preencher as [prioridades](prioridades.md) (valores, prioridades do momento e tempo disponível), criar as suas áreas a partir de [areas/_modelo/](areas/_modelo/) e registrar os primeiros projetos. Ele roda uma vez só: ao final, cria o arquivo `.onboarding-concluido`, que impede uma nova execução.
3. **Depois**, use `/os-novo-projeto` para projetos novos e jogue ideias soltas em [inbox.md](inbox.md).
4. **No dia a dia**, use `/os-hoje` de manhã e `/os-fim-do-dia` ao encerrar.
5. **Uma vez por semana**, rode `/os-revisao`.

Se quiser, ajuste o [CLAUDE.md](CLAUDE.md) ao seu jeito: o papel do assistente, o idioma e as convenções.

## Como usar

Abra o Claude Code **dentro da área** em que quer trabalhar. O contexto da área é carregado junto com o global:

```bash
cd myos/areas/<area> && claude
```

Abrindo na raiz, você trabalha na visão geral: inbox, revisão semanal de todas as áreas e prioridades. Para trocar de área no VS Code, use `/os-area <nome>`.

Não precisa de comando para tudo: "anota que preciso...", "o que falta no projeto X?" ou "me ajuda com o currículo" também funcionam.

## Rotina

```
captura (inbox.md, fontes/) ─▶ ideia (/os-avaliar) ─▶ projeto (/os-novo-projeto) ─▶ arquivo/

dia:      /os-hoje (plano) ─▶ registro no diário ─▶ /os-fim-do-dia (fechamento)
semana:   /os-revisao (lê os diários, triagem, arquivamento, foco)
trimestre: revisão de prioridades.md, disparada pelo /os-revisao
```

| Comando | O que faz |
|---|---|
| `/os-onboarding` | Primeiro uso: apresenta o sistema, preenche as prioridades e cria as áreas (roda uma vez só) |
| `/os-configurar` | Cria áreas novas, revisa as prioridades ou liga um repositório externo |
| `/os-novo-projeto` | Cria um projeto com objetivo e próximos passos |
| `/os-avaliar` | Ajuda a decidir se uma ideia vale a pena agora, depois ou nunca |
| `/os-hoje` | Escolhe de 1 a 3 coisas para o dia e abre o diário |
| `/os-fim-do-dia` | Fecha o dia: o que foi feito, o que fica para amanhã e conquistas |
| `/os-revisao` | Revisa o andamento, faz a triagem da inbox, arquiva o que terminou e registra em `reviews/` |
| `/os-ingerir` | Lê um arquivo de `fontes/inbox/`, arquiva o original e grava o conteúdo na área certa |
| `/os-area <nome>` | Troca de área: abre a pasta numa nova janela do VS Code, com conversa limpa |

## Estrutura

| Onde | O quê |
|---|---|
| `.onboarding-concluido` | Flag criada ao fim do `/os-onboarding`; não apague |
| [prioridades.md](prioridades.md) | Valores, prioridades do momento e capacidade semanal |
| [projetos/](projetos/) | Um arquivo por projeto, com a área a que pertence: objetivo, próximos passos, pendências e registro |
| `areas/<area>/CLAUDE.md` | Contexto da área e o papel do assistente nela |
| `areas/<area>/tarefas.md` | Pendências avulsas da área |
| `areas/<area>/ideias/` | Ideias pensadas, inclusive as descartadas |
| `areas/<area>/notes/` | Referências, listas de estudo, currículo, anotações |
| [areas/_modelo/](areas/_modelo/) | Modelo usado para criar áreas novas |
| [arquivo/](arquivo/) | Projetos concluídos ou abandonados |
| [diario/](diario/) | Um arquivo por dia: plano, registro e fechamento |
| [inbox.md](inbox.md) | Ideias e lembretes de uma linha, triados na revisão semanal |
| [fontes/](fontes/) | Arquivos para ler e organizar (chats, transcrições, documentos), processados com `/os-ingerir` |
| [reviews/](reviews/) | Revisões semanais |
| [templates/](templates/) | Modelos de projeto, ideia, diário, revisão e ficha de fonte |

## Áreas (`areas/`)

| Pasta | Assunto |
|---|---|
| _(criadas pelo `/os-onboarding`)_ | |

## Projetos com repositório externo

Um projeto pode apontar para outro repositório (campo `repositorio:`, ex.: um software que você desenvolve). O trabalho técnico vive lá; o myos só lê para acompanhar o progresso. Adicione o caminho em `additionalDirectories` de [.claude/settings.json](.claude/settings.json).

## Privacidade

- Use um repositório **privado**: diário, saúde e carreira são informação pessoal.
- O material bruto de `fontes/inbox/` e `fontes/originais/` fica fora do git (ver [fontes/README.md](fontes/README.md)).
