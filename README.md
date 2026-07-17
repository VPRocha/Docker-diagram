# Do Projeto ao Container

Tutorial interativo sobre como uma aplicação Angular + Node.js sai da máquina do desenvolvedor e vai parar dentro de um container Docker.

É uma página só, sem build e sem dependências. Abra o `index.html` no navegador.

## O que tem dentro

São 8 etapas numa timeline vertical:

| # | Etapa | Assunto |
|---|-------|---------|
| 1 | Criando o projeto local | A pasta raiz e a separação backend / frontend |
| 2 | Criando o Backend Node.js | A API que processa as regras de negócio |
| 3 | Criando o Frontend Angular | A interface que o usuário vê e usa |
| 4 | Criando o Dockerfile | A receita para construir a imagem |
| 5 | Criando as imagens Docker | `docker build`, do código à imagem |
| 6 | Criando e iniciando containers | `docker run`, a imagem ganha vida |
| 7 | Verificando containers | Listar, parar e remover |
| 8 | Evolução para Docker Compose | Orquestrando tudo com um só comando |

Cada etapa tem a explicação do conceito, a árvore de arquivos daquele momento do projeto e um terminal com os comandos.

## Interações

Clique em uma etapa para abrir ou fechar o conteúdo.

Nos terminais, o botão `▶ Executar comandos` digita os comandos e imprime a saída.

A faixa do topo anima o caminho `Projeto → Dockerfile → Imagem → Container → App rodando` e pode ser repetida pelo botão `↻ Repetir animação`.

Há uma barra de progresso na rolagem, e as etapas aparecem conforme entram na tela. Com `prefers-reduced-motion: reduce` ativo, as animações são desligadas e o conteúdo continua todo acessível.

## Código de cores

Cada tipo de artefato tem uma cor, usada na legenda, no cartão e na borda de destaque. A paleta é dessaturada de propósito, porque a cor serve para identificar.

| Token | Cor | Significado |
|-------|-----|-------------|
| `--c-source` | `#7e9689` verde | Código fonte |
| `--c-docker` | `#7089a3` azul | Dockerfile |
| `--c-image` | `#97899a` malva | Imagem Docker |
| `--c-container` | `#888ca3` violeta | Container |
| `--c-command` | `#9c9280` âmbar | Comandos |
| `--c-compose` | `#9a8a8a` terracota | Docker Compose |

Os terminais são exceção: usam verde e âmbar mais vivos (`--t-green`, `--t-amber`) para parecerem terminais de verdade.

## Como usar

```bash
git clone https://github.com/VPRocha/Docker-diagram.git
cd Docker-diagram
```

Abra o `index.html` no navegador. Não tem instalação nem build.

Para servir por HTTP, o que ajuda a testar em outros dispositivos da rede:

```bash
python -m http.server 8000
# acesse http://localhost:8000
```

A única dependência externa são as fontes Inter e JetBrains Mono, carregadas do Google Fonts. Sem conexão, a página usa as fontes do sistema e continua funcionando.

## Estrutura

```
Docker-diagram
├── index.html             # a aplicação inteira: markup, CSS e JS
├── design-philosophy.md   # a filosofia de design da interface
└── README.md
```

O conteúdo das 8 etapas fica no array `steps`, dentro do `<script>` do `index.html`. É lá que se edita texto, comandos ou se acrescenta uma etapa nova.

## Design

A interface segue o movimento *Estratos Luminosos*: camadas sobre um fundo quase preto, cor como sistema de informação, movimento discreto. Os princípios estão em [design-philosophy.md](design-philosophy.md).

## Escopo

Material educativo, focado em desenvolvimento local e Docker básico. Os Dockerfiles e comandos servem para explicar o fluxo e não valem como configuração de produção.
