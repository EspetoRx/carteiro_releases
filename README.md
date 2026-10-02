# Carteiro

<p align="center">
  <img src="carteiro.png" alt="Carteiro" width="120" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Em%20desenvolvimento-orange?logo=githubactions&logoColor=white" alt="Em desenvolvimento" />
  <img src="https://img.shields.io/badge/Version-0.6.0-blue?logo=semver&logoColor=white" alt="Versão 0.6.0" />
  <img src="https://img.shields.io/badge/Vue-3-4FC08D?logo=vue.js&logoColor=white" alt="Vue 3" />
  <img src="https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Tauri-2-24C8DB?logo=tauri&logoColor=white" alt="Tauri 2" />
  <img src="https://img.shields.io/badge/Vite-6-646CFF?logo=vite&logoColor=white" alt="Vite" />
</p>

O Carteiro é um cliente desktop para criar, enviar e organizar requisições HTTP. A interface Vue 3 roda sobre Tauri 2, com um backend Rust responsável pelo transporte HTTP e pelas integrações nativas do aplicativo.

## Instalação da aplicação

### macOS

Utilize o comando abaixo caso seja indicado que o APP não foi assinado ou que esteja corrompido.

```bash
xattr -cr /Applications/Carteiro.app
```

### Windows

Não se esqueça de autorizar a execução da aplicação que foi baixada da internet.

## Funcionalidades

### Requests HTTP

- Envie `GET`, `POST`, `PUT`, `PATCH` e `DELETE`.
- Configure URL, query params, headers, autenticação e body.
- Edite bodies JSON, texto ou `application/x-www-form-urlencoded` com o Monaco Editor.
- Ative ou desative linhas de parâmetros e headers sem removê-las.
- Use variáveis `{{chave}}` em URLs, parâmetros, headers, autenticação, body e scripts.
- Execute scripts JavaScript pre-request antes da chamada e scripts de teste depois da resposta. Os scripts podem ler e atualizar variáveis de ambiente e verificar status e conteúdo da resposta.

### Autenticação e headers

- Configure Bearer Token, JWT Bearer, OAuth 2.0 por token, Basic Auth, API Key e Digest Auth.
- O formulário também apresenta opções de OAuth 1.0, Hawk, AWS Signature, NTLM e EdgeGrid; valide a compatibilidade com o esquema e o provedor usados antes de depender delas.
- Inspecione headers padrão e gerados pelo transporte, como `Host`, `User-Agent`, `Accept` e `Content-Type`.
- Use o Cookie Manager local para inspecionar cookies, capturar `Set-Cookie` e enviar cookies compatíveis com domínio, path, segurança e expiração.

### Respostas

- Consulte status HTTP, duração, headers e corpo da resposta.
- Formate e copie respostas textuais e JSON; pesquise conteúdo no body e no preview HTML.
- Visualize HTML e imagens no painel de preview. PDFs podem abrir em viewer inline conforme o suporte do WebView do sistema.
- Preserve respostas binárias sem convertê-las em texto e baixe respostas textuais ou arquivos, usando o nome informado pelo servidor quando disponível.

### Workspaces, abas e histórico

- Separe projetos em workspaces com pastas, requests salvas, ambientes e flows.
- Mantenha várias requests e flows em abas; crie, duplique, renomeie, mova, reordene e feche abas individualmente ou em grupo.
- Reordene e mova requests e pastas na coleção do workspace.
- Reabra chamadas do histórico, que registra os dados necessários para recuperar a request, além de status e duração quando disponíveis.
- Alterações em uma aba vinculada a uma request salva são sincronizadas com o item da coleção.

### Ambientes e flows

- Crie ambientes para desenvolvimento, staging, produção ou outros contextos, com variáveis habilitadas ou desabilitadas.
- Escolha o ambiente ativo e reutilize os valores em requests, scripts e snippets.
- Monte flows sequenciais a partir de requests da coleção. Configure delays e repetições; pause, retome ou interrompa uma execução.
- Inspecione resultados por etapa, incluindo status, duração, testes e downloads de resposta. Os resultados de execução podem ser exportados em JSON.
- O Cookie Manager é compartilhado entre requests manuais e etapas de flows.

### Arquivos e código

- Importe e exporte requests em `.creq`, workspaces em `.cwsk`, ambientes em `.cenv` e flows em `.cflw`.
- Abra arquivos na aplicação e escolha se deseja habilitar autosave no arquivo de origem. Com autosave desabilitado, as alterações permanecem apenas no estado local do aplicativo.
- Salve requests preservando variáveis ou substituindo-as pelos valores do ambiente atual.
- Gere e copie código para cURL, JavaScript Fetch, JavaScript Axios e Python Requests, preservando placeholders ou resolvendo variáveis.
- Baixe respostas para arquivos pelo diálogo nativo no desktop.

### Interface e armazenamento

- Alterne entre tema claro, escuro e do sistema.
- Idiomas disponíveis: 🇺🇸 English, 🇧🇷 Português (Brasil), 🇪🇸 Español, 🇫🇷 Français, 🇨🇳 简体中文 e 🇯🇵 日本語.
- Use menus nativos e da aplicação para comandos de requests, workspaces, ambientes, flows e histórico.
- Consulte o estado da request e métricas disponíveis na barra de status.
- Requests, abas, workspaces, ambientes, histórico, preferências e cookie jar são mantidos localmente no perfil da aplicação. O cookie jar não é incluído nos arquivos exportados.

> O Carteiro é um cliente de API, não um cofre de segredos. Revise credenciais antes de compartilhar arquivos `.creq`, `.cwsk`, snippets, histórico ou capturas de tela.

## Tecnologias

- [Vue 3](https://vuejs.org/) e TypeScript
- [Vite](https://vite.dev/)
- [Tauri 2](https://tauri.app/) e Rust
- [Monaco Editor](https://microsoft.github.io/monaco-editor/)
- `reqwest` para o transporte HTTP no backend

## Executar em desenvolvimento

Pré-requisitos: Node.js, pnpm, Rust e as dependências de sistema exigidas pelo Tauri 2 para sua plataforma. Consulte o [guia de pré-requisitos do Tauri](https://tauri.app/start/prerequisites/).

```bash
pnpm install
pnpm dev
```

Para abrir a aplicação desktop durante o desenvolvimento:

```bash
pnpm tauri dev
```

Para compilar o backend Rust isoladamente:

```bash
cargo build --manifest-path src-tauri/Cargo.toml
```

Os comandos de empacotamento do aplicativo podem ser executados pelo CLI do Tauri, conforme a configuração e as dependências instaladas para cada plataforma.

## Documentação

A documentação incorporada à aplicação detalha requests, respostas, autenticação, headers e cookies, ambientes, workspaces, flows, histórico, arquivos, snippets, preferências, segurança e solução de problemas. A árvore de código-fonte também está em [docs/source-tree.md](docs/source-tree.md).

## Contribuição

Contribuições são bem-vindas. Abra uma issue para discutir mudanças maiores ou envie um pull request com uma descrição objetiva do comportamento alterado e das verificações realizadas.
