# 🎯 CS2 Metas

Landing page responsiva com execuções, smokes e timings para os mapas do **Counter-Strike 2**, desenvolvida com **Bootstrap 5.3**.

*Autor:* Felipe Santos Iensen

---

## 📚 Contexto

Projeto da **Atividade 07 – Explorando o Bootstrap** da disciplina *Desenvolvimento de Páginas Web com Framework e CSS* (TSI32B), da UTFPR, campus Guarapuava, ministrada pelo Prof. Dr. Roni Fabio Banaszewski.

O objetivo da atividade é praticar os principais recursos do Bootstrap: sistema de grid, componentes prontos (botões, modais e cards), personalização de cores, utilidades de texto, Flexbox e ícones. O tema escolhido foi o jogo Counter-Strike 2: a página apresenta a execução de um bomb (smokes, flashes e tempos), dicas táticas e uma legenda dos utilitários do jogo.

---

## 🛠️ Tecnologias e Dependências

* **[Bootstrap 5.3](https://getbootstrap.com/)**: grid responsivo, componentes (Button, Modal, Card), utilitários de Flexbox e de texto, e modo escuro nativo (`data-bs-theme="dark"`).
* **[Bootstrap Icons](https://icons.getbootstrap.com/)**: ícones da legenda (smoke, flash, molotov, timing, posição) e dos cards.
* **HTML5 + CSS3**: o arquivo `styles.css` personaliza as cores do tema.

As dependências são instaladas via **NPM** e carregadas da pasta `node_modules`.

---

## 🧩 Recursos do Bootstrap utilizados

| Passo da atividade | Onde aparece na página | Classes / recursos |
|---|---|---|
| **Grid – Linha 1** | Três colunas: "Mapa da semana", card da Mirage, seletor de mapas | `.row`, `.col`, `d-none d-md-block` (3ª coluna oculta em XS e SM) |
| **Grid – Linha 2** | Legenda de utilitários | `.col-12` |
| **Grid – Linha 3** | Cards Economia, Pós-plant e Comunicação | `.col-md-4`, `.offset-md-2`, `.order-md-1`, `.order-md-3` |
| **Botão** | "Ver execução B rápido" | `.btn .btn-primary`, `data-bs-toggle="modal"`, `data-bs-target` |
| **Modal** | Mirage – Execução B rápido | `.modal`, `.modal-dialog-centered`, `.modal-header/body/footer`, `.btn-close` |
| **Card** | Card da Mirage | `.card`, `.card-img-top`, `.img-fluid`, `.card-body`, `.custom-card` |
| **Personalização de cores** | Laranja do lado TR e azul do lado CT | `--bs-primary`, `--bs-secondary` no `:root`; variáveis `--bs-btn-*` no `.btn-primary` |
| **Utilidades de texto** | Título e textos do card | `.text-uppercase`, `.fw-bold`, `.text-primary`, `.fst-italic`, `.text-decoration-underline`, `.fs-6` |
| **Flexbox** | Cinco botões de mapas | `.d-flex`, `.justify-content-between`, `.flex-wrap`, `.gap-2` |
| **Ícones** | Legenda e títulos | `bi-cloud-fog2-fill`, `bi-lightning-charge-fill`, `bi-fire`, `bi-stopwatch`, `bi-geo-alt-fill` |

---

## 🎨 Personalização de cores

As cores do tema seguem as cores clássicas dos dois lados do Counter-Strike:

| Variável | Cor | Uso |
|---|---|---|
| `--bs-primary` | `#de9b35` (laranja TR) | títulos, botão principal, destaques |
| `--bs-secondary` | `#5d79ae` (azul CT) | fundo do card e da legenda |

O `.btn-primary` não lê a variável `--bs-primary`, porque tem variáveis próprias (`--bs-btn-bg`, `--bs-btn-hover-bg`, etc.). Por isso, o `styles.css` sobrescreve também essas variáveis, informando manualmente os tons de *hover* e *active*.

---

## 📁 Estrutura de Arquivos

```
CounterStriker2/
├── index.html      # Estrutura da página
├── styles.css      # Personalização das cores do Bootstrap
├── package.json    # Dependências (bootstrap, bootstrap-icons)
└── node_modules/   # Gerada pelo npm install (ignorada pelo Git)
```

---

## 🚀 Como Executar Localmente

### Pré-requisitos
- [Node.js](https://nodejs.org/) instalado
- Extensão [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) no VS Code

### Passo a passo

1. Clone o repositório:
   ```bash
   git clone https://github.com/flpiensen/CounterStriker2.git
   cd CounterStriker2
   ```
2. Instale as dependências (gera a pasta `node_modules`):
   ```bash
   npm install
   ```
3. Abra a pasta no VS Code, clique com o botão direito no `index.html` e escolha **Open with Live Server**.

---

## 📱 Responsividade

| Tamanho | Comportamento |
|---|---|
| **XS / SM** (< 768px) | Colunas empilhadas; seletor de mapas oculto; cards da linha 3 na ordem do HTML |
| **MD+** (≥ 768px) | Três colunas lado a lado; linha 3 com deslocamento (`offset`) e reordenada (`order`) |
