# Carteiro 1.0.1

Cliente desktop para criar, enviar e organizar requisições HTTP, construído com Vue 3 e Tauri 2.

## Novidades desta versão

- Barra de título integrada à interface, com controles de minimizar, maximizar/restaurar e fechar.
- Controles da janela adaptados ao sistema operacional: Windows, macOS e Linux.
- Arraste da janela pela área livre do cabeçalho e maximização/restauração por duplo clique.
- Remoção da barra nativa da janela, com ajustes específicos para manter esse comportamento no Linux.
- Fundo da janela sincronizado com os temas claro, escuro e do sistema, evitando diferenças de cor ao maximizar.
- Versão do aplicativo atualizada para 1.0.1 nos metadados, na interface e no User-Agent das requisições.

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
