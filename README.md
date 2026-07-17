# Do Projeto ao Container

Tutorial visual e interativo que mostra como uma aplicação **Angular + Node.js** nasce na máquina do desenvolvedor e é empacotada, camada por camada, até rodar em Docker.

É uma página única, sem build e sem dependências: abra o `index.html` no navegador e pronto.

## O que tem dentro

A jornada é dividida em 8 etapas, apresentadas numa timeline vertical:

| # | Etapa | Assunto |
|---|-------|---------|
| 1 | Criando o projeto local | A pasta raiz e a separação backend / frontend |
| 2 | Criando o Backend Node.js | A API que processa as regras de negócio |
| 3 | Criando o Frontend Angular | A interface que o usuário vê e usa |
| 4 | Criando o Dockerfile | A receita para construir a imagem |
| 5 | Criando as imagens Docker | `docker build` — do código à imagem |
| 6 | Criando e iniciando containers | `docker run` — a imagem ganha vida |
| 7 | Verificando containers | Listar, parar e remover |
| 8 | Evolução para Docker Compose | Orquestrando tudo com um só comando |

Cada etapa traz a explicação do conceito, a árvore de arquivos daquele momento do projeto e um terminal com os comandos correspondentes.

## Interações

- **Cartões expansíveis** — clique em uma etapa para abrir ou fechar o conteúdo.
- **Terminais simulados** — o botão `▶ Executar comandos` digita os comandos e imprime a saída, como se alguém estivesse ali.
- **Animação de transformação** — a faixa do topo percorre `Projeto → Dockerfile → Imagem → Container → App rodando`, e pode ser repetida a qualquer momento.
- **Barra de progresso** que acompanha a rolagem, e as etapas surgem conforme entram em cena.

Quem tiver `prefers-reduced-motion: reduce` ativo recebe a versão sem animações — todo o conteúdo continua acessível.

## Código de cores

A cor é o sistema de informação da página: cada tipo de artefato tem sua própria assinatura cromática, repetida na legenda, no cartão e na borda de destaque. A paleta é deliberadamente dessaturada — a cor identifica, não decora.

| Token | Cor | Significado |
|-------|-----|-------------|
| `--c-source` | `#7e9689` verde | Código fonte |
| `--c-docker` | `#7089a3` azul | Dockerfile |
| `--c-image` | `#97899a` malva | Imagem Docker |
| `--c-container` | `#888ca3` violeta | Container |
| `--c-command` | `#9c9280` âmbar | Comandos |
| `--c-compose` | `#9a8a8a` terracota | Docker Compose |

Os terminais fogem dessa regra de propósito: usam verde e âmbar mais vivos (`--t-green`, `--t-amber`) para parecerem terminais de verdade.

## Como usar

```bash
git clone https://github.com/VPRocha/Docker-diagram.git
cd Docker-diagram
```

Depois é só abrir o `index.html` no navegador — não há passo de instalação nem de build.

Se preferir servir por HTTP (útil para testar em outros dispositivos da rede):

```bash
python -m http.server 8000
# acesse http://localhost:8000
```

A única dependência externa são as fontes **Inter** e **JetBrains Mono**, carregadas do Google Fonts. Sem conexão, a página cai nas fontes do sistema e continua funcionando.

## Estrutura

```
Docker-diagram
├── index.html             # a aplicação inteira: markup, CSS e JS
├── design-philosophy.md   # a filosofia de design da interface
└── README.md
```

O conteúdo das 8 etapas vive no array `steps`, dentro do `<script>` do `index.html` — é o ponto de partida para editar textos, comandos ou acrescentar etapas.

## Design

A interface segue o movimento *Estratos Luminosos*: camadas precisas sobre um fundo quase preto, informação irradiada em vez de gritada, movimento que revela sem distrair. Os princípios estão descritos em [design-philosophy.md](design-philosophy.md).

## Escopo

Material educativo, com foco em desenvolvimento local e Docker básico. Os Dockerfiles e comandos mostrados servem ao aprendizado do fluxo — não são uma configuração de produção.
