# Carteiro

<p align="center">
  <img src="carteiro.png" alt="Carteiro" width="120" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Em%20desenvolvimento-orange?logo=githubactions&logoColor=white" alt="Em desenvolvimento" />
  <img src="https://img.shields.io/badge/Main-stable-success?logo=git&logoColor=white" alt="Main stable" />
  <img src="https://img.shields.io/badge/Version-0.2.0-blue?logo=semver&logoColor=white" alt="Version 0.2.0" />
  <img src="https://img.shields.io/badge/Vue-3-4FC08D?logo=vue.js&logoColor=white" alt="Vue 3" />
  <img src="https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Tauri-2-24C8DB?logo=tauri&logoColor=white" alt="Tauri 2" />
  <img src="https://img.shields.io/badge/Vite-6-646CFF?logo=vite&logoColor=white" alt="Vite" />
</p>

Carteiro é um cliente desktop para testes de APIs HTTP, pensado para ser leve, rápido e focado em produtividade. A aplicação funciona como uma alternativa minimalista para ferramentas como Postman e Insomnia, porém com a proposta de ser mais enxuta e nativa, rodando em desktop com Vue + Tauri.

Ele permite criar, organizar, testar e exportar requisições HTTP em um ambiente simples e direto, com suporte a múltiplas abas, workspaces, ambientes e variáveis de ambiente, além de salvar históricos e coleções locais.

## O que a aplicação faz hoje

### Requisições HTTP

- Envio de requisições com os principais métodos HTTP: `GET`, `POST`, `PUT`, `PATCH` e `DELETE`
- Campo de URL dinâmico com suporte a manipulação e edição rápida
- Configuração de parâmetros de query string e headers
- Suporte a corpo de requisição em diferentes contextos, com edição direta no editor
- Autenticação configurável por requisição

### Organização e produtividade

- Múltiplas abas de requisições em execução simultânea
- Gerenciamento de workspaces e pastas para organizar chamadas por projeto
- Histórico de requisições recentes
- Salvamento de solicitações e exportação para arquivos/coleção
- Ambiente e variáveis configuráveis para reutilização de valores em múltiplas requisições

### Respostas e análise

- Exibição do status HTTP e tempo de resposta
- Visualização do corpo de retorno com destaque/formatador JSON
- Modo visual de preview para conteúdos HTML
- Busca e filtro do conteúdo de resposta para facilitar inspeção
- Informações de erro quando a requisição falha

### Desktop e experiência local

- Interface desktop executando com Tauri
- Experiência leve, sem depender de um navegador para o uso principal
- Estrutura modular e organizada para expansão futura

## Pilha tecnológica

- [Vue 3](https://vuejs.org/)
- [TypeScript](https://www.typescriptlang.org/)
- [Vite](https://vitejs.dev/)
- [Tauri 2](https://tauri.app/)
- [Monaco Editor](https://microsoft.github.io/monaco-editor/)

## Como usar

### Executar localmente

```bash
npm install
npm run dev
```

Ou, se preferir usar pnpm:

```bash
pnpm install
pnpm dev
```

### Compilar localmente

```bash
cargo build --manifest-path src-tauri/Cargo.toml
```

## Download dos binários

> Acesse as Releases do projeto no GitHub para baixar os executáveis já compilados para seu sistema operacional.

Clique na aba de Releases na página do repositório e escolha o arquivo compatível com seu ambiente (Windows, macOS ou Linux). Isso evita a necessidade de compilar o projeto manualmente.

## Status do projeto

O projeto está em desenvolvimento ativo e a funcionalidade principal de cliente HTTP já está em uso, com foco em evoluir para uma ferramenta mais completa de testes e organização de APIs.

## Contribuição

Contribuições são bem-vindas. Se você quiser melhorar a interface, adicionar suporte a novos payloads, aprimorar a experiência de trabalho com collections ou ajustar a arquitetura do app, fique à vontade para abrir issues ou pull requests.

## Badges de Status

### Vibecoded With: Llama 3.1 8B

![Badge de Vibecoded](https://img.shields.io/badge/Vibecoded-Integrado%20com%20Llama-orange?logo=vibecoded&logoColor=white)

### Gemini 3.5 Flash-Light

![Badge de Gemini](https://img.shields.io/badge/Gemini-3.5%20Flas%20Light-green?logo=gemini&logoColor=white)

### Copilot 2.5 Free

![Badge de Copilot](https://img.shields.io/badge/Copilot-2.5%20free%20used-blue?logo=copilot&logoColor=white)
