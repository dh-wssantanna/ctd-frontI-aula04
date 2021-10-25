# HTML: Estrutura semântica

## `<section>`

O elemento HTML `<section>` representa uma seção genérica contida em um documento HTML, geralmente com um título, quando não existir um elemento semântico mais específico para representá-lo.

### Notas de uso

- Cada `<section>` deve ser identificado, geralmente incluindo um cabeçalho `<h1>-<h6>` como um filho do elemento `<section>`.
- Se faz sentido distribuir separadamente o conteúdo de um elemento , use um elemento `<article>` em seu lugar.
- Não use o elemento `<section>` como um container genérico; para isso que a `<div>` serve, especialmente quando a seção é apenas com propósito de estilização. Uma regra de ouro é quando um seção deve aparecer logicamente na estrutura de um documento.

**Fonte:** https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/section

Você pode usar uma `<section>` para definir áreas ou regiões para:

- Textos introdutórios
- Listagens
- Mapas
- Comentários
- Informações de contato

``` html
<section>
  <h2>Título</h2>
  <p>Lotes de texto.</p>
</section>
```

## `<article>`

O Elemento HTML Article `<article>` representa uma composição independente em um documento, página, aplicação, ou site, ou que é destinado a ser distribuído de forma independente ou reutilizável, por exemplo, em sindicação. Este poderia ser o post de um fórum, um artigo de revista ou jornal, um post de um blog, um comentário enviado por um usuário, um gadget ou widget interativos, ou qualquer outra forma de conteúdo independente.

### Notas de uso

- Quando um elemento `<article>` está aninhado, o elemento interior representa um artigo relacionado com o elemento exterior. Por exemplo, os comentários do post de um blog podem ser elementos `<article>` aninhados em `<article>` representando o post do blog.
- Informações sobre o autor de um elemento `<article>` podem ser fornecidas através do elemento `<address>`, mas ele não se aplica aos elementos `<article>` aninhados.
- A data e hora de publicação de um elemento `<article>` pode ser descrita usando o atributo pubdate de um elemento `<time>`.

Normalmente se usa um `<header>` dentro do `<article>` e também pode ser aconselhável usar um `<footer>`.

**Fonte:** https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/article

Você pode usar uma `<article>` para definir áreas ou regiões para:

- Poste em Foruns
- Entradas de Blog
- Artigos

``` html
<article>
  <h2>Título</h2>
  <p>Lotes de texto.</p>
</article>
```

**Nota:** O que se observa é que você pode separa por exemplo um conjunto de articles em uma section, e em cada um desses articles você pode ter outras sections dentro. Por isso acredito que alguns de vocês tenham um pouco de dificuldade para interpretar quando utilizar `<articles>` e `<sections>`. 

## `<aside>`

O elemento HTML `<aside>` representa uma seção de uma página que consiste de conteúdo que é tangencialmente relacionado ao conteúdo do seu entorno, que poderia ser considerado separado do conteúdo. Essas seções são, muitas vezes, representadas como barras laterais. Elas muitas vezes contem explicações laterais, como a definição de um glossário; conteúdo vagamente relacionado, como avisos; a biografia do autor; ou, em aplicações web, informações de perfil ou links de blogs relacionados.
  
``` html
<aside>
  <p>Algum conteudo relacionado a um <article></p>
</aside>  
```

**Fonte:** https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/aside


## `<main>`

Diferente dos elementos `<section>` e `<article>` por exemplo, que não é aconselhável ter mais de um `<main>` por documento, ou defini-lo dentro de um `<article>`. É utilizado basicamente para se dá destaque a um conteúdo, pois define o conteúdo como o principal da página, ou seja, o que deve ser lido primeiro e o que descreve o conteúdo que a página possui.

**Fonte:** https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element/main

### Notas de uso
- Utiliza-se quando se deseja definir qual o conteúdo principal do documento e/ou para se destacar o primeiro conteúdo a ser lido pelos motores de busca
- Não se deve utilizá-lo mais de uma vez por documento
- Não se deve utilizá-lo dentro de `<article>`, `<aside>`, `<section>`
- É aconselhável se resumir as informações que deseja definir como principal. 

``` html
<main>
  <h1>Maçãs</h1>
  <p>A maçã é a fruta pomácea da macieira.</p>

  <article>
    <h2>Vermelho delicioso</h2>
    <p>Estas maçãs vermelhas brilhantes são as mais comumente encontradas em muitos supermercados.</p>
    <p>... </p>
    <p>... </p>
  </article>

  <article>
    <h2>Granny Smith</h2>
    <p>Essas suculentas maçãs verdes, são um ótimo recheio para torta de maçã.</p>
    <p>... </p>
    <p>... </p>
  </article>
</main>
```

## Modelo de Estrutura HTML construída com tag(s) semântica(s):

![Exemplo de Estrutura semântica](https://i.stack.imgur.com/cm0rd.jpg)

## "Estrutura HTML não semântica" versos "Estrutura semântica" 

![Exemplo de Estrutura não semântica vs Estrutura semântica](https://i.stack.imgur.com/w9ADa.jpg)

**Fonte:** https://www.vikingcodeschool.com/html5-and-css3/html5-semantic-tags

## Exemplo prático

Nesse exemplo vai ficar a critério do time definir o escopo e entendimento de como deve ser interpretado semanticamente "Missão, Visão e Valores". Se cada parte funciona sozinha ou se a mensagem só funciona em conjunto.

Se você entende que a "Missão, Visão e Valores" pertencem ao mesmo contexto, e não faria sentido, por exemplo, usar apenas os Valores de forma insolada em outras partes do site, te sugiro usar um article montado como abaixo:

``` html
<article>
  <h2>Missão, Visão e Valores</h2>
  <section>
    <h3>Missão</h3>
    <p>Lorem ipsum dolor sit amet.</p>
  </section>
  <section>
    <h3>Visão</h3>
    <p>Lorem ipsum dolor sit amet.</p>
  </section>
  <section>
    <h3>Valores</h3>
    <p>Lorem ipsum dolor sit amet.</p>
  </section>
</article>
```

Já se você acredita que é plenamente possível usar apenas a Missão em determinada parte da página e que mesmo insolada ela passaria a mensagem de forma adequada e não depende de Visão e Valores você pode separar "Missão, Visão e Valores" em `<article>` dentro de uma `<section>`, pois o `<article>` funciona de forma independente sem depender do restante do conteúdo ao redor.

``` html
<section>
  <h2>Missão, Visão e Valores</h2>
  <article>
    <h3>Missão</h3>
    <p>Lorem ipsum dolor sit amet.</p>
  </article>
  <article>
    <h3>Visão</h3>
    <p>Lorem ipsum dolor sit amet.</p>
  </article>
  <article>
    <h3>Valores</h3>
    <p>Lorem ipsum dolor sit amet.</p>
  </article>
</section>
```

## Validação HTML5
Conselho o uso das seguintes ferramentas:
- https://h5validator.appspot.com/dcm/asset 
- https://validator.w3.org/

## Link(s):
- https://developer.mozilla.org/pt-BR/docs/Web/Reference
- https://www.w3.org/standards/webdesign/
- https://html.spec.whatwg.org/
- https://www.w3schools.com/
