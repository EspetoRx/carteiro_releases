# Carteiro 1.4.1

Cliente de APIs desktop e web inicial, construído com Vue 3 e Tauri 2.

## Versão 1.4.1 — 27 de outubro de 2026

- Cancelamento de requisições HTTP em andamento, tanto no desktop (Tauri/Rust)
  quanto na web (`AbortController`).
- Novo workspace para testar HTTP, GraphQL, WebSocket, Socket.IO, gRPC, MQTT e
  SSE.
- Melhorias no estado vazio, na árvore e nos menus de Workspaces.
- Ajustes de layout nos painéis, seletores, barra de status e controles de
  janela.
- Correção da bandeira do idioma chinês simplificado.
- Reorganização dos testes em repositório independente, com cobertura e
  automação ampliadas para macOS, Windows, Linux e WSL.
- Documentação e relatórios de testes reorganizados e atualizados.

O detalhamento completo desta versão e o histórico anterior estão em
[docs/releases_notes](./releases_notes/index.md).
