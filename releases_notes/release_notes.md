# Carteiro 1.4.1

## Versão 1.4.1 — alterações desde o commit `05e64e2`

Esta versão reúne as alterações desenvolvidas depois da preparação da versão
1.4.0. O intervalo inclui melhorias funcionais, correções de interface,
reorganização da infraestrutura de testes e documentação.

### Funcionalidades e correções

- **Cancelamento de requisições HTTP em andamento**: a aplicação permite
  interromper uma chamada e sair do estado de carregamento. O cancelamento é
  integrado ao transporte nativo Tauri/Rust e ao transporte web com
  `AbortController`, chegando até os controles da requisição.
- **Workspace público para testes de protocolos**: novo arquivo de workspace
  para exercitar HTTP, GraphQL, WebSocket, Socket.IO, gRPC, MQTT e Server-Sent
  Events (SSE), disponível nos materiais para download e acompanhado de
  instruções.
- **Estado vazio de Workspaces**: quando não há workspace ativo, a interface
  explica a situação e desabilita a criação de pastas e requisições que
  dependem dele.
- **Árvore e menus de Workspaces**: ajustes na representação da árvore e na
  movimentação de itens entre pastas, além de melhorias no fechamento de menus
  de contexto.
- **Painéis, seletores e controles**: cabeçalhos e espaçamentos de painéis mais
  consistentes, refinamentos nos seletores de ambiente e workspace e correção
  da disposição dos controles de janela no cabeçalho.
- **Barra de status**: ações reorganizadas em áreas de estado e controles, com
  identificadores estáveis para automação de testes e ajustes de layout.
- **Localização**: correção da bandeira associada ao idioma chinês simplificado.

### Reorganização estrutural e manutenção

- **Testes em repositório independente**: scripts e relatórios foram separados
  do pacote principal para um repositório irmão. O setup cria as ligações locais
  ignoradas pelo Git, preserva repositórios com alterações locais e os comandos
  de teste verificam os requisitos antes de executar.
- **Execução multiplataforma**: fluxos e suítes foram ampliados e ajustados
  para macOS, Windows, Linux nativo e Linux em WSL, incluindo variações de
  distribuições e ambientes.
- **Seletores acessíveis e estáveis**: painéis de histórico, Git, arquivos,
  Flows e ambientes receberam regiões semânticas e identificadores destinados
  a tornar os testes de interface menos dependentes da estrutura visual.
- **Documentação e relatórios**: documentos foram reorganizados sob
  `docs/markdown`, exemplos de workspaces foram atualizados, e resumos e passos
  de cobertura por plataforma foram revisados.
- **Metadados de versão**: a versão 1.4.0 foi preparada nos manifestos e
  sincronizada entre o pacote, Cargo/Tauri, README e notas. Esta preparação
  segue agora para 1.4.1.

### Commits representativos do intervalo

| Commit | Alteração |
| --- | --- |
| `0f2b747` | Preparação dos metadados da versão 1.4.0 |
| `59c6aeb` | Correção da bandeira do idioma chinês |
| `a038242` | Estado vazio e controles de Workspaces sem seleção |
| `b8191b8` | Reorganização e ajustes da barra de status |
| `f0d5476` | Ajustes visuais de painéis e seletores |
| `41a3769` | Correção dos controles de janela no cabeçalho |
| `669030d` | Ajustes na árvore e no menu de movimentação de itens |
| `0fd8626` | Cancelamento HTTP e workspace de testes de protocolos |
| `2c01f11` | Melhorias estruturais e de testabilidade em painéis |
| `acd4e1d` | Ajustes nos testes de Linux/Ubuntu |

O histórico consolidado das versões anteriores começa abaixo.

---

# Carteiro 1.4.0

Cliente de APIs desktop e web inicial, construído com Vue 3 e Tauri 2.

## Versão 1.4.0 — 17 de outubro de 2026

Consolidação do intervalo após `59926ef` até a preparação desta versão, incluindo as refatorações e validações concluídas no estado atual.

### Exemplos, arquivos e importação de snippets

- Revisão dos Downloadables: Workspaces antes incompletos passam a conter requests, ambientes e Flows; exemplos GraphQL recebem URLs/queries configuradas e exemplos realtime recebem ajustes de endpoints, mensagens e configurações.
- Exemplos HTTP individuais usam valores concretos e descartam headers automáticos obsoletos. Foram revisados exemplos de métodos HTTP, cookies, respostas em arquivo, scripts, WebSocket, Socket.IO, MQTT e EventStream.
- O Workspace de Flow Runner contém os dois Flows; abrir cópias resolve/importa dependências. Downloads e abertura validam JSON e preservam protocolos, scripts e bodies.
- Parser de código ampliado para cURL, Fetch, Axios, Python requests, PHP cURL e Go: interpretação de variáveis, objetos de headers/body, JSON, formulários e métodos HTTP.
- Novo Workspace de testes de colagem com 20 snippets, acompanhado de verificações dos métodos, URLs, headers e corpos interpretados.

### Interface, inicialização, temas e menus

- Corrigidos dimensionamento e overflow da TabBar; badges de protocolos e tipos opcionais recebem tratamento mais robusto.
- Barra de abas dividida em apresentação, renomeação, rolagem, arraste, menus e progresso, preservando eventos, indicadores de Collection e proteção de abas de documentação/histórico/diff.
- Tela de carregamento desktop com progresso, status localizado, wordmarks para temas claros/escuros e transição para a aplicação. Inicialização coordena atalhos, listeners, resize e recuperação de sessões; a web não exige a tela nativa.
- Cabeçalho e status bar separados em menus, seletores e indicadores especializados; controles da janela e redimensionamento mantêm suas responsabilidades próprias.
- Sobre, Documentação e Notas da versão reunidos no menu Carteiro também em Windows/Linux. Notas da versão recebe o atalho Ctrl/Cmd+Shift+F4; atalhos de Sobre/Documentação/Notas também são tratados na web.
- Modais compatíveis reutilizam BaseModal; o host centraliza especificações e coordenação, mantendo conteúdo e comportamento dos diálogos de requests, ambientes, Workspaces, Git, arquivos, nomes duplicados e confirmações.
- CSS de componentes extraído por área, incluindo controles de redimensionamento, ambientes, arquivos, Flows, Git, histórico, requests, configurações e Workspaces. Estilo de nomes duplicados também passa a arquivo próprio; escopo dos seletores e coerência dos temas preservados.

### Arquitetura e manutenção

- App desacoplado em composição de estado, ações, navegação, painéis, atalhos, inicialização e coordenação dos modais.
- Terminal separado em sessões xterm/IPC, navegação, resize e predefinições; documentação separada em toolbar, índice, artigos, seções, navegação e downloads.
- FlowEditor dividido em componentes de passos, scripts, controles e resultados. GitFilesPanel, GitHistoryTab e GitPanel separados por responsabilidade.
- RequestPanel separado em abas, autenticação/headers/parâmetros, body e scripts; ResponsePanel em busca, prévias, resultados e arquivos; SettingsTab em navegação, seções, atalhos e preferências.
- Corrigidos erros de IDE em TerminalPanel, GitPanel, MqttPanel, ExportSidebar e WorkspaceItem; corrigidos bindings extraídos e preservadas referências DOM e reatividade dos controllers.
- Todos os módulos TypeScript avulsos saíram de components e foram distribuídos entre composables, utils e types por área funcional. Imports estáticos/dinâmicos, estilos externos e mapa lazy foram atualizados.
- Tipos de ambientes, histórico, Workspaces e navegação foram separados por domínio; catálogos e predefinições ficaram em utils.
- Dez módulos extensos foram divididos: geração de código por família de linguagem e preparação da requisição; parser por expressões/metadados/headers/body; Flow Runner por agendamento, passos/scripts e transportes; sessões por registry, persistência/recuperação, autorização e autosave; importação/exportação por operação; estado do app por navegação/sincronização; Workspaces por persistência/mutações; integração Git por abas/clone/status; controller Git por estado/comandos/refresh; Explorer por árvore/listeners e ações.
- APIs públicas, identidade singleton, controle de concorrência/races, cleanup e persistência foram preservados. Nenhum módulo nas três pastas ultrapassa 310 linhas nesta entrega; geração de código mantém exatamente as 1.464 saídas comparadas.

### Documentação e testes

- Artigos dedicados a Git e Explorer; guia de aparência com 13 paletas, modo Automático e ilustrações de menus, famílias de temas e carregamento.
- README ampliado com organização de componentes, estilos e TypeScript, comandos/opções dos testes e orientações de execução multiplataforma; mapa de fontes atualizado.
- Novos executores de Sobre, Documentação e Downloadables para web/desktop, com automação macOS e WebDriver. Cenários incluem menu/atalho, formas de fechar, reutilização da aba DOC, tópicos, busca, download, cancelamento, conteúdo exato e abertura de cópias.
- Executor de regressão combina Sobre e Documentação/Downloadables; cenários sorteados e parâmetros de rodadas, tópicos, palavras e ações são documentados.
- Testes Chromium de barra de abas, terminal, documentação, Flows, Git, requisição/resposta e configurações; testes de composables cobrem sincronização de coleções/abas, persistência, sessões, autorização, concorrência de escrita, importação/exportação, scripts, transportes simulados, clone e races de status Git.
- Testes de estrutura validam ausência de TypeScript avulso em components, organização por área e resolução de imports/exports, estilos e componentes lazy.
- Validação da entrega: 123 testes aprovados, regressão web aprovada, TypeScript/build aprovados e nenhum diagnóstico de IDE. Operações Git, disco e serviços de protocolo são simuladas nos testes de integração; isso não substitui validação nativa em todas as plataformas.

### Versão e ferramentas

- Versão 1.4.0 definida em package.json e propagada pelo script existente `pnpm sync:version`: Cargo e badge/tabela de suporte atuais do README são sincronizados sem reescrever versões históricas.
- Tauri referencia package.json; Vite injeta a versão atual usada pela interface/Sobre e o desktop deriva o User-Agent dos metadados do pacote.
- Sincronização integrada aos comandos Tauri, ao build/dev Vite e ao workflow que publica o README; testes verificam SemVer, preservação do histórico, idempotência e falhas explícitas.
- TypeScript incluído nas dependências de desenvolvimento e configuração de tipos ajustada.
- README e notas integradas em português/inglês atualizados. Não foram criados commit, tag, deploy ou release GitHub; limites da web, CORS e exclusividade desktop de integrações nativas continuam válidos.

### Commits incluídos após a base

| Commit | Alteração |
| --- | --- |
| `e082815` | Ajustes baixáveis |
| `2632459` | Ajuste documentação |
| `42f8b7d` | Correção de inserção de código fonte |
| `ca5d3be` | Correção da TabBar |
| `dcf9d4b` | Correção das tabs |
| `13428be` | Application Loading |
| `045ce43` | Documentação dos temas e correção de arquivos com erros |
| `a2a985b` | Refatoração de fonte 1 |
| `87a7877` | Teste do menu Sobre |
| `8372bbc` | Testes da documentação |
| `05e64e2` | Refatoração de fonte 2 |

## Versão 1.3.0 — 14 de outubro de 2026

Alterações dos commits e do estado local após `99add34`.

### Arquivos e Workspaces na web

- Downloadables revisados: catálogo completo, quatro Workspaces antes vazios convertidos em exemplos autocontidos, GraphQL com URLs/queries corretas e WebSocket com URL WSS e mensagem persistida. Exemplos HTTP individuais usam valores concretos e removem headers gerados obsoletos. Workspace de Flow Runner inclui ambos os Flows; Open copy de Flow resolve/importa suas dependências. Downloads e abertura validam JSON e preservam configurações, scripts e bodies.
- Adaptador de arquivos compartilhado para abrir/importar e salvar/exportar `.creq`, `.cwsk`, `.cenv`, `.cflw` e `.cflow`, resultados de Flows e exemplos da documentação. Desktop mantém os diálogos e operações Tauri; navegador usa APIs locais sem backend Rust.
- File System Access API com autorização explícita para autosave na origem; handles persistidos em IndexedDB para recuperação do vínculo. Avisos para acesso expirado, negado ou indisponível. Importação por seletor convencional e download funcionam como alternativa, sem autosave ou recuperação do vínculo na origem.
- Exportação em lote para pasta com nomes exclusivos quando suportada; caso contrário, um único `.creq` com todas as requisições, compatível com a abertura em lote. Abas DOC não entram na exportação de requests.
- Manifestos de Workspace `projectVersion: 1` carregam requests, ambientes e Flows ao selecionar a pasta completa. Na web, importam uma cópia sem sincronizar, modificar ou excluir arquivos da pasta original.
- Rejeição de caminhos desktop e requisições inválidas na web; referências ausentes de projetos web geram erro em vez de conteúdo vazio. Falhas de salvamento/exportação de Flow são notificadas.
- Git, clone e Explorer de repositórios permanecem desktop e agora informam essa limitação na web sem chamar Rust. Sincronização automática de pastas e Git web continuam pendentes; hospedagem permanece estática e requests continuam sujeitos a CORS.

### Variáveis, temas e identidade

- Destaque compartilhado em URL, params, headers, auth, body, scripts, Flows e editores de protocolos: azul para variáveis habilitadas e preenchidas no ambiente selecionado; vermelho para ausentes, desabilitadas, vazias ou apenas com espaços.
- Corrigida a origem das variáveis para usar o ambiente selecionado no cabeçalho. Alterações de valores e troca de ambiente atualizam os destaques; nomes com espaços codificados são reconhecidos e o texto dos inputs é escapado. Senhas ocultas continuam mascaradas.
- Corrigidos estilos globais que cobriam a camada de destaque dos inputs e o alinhamento do texto da camada colorida. Decorações Monaco compartilham validação e limpam listeners ao desmontar editores.
- Editores Monaco de requisições, Flows, protocolos, Markdown, arquivos Git e diffs acompanham as 13 paletas, incluindo texto, fundo, seleção, sugestões, tooltips e diferenças. Mudanças de tema preservam conteúdo e destaque de variáveis.
- Menus claros, incluindo Light Pastel, mantêm texto, ícones e atalhos legíveis no hover e foco. Contraste verificado nos cinco temas claros; Light Pastel apresentou 9,53:1.
- Favicon com PNG 32×32 da logo, declaração única e URL com hash no build; `.ico` na raiz e logo para dispositivos Apple. O Safari pode conservar o favicon anterior em cache; a atualização visual não foi confirmada nesse navegador.

### Desenvolvimento e versão

- Configuração VS Code corrigida para o formato 0.2.0 e recomendação CodeLLDB. Windows e Linux/WSL usam executáveis e diretórios Cargo específicos, permitindo instâncias separadas no mesmo checkout.
- Portas web/desktop: `5173`/`1420` em Windows/macOS e `5174`/`1430` em Linux/WSL. Vite aceita `TAURI_DEV_PORT`; configuração Tauri Linux aponta para a porta desktop correspondente.
- Tarefas Vite em primeiro plano, com sinais de início/prontidão e encerramento da própria instância por socket Unix ou pipe Windows, sem encerrar outros servidores por nome. Shell interativo no Linux/WSL carrega Node/NVM. Porta ocupada permanece erro explícito.
- `Cargo.lock` removido do versionamento e adicionado ao ignore.
- Versão 1.3.0 em npm, Cargo, Tauri, janela Sobre e User-Agent gerado no desktop. README e notas em inglês/português atualizados; Carteiro → Notas da versão reutiliza a aba DOC.

## Versão 1.2.0 — 14 de outubro de 2026

Resumo das alterações após `3272edf`, incluindo mudanças ainda não commitadas na preparação da versão.

### Web inicial

- Adaptador HTTP compartilhado: Rust/Tauri no desktop, Fetch direto no navegador. Integrado às requisições HTTP e aos passos HTTP/GraphQL dos Flows, com timeout, limite de resposta, detecção de binários e base64.
- Cookies enviados por `credentials: include`, conforme as políticas do navegador e do servidor. O cookie jar editável permanece exclusivo do desktop; na web o gerenciador mostra um aviso, sem edição ou leitura de `Set-Cookie`.
- Erros explícitos para headers proibidos, Digest, proxies, certificados personalizados, SSL desativado e versão HTTP forçada. Headers automáticos gerenciados pelo browser não são definidos manualmente. Falhas de acesso informam a possibilidade de bloqueio CORS.
- Título e favicon Carteiro; Documentação e Notas de versão disponíveis no menu web. Controles de janela, Sair e divisória correspondente ocultos no navegador.
- Documentação integrada como aba única DOC, com título localizado e sem renomeação ou duplicação; menus e atalhos reutilizam a aba aberta, e Notas de versão seleciona seu tópico na mesma aba. A documentação não é exportada como requisição nem adicionada à Collection.
- Dev Tools substitui o comando Visualizar Terminal no cabeçalho e no menu Tauri e preserva a aba selecionada. Na web, shell oculto, Console de logs e Performance com armazenamento/cache e tempo da página, sem RAM, CPU, PID ou tamanho de arquivos nativos.
- Configurações VS Code para iniciar desktop e web separadamente ou juntos, com portas `1420` e `5173`.
- **Limites desta entrega**: hospedagem estática sem proxy de requests; destinos precisam permitir CORS e credenciais. Sincronização automática de pastas e Git web GitHub/GitLab ainda pendentes; Git e seu Explorer informam a exclusividade desktop sem chamar Rust no navegador. gRPC continua exclusivo do desktop; Flows exibem erro explícito na web. Protocolos realtime dependem dos transportes aceitos pelo navegador e pelo destino.

### Collection e Git desktop

- Novo comando de salvar todas as abas de requisição não vinculadas na raiz da Collection do workspace ativo, no menu nativo e no cabeçalho web/desktop. Ignora itens já salvos, Flows e abas auxiliares; mantém protocolo/configurações e gera IDs únicos.
- Exportação desktop de várias requisições para pasta preservada; corrigida a tradução que a confundia com salvar na Collection. Corrigido o clique de criação de requisição na raiz.
- Histórico Git geral e por arquivo em abas com filtros por branch, autor e texto, detalhes de commits, agrupamento de arquivos alterados, estatísticas e diffs históricos.
- Seleção múltipla de alterações para stage/unstage, ações de commit/amend/sincronização e menus de gerenciamento de branches, remotes, stash e tags.
- Saída Git integrada ao Dev Tools com níveis, busca, limpeza e rolagem automática; branch na barra de status e melhorias na navegação de histórico, editores e diffs.

### Manutenção e compatibilidade

- Ajustes do cabeçalho responsivo no Linux e arraste pelo logo ao manter pressionado no macOS; correções de propriedades opcionais e chaves Vue, além de avisos de Rust específicos de plataforma.
- Exclusão de ambientes sincronizada com Workspaces e persistência local.
- Extração do redimensionamento para composable, lazy loading de componentes pesados e idiomas e redução do chunk inicial, eliminando o aviso de tamanho excessivo do Vite.
- Remoção de imports, variáveis, composables, estilos, traduções duplicadas, assets e dependência/permissão opener sem uso; árvore de fontes atualizada.
- Corrigido conflito de nomes entre o executor HTTP de Flow e o adaptador de transporte, evitando chamada recursiva nos passos HTTP/GraphQL.
- Versão 1.2.0 nos manifestos npm/Tauri/Cargo, janela Sobre, User-Agent, README e notas integradas. O browser continua controlando seu próprio User-Agent.

## Novidades da versão 1.1.0

- **Git por Workspace**: repositórios independentes por Workspace, inicialização, branches, commits, grafo e estado ahead/behind, stage/unstage, fetch, pull, push e comandos Git.
- **Explorer Git na sidebar**: árvore expansível, criação inline de arquivos e pastas, seleção e indicação de arquivos abertos, além de copiar, recortar, colar, renomear e excluir pelo menu de ações.
- **Editor com salvamento automático**: arquivos do repositório abrem no editor Monaco. Alterações em `workspace.cwsk`, `.creq`, `.cenv` e `.cflow` são sincronizadas com a aplicação.
- **Diff e descarte de alterações**: comparação lado a lado ou em linha, reutilização de abas de diff já abertas e descarte individual ou total com confirmação, inclusive em repositórios sem commit inicial.
- **Criar Workspace a partir do Git**: clone pelo menu Workspaces e pelo menu Carteiro; se `workspace.cwsk` não existir, o manifesto é criado sem apagar os demais arquivos clonados.
- **README do Workspace**: `CARTEIRO-README.md` na raiz da Collection abre em um editor Markdown com pré-visualização.
- **Correção do modal de clone**: fundo e campos agora usam cores opacas do tema.
- **Barra de títulos no Linux**: seletores de Environment e Workspace cedem espaço e truncam nomes longos ao reduzir a janela, mantendo os controles de minimizar, maximizar e fechar visíveis.
- Versão atualizada para 1.1.0 nos metadados, na janela Sobre, no README, nas notas integradas acessíveis pelo menu Carteiro e no User-Agent HTTP.

## Novidades da versão 1.0.11

- **Socket.IO por versão de cliente**: a aba dedicada permite escolher Socket.IO v2, v3 ou v4 e negocia a geração Engine.IO correspondente. O status distingue transporte aberto, handshake e conexão do namespace, responde a ping/pong e apresenta erros de versão, namespace e desconexão. WebSocket Echo continua restrito à aba WebSocket.
- **Exemplos públicos Socket.IO**: cinco requests `.creq` e um workspace `.cwsk` estão disponíveis nos downloads da documentação, organizados por formato e tema. A documentação informa que o endpoint público atual aceita Engine.IO 4, exige token para conectar o namespace e não suporta Engine.IO 3.
- **Flow Runner e amostras de protocolos**: suporte a métodos HTTP personalizados e protocolos realtime/RPC com arquivos `.cflow` e `.cwsk` disponíveis para teste e download.
- **Estrutura comum de modais**: modais compatíveis compartilham uma base com cabeçalho, acessibilidade, ações e botão de fechar, sem remover layouts especializados.
- **CSS separado dos componentes Vue**: estilos scoped relacionados foram movidos para arquivos próprios para reduzir o tamanho dos componentes.
- **Ajustes de controles de configurações**: dimensões de inputs e selects de General Inputs, HTTP version, proxy e certificados foram corrigidas, inclusive a altura dos selects no macOS.
- **Diálogo de salvar resiliente ao cancelamento**: diálogos concorrentes de salvar são evitados e a trava é sempre liberada ao cancelar ou falhar; atalhos repetidos são ignorados no tratamento local do Linux.
- **Notas acessíveis pelo menu Carteiro**: adicionado acesso direto às notas de versão integrado ao menu do aplicativo.
- Versão atualizada para 1.0.11 nos metadados, na janela Sobre, no README, nas notas integradas e no User-Agent HTTP.

## Novidades da versão 1.0.10

- **Correção de overflow vertical nas abas (Windows)**: corrigida a ativação indevida de `overflow-y` e o aparecimento de barra de rolagem vertical nas abas da TabBar no Windows. A altura das abas foi alinhada com `100%` e `box-sizing: border-box`, foi aplicado `overflow-y: hidden` explícito nos containers de rolagem e desativada qualquer barra de rolagem vertical.
- **Suporte a protocolos em tempo real e RPC no Flow Runner**: execução em Flows de chamadas WebSocket, Socket.IO, GraphQL, gRPC, MQTT e EventStream (SSE), com cliente nativo gRPC em Rust integrado ao backend do Tauri.
- **Testes e exemplos de Flows**: adicionados workspaces e arquivos de teste de Flows (`flow-http-custom-methods.cflow`, `flow-realtime-rpc.cflow`, `flow-runner-protocol-tests.cwsk`).
- Versão do aplicativo atualizada para 1.0.10 nos metadados, na janela Sobre, na documentação integrada e no User-Agent HTTP.

## Novidades da versão 1.0.9

- **Criação unificada de chamadas**: o menu Arquivo, o atalho de nova chamada, o botão `+` da TabBar, a tela inicial e as ações das Collections abrem o mesmo fluxo modal para definir nome, protocolo e método HTTP.
- **Seletores de protocolo e método ampliados**: controles maiores, mais legíveis e com foco visual consistente em todos os temas.
- **Modais tematizados e padronizados**: criação de chamadas e pastas, exclusões, importações, ambientes, cookies e diálogos auxiliares respeitam as cores semânticas do tema ativo.
- **Arquivos `.creq` públicos por protocolo**: adicionados exemplos independentes para WebSocket, Socket.IO, GraphQL, gRPC, MQTT e EventStream (SSE), além do workspace consolidado para testes.
- **Persistência multi-protocolo completa**: `protocol` e `protocolConfig` agora são mantidos ao abrir, salvar, recuperar e salvar novamente arquivos `.creq`.
- Versão do aplicativo atualizada para 1.0.9 nos metadados, na janela Sobre e no User-Agent HTTP.

## Novidades da versão 1.0.8

- **Suporte a múltiplos protocolos nas Collections e Abas**: suporte nativo a requisições e conexões de **WebSocket**, **Socket.IO**, **GraphQL**, **gRPC**, **MQTT** e **EventStream (SSE)**, além de HTTP.
- **Painéis dedicados por protocolo**:
  - **WebSocket (WS)**: envio bidirecional de mensagens, streaming em tempo real, badges distintivas e status de conexão.
  - **Socket.IO (SIO)**: suporte a handshake Engine.IO, canais, eventos e emissão/recepção de payloads em tempo real.
  - **GraphQL (GQL)**: abas dedicadas para query/mutation, variáveis JSON e headers customizados, com métricas de tempo e status.
  - **gRPC**: chamadas RPC estruturadas com definições .proto e payloads de requisição JSON.
  - **MQTT**: comunicação pub/sub sobre conexões de WebSocket bridge com inscrição em tópicos e publicação em tempo real.
  - **EventStream (SSE)**: streaming contínuo de Server-Sent Events com visualização instantânea de eventos recebidos.
- **Coleção de testes com chamadas públicas**: arquivo `realtime-protocols-test-workspace.cwsk` com exemplos públicos prontos para teste (Postman Echo WebSocket, Countries GraphQL, EMQX MQTT, demo gRPC e Express EventStream).
- **Aba de Script unificada (Pre-request e Post-response)**: união das abas de script no painel de requisições sob a aba `Script`, com alternador de fase entre Pre-request e Post-response e editor de código dedicado.
- **Post-response Scripts e aba Script Output**: suporte a scripts executados com base na resposta HTTP, com saída dedicada em `Script Output` no painel de respostas.
- **Painel Dev Tools unificado no App Status Bar**: substituição dos botões isolados de terminal e métricas por um único botão `Dev Tools` alinhado à barra de status, com botão de fechar alinhado à direita e três abas:
  - **Terminal**: sessões de terminal interativo com navegação lateral por setas em larguras reduzidas.
  - **Performance**: métricas de CPU, memória RAM, PID do processo em execução e tamanho total dos arquivos abertos. Adaptação completa da tabela de métricas aos temas claros e escuros.
  - **Console**: console centralizado para visualização de logs emitidos por scripts de pós-resposta, com filtros e ação de limpeza rápida.
- **Suporte completo a Scripts nos Flows**: execução de post-response scripts em requisições de Flows, com envio de logs para o Console e correção do funcionamento de pre-delay e repetição (`repeat`).
- **Theming aprimorado para abas ativas e menus**:
  - Aba ativa na TabBar com realce usando a cor de destaque (`--accent-color`) tanto no tema escuro quanto no claro.
  - Menus suspensos do App Header e menus dropup da barra de status (Workspace, Environment, Temas, Idioma e Sessões de Arquivos) com herança completa das cores de fundo, bordas e destaque do tema ativo.
  - Indicador lateral de arquivos/flows ativos e abertos alinhado à cor do tema escolhido.
- **Tela cheia no menu Visualizar do macOS**: o toggle nativo ocupa a área da mesa no modo Full Screen, sem maximizar a janela na área útil.
- **Documentação de scripts e exemplos .creq**: inclusão de arquivos `.creq` de exemplo cobrindo todas as fases de scripts e 3 novos tópicos detalhados sobre scripts na documentação interna do menu Carteiro.
- Versão do aplicativo atualizada para 1.0.8 nos metadados, na interface e no User-Agent.

## Novidades da versão 1.0.6

- **Configurações gerais**: nova aba global com seções para aparência, idioma, atalhos, requisições HTTP, proxies e certificados. A navegação se adapta a janelas estreitas, permite rolagem horizontal com controles e redimensionamento da área lateral.
- **Aparência e idioma**: temas disponíveis com prévias visuais e seletor de idioma nas configurações.
- **Atalhos editáveis**: consulte e personalize combinações por sistema operacional, com captura guiada e persistência.
- **Opções HTTP persistentes**: escolha HTTP/1.1 ou HTTP/2, timeout, tamanho máximo da resposta e verificação de certificados SSL.
- **Perfis de proxy**: crie, edite e selecione perfis HTTP, HTTPS, SOCKS5 ou SOCKS5h para requisições manuais e Flows. Senhas de proxy são armazenadas no cofre de credenciais do sistema operacional.
- **Perfis de certificados**: configure autoridades certificadoras PEM/DER adicionais e autenticação mTLS com certificado de cliente e chave privada PEM não criptografada.
- **Abas refinadas**: removido o indicador colorido único à esquerda, preservando indicadores de requisições, Flows e variáveis; aprimorados o destaque da aba ativa, o botão de fechar e o comportamento ao arrastar. Requisições e Flows agora apresentam o indicador de cor de forma consistente.
- Versão do aplicativo atualizada para 1.0.6 nos metadados, na interface e no User-Agent.

## Novidades da versão 1.0.5

- **Redimensionamento dos painéis de Requisição e Resposta**: divisor interativo entre os blocos de Request e Response com suporte aos modos vertical (empilhado) e horizontal (lado a lado), atalhos de teclado (setas), duplo clique para redefinir para 50/50 e persistência das proporções no armazenamento local.
- **Redimensionamento do Terminal integrado**: alça superior no console/terminal permitindo ajuste vertical de altura em relação ao bloco de conteúdo acima, com limites dinâmicos, redimensionamento automático das sessões de shell (`xterm`), duplo clique para restaurar altura padrão e persistência da altura configurada.
- Bloqueio de eventos de ponteiro nos editores Monaco e iframes durante o arrasto de redimensionamento para evitar travamentos do cursor do mouse.
- Versão do aplicativo atualizada para 1.0.5 nos metadados, no User-Agent e na interface.

## Novidades da versão 1.0.4

- Temas Light e Dark default renomeados e novas opções: Light Monochrome, Light Pastel, Catppuccin Latte, VS Code Light, Dark Monochrome, Dark Pastel, Catppuccin Frappe, Catppuccin Macchiato, Catppuccin Mocha, Nord e VS Code Dark.
- Suporte aos métodos HTTP `OPTIONS`, `HEAD`, `TRACE` e `CONNECT`, além de métodos personalizados.
- Console integrado com sessões interativas de shell no aplicativo desktop, acessível pelo menu View e pela barra de status.

## Novidades da versão 1.0.3

- Barra de título integrada à interface, com controles de minimizar, maximizar/restaurar e fechar.
- Controles da janela adaptados ao sistema operacional: Windows, macOS e Linux.
- Arraste da janela pela área livre do cabeçalho e maximização/restauração por duplo clique.
- Remoção da barra nativa da janela, com ajustes específicos para manter esse comportamento no Linux.
- Fundo da janela sincronizado com os temas claro, escuro e do sistema, evitando diferenças de cor ao maximizar.
- Versão do aplicativo atualizada para 1.0.3 nos metadados, na interface e no User-Agent das requisições.

## Funcionalidades

### Requests HTTP

- Envio de `GET`, `POST`, `PUT`, `PATCH` e `DELETE`.
- URL, query params, headers, autenticação e body (JSON, texto ou `application/x-www-form-urlencoded`) com Monaco Editor.
- Ativação e desativação de linhas de parâmetros e headers sem removê-las.
- Variáveis `{{chave}}` em URLs, parâmetros, headers, autenticação, body e scripts.
- Scripts JavaScript pre-request e de teste, com acesso às variáveis de ambiente e à resposta.

### Autenticação e headers

- Bearer Token, JWT Bearer, OAuth 2.0 por token, Basic Auth, API Key e Digest Auth.
- Inspeção de headers padrão e gerados pelo transporte.
- Cookie Manager local com captura de `Set-Cookie` e envio conforme domínio, path, segurança e expiração.

### Respostas

- Status, duração, headers e corpo da resposta.
- Formatação, cópia e pesquisa de conteúdo; preview de HTML, imagens e PDFs.
- Respostas binárias preservadas e download de arquivos pelo diálogo nativo.

### Workspaces, abas e histórico

- Workspaces com pastas, requests salvas, ambientes e flows.
- Várias abas com criação, duplicação, renomeação, movimentação, reordenação e fechamento em grupo.
- Reordenação de requests e pastas na coleção.
- Histórico com reabertura de chamadas.
- Sincronização entre abas e itens salvos da coleção.
- Trocar de workspace fecha requisições e flows da workspace antiga.

### Ambientes e flows

- Ambientes com variáveis habilitadas ou desabilitadas e seleção do ambiente ativo.
- Flows sequenciais com delays, repetições, pausa, retomada e interrupção.
- Resultados por etapa (status, duração, testes e downloads), exportáveis em JSON.
- Cookie Manager compartilhado entre requests manuais e flows.

### Arquivos e código

- Importação e exportação em `.creq`, `.cwsk`, `.cenv` e `.cflw`, com opção de autosave no arquivo de origem.
- Salvamento preservando variáveis ou resolvendo-as pelo ambiente atual.
- Geração de código para cURL, JavaScript Fetch, JavaScript Axios e Python Requests.

### Interface e armazenamento

- Temas claro, escuro e do sistema.
- Idiomas: English, Português (Brasil), Español, Français, 简体中文 e 日本語.
- Menus nativos, barra de status com métricas e documentação incorporada.
- Dados mantidos localmente no perfil da aplicação; o cookie jar não é incluído nos arquivos exportados.

> O Carteiro não é um cofre de segredos. Revise credenciais antes de compartilhar arquivos exportados, snippets, histórico ou capturas de tela.

## Downloads

Instaladores para macOS (`.dmg`), Windows (`-setup.exe`, `.msi`) e Linux (`.AppImage`, `.deb`, `.rpm`).

## Recursos adicionais

- Seletor de temas com Light Mode default, Light Monochrome, Light Pastel, Catppuccin Latte, VS Code Light, Dark Mode default, Dark Monochrome, Dark Pastel, Catppuccin Frappe, Catppuccin Macchiato, Catppuccin Mocha, Nord e VS Code Dark, além da opção de seguir o tema do sistema.
- Suporte aos métodos HTTP `OPTIONS`, `HEAD`, `TRACE` e `CONNECT`, além da possibilidade de informar um método personalizado. `OPTIONS` e métodos personalizados podem enviar body; `HEAD`, `TRACE` e `CONNECT` não enviam body pelo fluxo normal.
- Console integrado acessível por **View > Terminal** e pelo ícone na barra de status. Permite iniciar, alternar e fechar sessões interativas do shell do sistema; fechar uma sessão encerra seu processo. Os comandos usam as permissões da conta atual, as sessões não são persistidas após reiniciar o app e o recurso está disponível no aplicativo desktop.
