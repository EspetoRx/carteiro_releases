# Carteiro

<p align="center">
  <img src="carteiro-wordmark.png" alt="Carteiro" width="400" />
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Status-Em%20desenvolvimento-orange?logo=githubactions&logoColor=white" alt="Em desenvolvimento" />
  <img src="https://img.shields.io/badge/Version-1.4.1-blue?logo=semver&logoColor=white" alt="Versão 1.4.1" />
  <img src="https://img.shields.io/badge/Vue-3-4FC08D?logo=vue.js&logoColor=white" alt="Vue 3" />
  <img src="https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white" alt="TypeScript" />
  <img src="https://img.shields.io/badge/Tauri-2-24C8DB?logo=tauri&logoColor=white" alt="Tauri 2" />
  <img src="https://img.shields.io/badge/Vite-6-646CFF?logo=vite&logoColor=white" alt="Vite" />
</p>

O Carteiro é um cliente de APIs com aplicação desktop para Windows, macOS e Linux e uma versão web inicial. A interface Vue 3 é compartilhada: no desktop, Tauri 2 e Rust fornecem transporte HTTP e integrações nativas; na web, as chamadas partem diretamente do navegador do usuário. O suporte completo a HTTP, WebSocket, Socket.IO, GraphQL, gRPC, MQTT e EventStream (SSE) continua na versão desktop, sujeito aos requisitos de cada protocolo.

## Instalação da aplicação

### macOS

#### Via Homebrew

```bash
# Adicione o repositório
brew tap EspetoRx/casks
# Confie na cask
brew trust --cask espetorx/casks/carteiro
# OU no repositório global
brew trust espetorx/casks
# Instale a aplicação
brew install --cask carteiro
```

#### Via DMG

Baixe o arquivo e o copie para dentro da pasta de Applications.

#### Após Instalar

Utilize o comando abaixo caso seja indicado que o APP não foi assinado ou que esteja corrompido.

```bash
xattr -cr /Applications/Carteiro.app
```

#### Para desinstalar

Para desinstalar use:

```bash
brew uninstall --cask carteiro
```

ou ainda se quiser fazê-lo removendo os arquivos de cache:

```bash
brew uninstall --cask --zap carteiro
```

ou ainda pela Interface Gráfica:

1. Abra o finder.
2. Vá na pasta aplicativos.
3. Encontre o ícone do carteiro.
4. Arraste-o para o Lixo ou clique com o botão direito e selelcione Mover para o Lixo.

### Windows

Não se esqueça de autorizar a execução da aplicação que foi baixada da internet.

## Funcionalidades

### Requests HTTP

- Envie `GET`, `POST`, `PUT`, `PATCH`, `DELETE`, `OPTIONS`, `HEAD`, `TRACE`, `CONNECT` ou informe um método personalizado.
- `POST`, `PUT`, `PATCH`, `DELETE`, `OPTIONS` e métodos personalizados podem enviar body; `GET`, `HEAD`, `TRACE` e `CONNECT` não enviam body pelo fluxo normal.
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
- No menu Requisições, **Salvar Todas as Requisições Não Vinculadas na Coleção** adiciona as abas de requisição ainda não vinculadas à raiz do workspace ativo, tanto no desktop quanto na web. Abas já salvas, flows, configurações e editores Git não são adicionados. **Salvar Várias Requisições em Pasta...** continua sendo a exportação de arquivos do desktop.

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

- Redimensione livremente os blocos da interface: ajuste a proporção entre Requisição e Resposta (tanto no modo vertical quanto horizontal/lado a lado) e a altura do Terminal em relação ao bloco de conteúdo. Suporta teclado, duplo clique para redefinir e persistência das dimensões.
- Alterne entre tema claro, escuro e do sistema. Os temas disponíveis são Light Mode default, Light Monochrome, Light Pastel, Catppuccin Latte, VS Code Light, Dark Mode default, Dark Monochrome, Dark Pastel, Catppuccin Frappe, Catppuccin Macchiato, Catppuccin Mocha, Nord e VS Code Dark.
- Idiomas disponíveis: English, Português (Brasil), Español, Français, 简体中文, 日本語, Deutsch, Italiano, Nederlands, Русский, 한국어, 繁體中文, العربية, हिन्दी, Türkçe, Polski, Українська, Svenska, Dansk, Norsk, Suomi, Čeština, Ελληνικά, العربية (فلسطين), Bahasa Indonesia e ไทย.
- Use menus nativos e da aplicação para comandos de requests, workspaces, ambientes, flows e histórico.
- Consulte o estado da request e métricas disponíveis na barra de status.
- Requests, abas, workspaces, ambientes, histórico, preferências e cookie jar são mantidos localmente no perfil da aplicação. O cookie jar não é incluído nos arquivos exportados.

### Dev Tools e terminal

- Abra o painel em **Visualizar → Dev Tools** ou pelo botão Dev Tools na barra de status. O mesmo comando está no menu nativo Tauri.
- Inicie várias sessões interativas do shell do sistema, alterne entre elas e feche-as individualmente. Fechar uma sessão encerra o processo correspondente.
- Ajuste a altura do painel com a alça de redimensionamento superior, com duplo clique para retornar ao tamanho padrão.
- O fundo do terminal acompanha o tema do aplicativo, inclusive na área abaixo da última linha.
- Os comandos são executados com as permissões da conta atual. As sessões são mantidas em memória e não são restauradas ao reiniciar o aplicativo.
- O shell interativo está disponível apenas no desktop. Na web, use o Console de logs e a aba Performance com as métricas disponíveis do navegador.

> O Carteiro é um cliente de API, não um cofre de segredos. Revise credenciais antes de compartilhar arquivos `.creq`, `.cwsk`, snippets, histórico ou capturas de tela.

## Tecnologias

- [Vue 3](https://vuejs.org/) e TypeScript
- [Vite](https://vite.dev/)
- [Tauri 2](https://tauri.app/) e Rust
- [Monaco Editor](https://microsoft.github.io/monaco-editor/)
- `reqwest` para o transporte HTTP no backend

<!-- test-dashboard:start -->

## Painel de testes automatizados

Atualizado em 2026-11-07T10:13:24.065Z. Gerado a partir dos relatórios JSON em `tests-carteiro/` e dos dados publicados para sistemas/plataformas sem relatórios locais (**390 relatórios**).

**Etapas aprovadas: 99.1%** (8576/8653) · **Execuções aprovadas: 90.3%** (352/390) · 0 execuções com falha · 0 interrompidas · 0 em andamento · 33 parciais · 5 ignoradas.

> A porcentagem de etapas mede somente os passos explicitamente registrados nos relatórios; não representa cobertura de código. A taxa de execuções considera apenas execuções concluídas (aprovadas ou com falha).
> Cada suíte/alvo/cenário aparece uma vez por sistema/plataforma, com o resultado mais recente; novas rodadas, tags ou versões atualizam o teste existente.

> Execuções parciais/ignoradas não contam como aprovação. SKIP mantém motivo e alvo nos passos; aprovação de Web não comprova desktop nativo.

<!-- test-dashboard-platforms: macos=macOS%20%2F%20nativo,linux=Linux%20%2F%20nativo,linux-wsl-ubuntu=Linux%20%2F%20WSL%20Ubuntu,linux-wsl-arch=Linux%20%2F%20WSL%20Arch%20Linux,windows=Windows%20%2F%20nativo -->
<!-- test-dashboard-skipped-steps: macos=10,linux=15,linux-wsl-ubuntu=9,linux-wsl-arch=18,windows=18 -->

| Sistema / Plataforma   | Relatórios | Aprovados | Com falha | Interrompidos | Em andamento | Etapas aprovadas | Etapas com falha | Parciais | Ignorados |
| ---------------------- | ---------: | --------: | --------: | ------------: | -----------: | ---------------: | ---------------: | -------: | --------: |
| macOS / nativo         |         97 |        91 |         0 |             0 |            0 |             2050 |                0 |        5 |         1 |
| Linux / nativo         |         83 |        77 |         0 |             0 |            0 |             1868 |                2 |        5 |         1 |
| Linux / WSL Ubuntu     |         61 |        58 |         0 |             0 |            0 |             1642 |                1 |        2 |         1 |
| Linux / WSL Arch Linux |         71 |        62 |         0 |             0 |            0 |             1451 |                2 |        8 |         1 |
| Windows / nativo       |         78 |        64 |         0 |             0 |            0 |             1565 |                2 |       13 |         1 |

<!-- test-dashboard:end -->

## Contribuição

Contribuições são bem-vindas. Abra uma issue para discutir mudanças maiores.
