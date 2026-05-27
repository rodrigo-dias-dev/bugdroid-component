# Dev Log — BugDroid Site (Desafio D10)

---

# v1 — Estrutura Inicial (Mobile-First)

**Data:** 20/05/2026

---

## Estrutura Inicial do Projeto

### O que foi implementado

* Estrutura base do projeto em HTML5;
* Organização inicial de pastas seguindo uma abordagem modular;
* Criação da arquitetura principal do projeto;
* Início da abordagem Mobile First;
* Construção inicial do header e da navegação.

---

## Estrutura de Pastas

```plaintext id="ozx72p"
assets/
versions/
docs/
```

---

## Primeiros passos no Layout

### Header

Primeiros testes utilizando:

* Flexbox;
* containers;
* alinhamento estrutural;
* distribuição vertical de conteúdo.

A estrutura inicial possuía:

* título;
* subtítulo;
* navegação abaixo do bloco principal.

---

## Primeiro problema estrutural importante

### Conflito de alinhamento

O layout precisava atender duas necessidades diferentes:

* `h1` e `p` centralizados;
* `nav` alinhada abaixo com comportamento independente.

Nesse momento percebi que o header estava sendo tratado como:

> “um único bloco visual”

quando na verdade ele possuía:

* responsabilidades diferentes;
* fluxos diferentes;
* alinhamentos diferentes.

---

## Primeiras decisões arquiteturais

### Direção adotada

* Evitar regras estruturais diretamente em elementos textuais;
* Reduzir dependência de:

```css id="x1n4fz"
p {
    max-width: ...
}
```

* Começar a controlar layout através dos containers;
* Separar:

  * estrutura;
  * composição;
  * conteúdo.

---

## Mudança de mentalidade

Comecei a perceber uma diferença importante entre:

### Estrutura

Responsável por:

* alinhamento;
* largura;
* distribuição;
* fluxo visual.

### Conteúdo

Responsável por:

* comunicação;
* semântica;
* tipografia.

Esse foi um dos primeiros momentos em que o projeto começou a deixar de ser apenas “visual”.

---

# Evolução do Header

## Insight estrutural

O header deixou de ser pensado como:

> “um bloco único”

e passou a ser dividido em:

* branding;
* bloco textual;
* navegação;
* distribuição estrutural.

Isso melhorou:

* previsibilidade;
* organização;
* responsividade;
* clareza da arquitetura.

---

# Responsividade

## Primeira Media Query

Breakpoint iniciado em:

```css id="m3q8po"
@media (min-width: 768px)
```

### Ajustes implementados

* expansão tipográfica;
* refinamento do spacing;
* mudança de alinhamento do menu;
* adaptação progressiva do layout.

---

# Momento Eureka 🚀

**21/05/2026**

Durante a construção do footer e do main aconteceu uma descoberta importante sobre o funcionamento do CSS Cascade.

Em determinado momento eu não conseguia entender de onde vinha a centralização de alguns elementos.

Depois de investigar melhor, percebi que:

* a mesma classe `.container` estava sendo reutilizada;
* os estilos estavam sendo herdados naturalmente;
* o comportamento vinha da cascata do CSS.

Foi a primeira vez que senti na prática o significado real do:

> Cascading Style Sheets.

---

# Simplificação da Estrutura HTML

## Refatoração de classes

Classes removidas:

* `post-header`
* `post-section`

### Motivo

Percebi que:

* a semântica já estava clara;
* existia redundância estrutural;
* algumas classes estavam adicionando complexidade sem necessidade.

A responsabilidade passou a ser absorvida diretamente por:

```css id="t8g1nv"
.post
```

---

# Refatoração completa do CSS

**22/05/2026**

## Mudanças realizadas

* Centralização de variáveis globais no `:root`;
* Organização completa dos design tokens;
* Padronização de:

  * cores;
  * fontes;
  * espaçamentos;
  * line-heights;
  * radius;
  * shadows;
* Estruturação do CSS em seções comentadas.

---

## Insight importante

Comecei a perceber que:

> CSS organizado reduz esforço mental.

Quando a arquitetura fica previsível:

* debugging melhora;
* manutenção melhora;
* leitura melhora;
* evolução do projeto fica mais segura.

---

# Resolução de Bug — Footer

## Problema encontrado

Após reorganizar as variáveis no `:root`, parte da rastreabilidade visual foi perdida.

Resultado:

* textos quase invisíveis;
* links herdando cores inadequadas;
* falha de contraste no rodapé.

---

## Solução aplicada

Foi realizada uma auditoria manual das variáveis de texto.

As responsabilidades passaram a ser melhor segmentadas entre:

* texto claro;
* texto escuro;
* títulos;
* links;
* elementos específicos.

---

# Evolução Arquitetural

Uma das maiores mudanças até aqui foi perceber que:

Antes eu tentava:

> “corrigir visualmente”.

Agora começo a pensar:

> “quem deveria possuir essa responsabilidade estrutural?”

Essa mudança alterou completamente minha forma de construir layouts.

---

# DevTools

## Ferramenta que mudou o processo

O DevTools começou a deixar de ser apenas:

> “ferramenta de inspeção”

e passou a virar:

> “ferramenta de raciocínio visual”.

Comecei a utilizar para:

* entender limites dos elementos;
* visualizar espaçamentos reais;
* testar ajustes rápidos;
* observar comportamento responsivo;
* debugar fluxo estrutural.

---

# Organização do Processo

## Pausa estratégica

**22/05/2026**

O desenvolvimento começou a ficar mais intenso.

Percebi que estava tentando controlar:

* tarefas;
* ideias;
* bugs;
* melhorias;

tudo mentalmente.

---

## Decisão importante

Início da organização de:

* fluxo de trabalho;
* documentação;
* estrutura de versões;
* quadro Kanban.

---

## Insight pessoal

O momento em que você deixa de gerenciar tudo na cabeça e começa a estruturar processo é uma mudança importante.

A mente deve:

* resolver problemas;
* criar soluções;
* pensar arquitetura.

Não armazenar pendências.

## Ajuste fino no nav-menu

**23/05/2026**

* Foi adicionado `padding` diretamente no `.navbar-menu`.
* O `padding` anterior da `.navbar` foi removido.
* A alteração reduz responsabilidades estruturais da `.navbar` e torna o `.navbar-menu` mais independente e flexível.
* Também foi adicionado um background preto com transparência para melhorar o contraste visual da navegação sobre o gradiente do header.
