# Fontes

Material bruto que precisa ser lido e organizado: chats, transcrições de reuniões, documentos, e-mails, artigos e referências. O conhecimento extraído vai para a área certa; aqui ficam o original e uma ficha de rastreio.

**Diferença para o `inbox.md`:** o `inbox.md` guarda ideias e lembretes de uma linha. Um **arquivo** a ser lido vem para `fontes/inbox/`.

| Pasta | Uso | No git? |
|---|---|---|
| [inbox/](inbox/) | Material recebido, ainda não lido. Qualquer formato legível (`.md`, `.txt`, `.vtt`, `.pdf`, `.docx`, `.eml`, `.html`...). | Não |
| [originais/AAAA/](originais/) | O original, sem edição, depois da ingestão: `FNT-AAAA-MM-DD-slug.ext`. | Não |
| [registros/](registros/) | Uma ficha por fonte (`FNT-AAAA-MM-DD-slug.md`, modelo em [templates/fonte.md](../templates/fonte.md)): resumo, área e link para onde o conteúdo foi gravado. | Sim |

`inbox/` e `originais/` ficam fora do git porque o material bruto pode ter dados sensíveis. Faça backup dessa pasta por outro meio se quiser guardar os originais.

## Fluxo

```
fontes/inbox/ ─/os-ingerir─▶ leitura ─▶ área (pergunta se ambígua) ─▶ confirmação
    ├─▶ original movido para originais/AAAA/
    ├─▶ ficha em registros/
    └─▶ conteúdo em areas/<area>/notes/ ─▶ ações: passo de projeto, tarefas.md, novo projeto, ideia ou inbox.md
```

## Regras

- O original é preservado intacto; os dados sensíveis são removidos do que vai para a ficha e para as notas.
- A ficha é curta e aponta para a nota da área; o conteúdo não é duplicado.
- Ações que surgirem vão para o projeto ou para o `tarefas.md` da área; objetivos novos viram sugestão de `/os-novo-projeto` ou `/os-avaliar`.
- Área ambígua: pergunte antes de gravar. Não force uma classificação.
- Fontes paradas em `inbox/` aparecem na revisão semanal (`/os-revisao`).

## Exemplos de classificação

Supondo áreas `carreira`, `estudo` e `familia`:

- Conversa sobre oportunidades de carreira → `carreira`
- Artigo sobre um tema que você está estudando → `estudo`
- Discussão sobre metas ou tempo dedicado a um projeto com repositório externo → o arquivo do projeto em `projetos/`, na área dele (conteúdo de produto vai para o repositório do projeto)
