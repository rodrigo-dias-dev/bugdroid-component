# Notes - BugDroid Site (Desafio D10)

## Arquitetura de Layout

### Princípio atual
- Layout deve ser controlado por containers
- Elementos de texto não devem carregar responsabilidades de posicionamento

### Aprendizado importante
- Flexbox deve organizar blocos (layout macro)
- Não deve ser usado para "forçar ajuste fino" de texto

---

## Problema atual do header

### Situação
- h1 e p centralizados visualmente
- nav precisa ficar alinhado à esquerda abaixo

### Insight arquitetural
O header não deve ser um bloco único de alinhamento.
Ele precisa ser dividido em subestruturas.

Possível abordagem:
- Header dividido em:
  - bloco superior (branding: h1 + p)
  - bloco inferior (nav)

---

## Decisões técnicas em evolução

- Evitar `max-width` aplicado diretamente em `<p>`
- Preferir controle de largura no `.container`
- Pensar layout em níveis:
  - nível 1: estrutura (header, main, footer)
  - nível 2: blocos internos (containers)
  - nível 3: elementos (texto, links, imagens)

---

## Dúvidas em aberto

- Melhor estrutura: header em flex column ou grid?
- Quando separar container interno vs usar o mesmo container global?
- Até que ponto responsividade deve estar no container vs no breakpoint?

---

## Direção atual

O foco está migrando de:
"fazer funcionar visualmente"

para:
"organizar arquitetura de layout escalável"

## Mini dicionário de Git / GitHub

- U (Untracked / Verde): Arquivo novo, o Git ainda não rastreia.
- M (Modified / Amarelo): Arquivo que já existe, o Git rastreia, e você alterou o código dele.
- A (Added / Verde): Arquivo que você já preparou (git add) e está pronto para o commit.

- `git init` = Inicia um repositório local novo na máquina.
- `git add .` = Coloca os arquivos na "área de preparação" (Staging). Eles estão prontos para serem salvos.
- `git commit -m "mensagem"` = Bate a "foto" oficial e salva essa versão no histórico do repositório.
- `git push` = Envia os commits da sua máquina para o repositório remoto (GitHub).

## 2. Aspect Ratio Box (Vídeo Responsivo)
Técnica para blindar `iframes` fixos do YouTube, tornando-os fluidos na proporção 16:9.

```css
.video {
    position: relative;
    height: 0;
    padding-bottom: 56.25%; /* Proporção 16:9 (9 / 16) */
    margin-bottom: var(--spacing-md);
}

.video iframe {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
}
``` 
---

``` 

## Observações arquiteturais importantes

### Containers não são apenas “caixas”

Comecei a entender que containers possuem responsabilidade estrutural.

Eles controlam:

* fluxo;
* alinhamento;
* distribuição;
* largura útil;
* comportamento responsivo.

---

### Largura de leitura

Nem sempre ocupar 100% da largura melhora o layout.

Limitar a largura textual melhora:

* ergonomia visual;
* leitura;
* equilíbrio da composição.

Exemplo estudado:

```css
width: min(22rem, 100%);
```

---

### Responsabilidade estrutural

Um dos maiores aprendizados até agora foi perceber que:

* layout;
* composição;
* conteúdo;

não devem disputar responsabilidade entre si.

Estrutura organiza.
Conteúdo comunica.

---

### Ajustes locais vs solução estrutural

Aprendizado importante:

Antes eu tentava resolver problemas diretamente no elemento.

Agora começo a pensar:

> “o problema pertence ao componente ou à estrutura?”

Isso mudou bastante minha forma de debugar layouts.

---

### Mobile First

Comecei a entender que Mobile First não significa apenas:

> “fazer primeiro no celular”.

Mas sim:

* começar pelo layout essencial;
* construir progressivamente;
* adicionar complexidade apenas quando necessário.

---

### CSS mais previsível

Quanto mais organizada a hierarquia:

* menos correções improvisadas;
* menos conflitos;
* menos dependência de ajustes arbitrários.

---

### Organização mental de CSS

Comecei a perceber uma separação natural entre:

#### Estrutura

* wrapper
* container
* sections
* fluxo
* distribuição

#### Componentes

* navbar
* cards
* media
* footer
* blocos reutilizáveis

#### Conteúdo

* títulos
* textos
* links
* imagens

---

### Pensamento de escalabilidade

O projeto deixou de ser apenas:

> “um desafio HTML/CSS”

e começou a virar:

> “um sistema que pode evoluir em versões”.

Isso influenciou:

* organização de pastas;
* versionamento;
* documentação;
* arquitetura;
* padronização.

---

### Debug visual

Muitas respostas começaram a aparecer quando:

* observei espaçamentos reais;
* visualizei limites dos elementos;
* testei alterações pequenas;
* comparei comportamento entre breakpoints.

O DevTools virou parte do processo de raciocínio, não apenas de correção.


