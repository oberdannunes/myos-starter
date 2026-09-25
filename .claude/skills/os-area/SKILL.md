---
name: os-area
description: Troca de área no myos abrindo a pasta da área numa nova janela do VS Code, com uma conversa limpa e só o contexto daquela área. Uso: /os-area <nome> (ex.: /os-area carreira), /os-area raiz para a visão global, ou /os-area sem argumento para listar.
disable-model-invocation: true
argument-hint: "[area | raiz]"
---

# Trocar de área

Argumento recebido: `$ARGUMENTS`

A raiz do myos é o topo deste repositório (`git rev-parse --show-toplevel`).

1. **Sem argumento:** liste as pastas em `areas/`, exceto `_modelo` (uma linha cada, com a descrição da tabela de áreas do `CLAUDE.md` da raiz) e pergunte para qual trocar.
2. **`raiz` ou `myos`:** o destino é a raiz do myos.
3. **Nome de área:** o destino é `areas/<nome>`. Aceite correspondência parcial (ex.: `saud` para `saude`). Se não houver correspondência ou houver mais de uma, liste as opções e pergunte.
4. Abra o destino com `code "<caminho absoluto>"`. Se a pasta já estiver aberta numa janela, o VS Code apenas a traz para frente.
5. Responda numa linha: a área aberta e a orientação para abrir o chat do Claude na nova janela. Não faça mais nada nesta conversa.
