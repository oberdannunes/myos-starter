---
name: os-ingerir
description: Ingere material bruto de fontes/inbox/ no myos (chats, transcrições, documentos, e-mails, artigos). Lê a fonte, confirma a área, arquiva o original, cria a ficha em fontes/registros/ e grava o conteúdo útil na área. Use quando eu disser que coloquei algo na inbox de fontes, pedir para ler, resumir ou arquivar um material, ou na triagem de fontes pendentes.
argument-hint: "[arquivo em fontes/inbox/ | vazio para listar]"
---

# Ingerir fonte

Argumento recebido: `$ARGUMENTS`

Rode na raiz do myos (a ingestão escreve em qualquer área). O fluxo e as convenções estão em `fontes/README.md`.

## 1. Identificar a fonte

- **Sem argumento:** liste os arquivos em `fontes/inbox/` (exceto `.gitkeep`) e pergunte qual ingerir. Se estiver vazia, diga isso e pare.
- **Com argumento:** a fonte precisa estar em `fontes/inbox/`. Se estiver em outro lugar, peça para movê-la para lá antes de continuar.
- Uma pasta ou um conjunto de arquivos sobre o mesmo assunto conta como **uma** fonte.

## 2. Ler e extrair

Leia o conteúdo inteiro e extraia:
- tema principal;
- fatos, decisões e aprendizados;
- ações ou pendências;
- referências úteis (links, livros, pessoas, com o papel delas);
- dados sensíveis (senhas, tokens, chaves, documentos pessoais, dados de terceiros).

Não invente o que não está na fonte. Marque interpretações como `SUPOSIÇÃO`.

## 3. Definir a área

- Liste as pastas em `areas/` (exceto `_modelo`) e use a descrição da tabela de áreas do `CLAUDE.md` da raiz.
- Se a área for clara, proponha-a. Se não for, pergunte: "Essa informação pertence a qual área?" e ofereça as opções.
- Se não couber em nenhuma área, diga isso e sugira criar uma área nova ou deixar só a ficha, sem forçar a classificação.
- Se a fonte for sobre um projeto com **repositório externo** (campo `repositorio:`, ex.: um software que você desenvolve), grave no myos apenas a visão pessoal (metas, tempo, motivação). Conteúdo de produto vai como sugestão para o repositório, que eu aplico lá.

## 4. Propor e confirmar

Antes de gravar, mostre numa lista curta: a área, o slug (`FNT-AAAA-MM-DD-slug`, com a data da fonte ou, se não houver, a de hoje), o que vai para a nota da área e as ações sugeridas. **Espere minha confirmação.**

## 5. Gravar

1. **Original:** mova de `fontes/inbox/` para `fontes/originais/AAAA/FNT-AAAA-MM-DD-slug.ext`, preservando o conteúdo sem edição. Esta pasta fica fora do git (`.gitignore`).
2. **Ficha:** crie `fontes/registros/FNT-AAAA-MM-DD-slug.md` a partir de `templates/fonte.md`. A ficha é curta e aponta para a nota da área; não repita o conteúdo.
3. **Área:** grave o conteúdo útil em `areas/<area>/notes/`. Prefira atualizar uma nota existente do mesmo tema (ex.: `notes/feedbacks.md`, `notes/lista-de-estudo.md`) em vez de criar outra. Nota nova: `notes/<tema>.md`, com link para a ficha.
4. **Ações:**
   - passo de um projeto existente → proponha incluí-lo nos próximos passos de `projetos/<slug>.md`;
   - pendência avulsa → proponha incluí-la em `areas/<area>/tarefas.md`;
   - objetivo novo → ofereça `/os-novo-projeto`; ideia ainda incerta → ofereça `/os-avaliar`;
   - captura sem destino claro → adicione ao `inbox.md`.

Nada que é gravado na ficha, na nota ou no `inbox.md` pode conter os dados sensíveis identificados no passo 2: omita-os ou substitua por `[removido]`.

## 6. Encerrar

Responda em 4 linhas:
1. Área.
2. Original em `fontes/originais/AAAA/...`.
3. Ficha em `fontes/registros/...`.
4. Onde o conteúdo foi gravado e as ações sugeridas (e o que ficou pendente de confirmação).
