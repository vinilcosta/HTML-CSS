# Módulo 1 do Curso Html & Css

Anotações sobre o que foi visto no curso.

### Tags h e p

**h**: Dentro desse projeto do modulo 1 usamos a tag `<h1>` ,colocando dentro dela o titulo da pagina,usamos a tag `<h1>` para estruturar melhor o texto do site separando em titulo e paragrafos de texto.

**p**: Usamos a tag `<p>` para inserir o texto da página ou seja ela é uma tag paragrafo. 


### Tags strong e em 

**strong**:Tag usada para deixar texto em **negrito**.

**em**: Tag usada para deixar texto em *itálico*.

### Tags !DOCTYPE e html

**!DOCTYPE**: 
-  Tag de informação
-  Tag principal do html. 
-  Colocamos a exclamação para que a tag seja identificada como "!DOCTYPE".
-  Colocamos html ao lado da tag para que seja sinalizado que estamos usando a ultima versão disponivel do html.

**html**: Tag de conteúdo que serve para marcarmos tudo que é html dentro da nossa página que será renderizado no navegador,como ela é uma tag de conteúdo ela precisa abrir na primeira linha e fechar na ultima linha. 

### Tags meta  e title

**meta** :
-  Tag que passa informações para o navegador.
-  Dentro dela temos a propriedade charset="UTF-8.
-  O atributo charset que é o conjunto de caracteres,dicionário que estamos escolhendo.
-  Usamos o dicionário UTF-8 - dicionário que tem todos os caracteres que são usados na maioria das linguas do mundo inteiro.Com esses caracteres vamos resolver os problemas de acentuação.

**html lang**:Dentro da tag `html` vamos adicionar a propriedade `lang` que significa language e dentro 
              dela vamos usar `pt-br` que é o português do Brasil,setando assim o idioma da página.

**title**:Tag title é usada para alteramos o titúlo da aba da nossa página no navegador.

### Head e Body

O html tem uma divisão estrutural,Head e Body .

**Head**: Cabeça,na head é aonde passamos as informações para o navegador.

**Body**: Corpo,no body é aonde colocamos as informações que queremos exibir na página.

### Iniciando com Css

Começando a usar Css,vamos começar alterar a ,aparência dos itens.

**Utilizando a propriedade style**:A propriedade `style` é utilizada para alterar,a aparência dos itens. Colocamos o atributo `style` na frente da tag `p`,dentro do style vamos colocar a propriedade `font size`,para alterar o tamanho da fonte do texto dentro da tag `p` .
> Escrevemos : 
```html 
<p style="font-size:20px";>.  
```
**Utilizando a propriedade text-align**: Logo após,vamos alinhar,todos os itens ao centro da página,para isso usamos a propriedade `text-align`Ex: 

```html
<h1 style="text-align:center";> 
```

> **center** é o valor da propriedade.


**Css-Inline**: Temos três formas de configurar o Css,e o text-inline é uma delas ,na linha da nossa tag adicionamos as propriedades.

**tag style na head**: Outra forma de configurar o Css ,é colocando a tag `style` na `head` ,antes especificarmos a tag que queremos *alterar*.

**Criando um arquivo externo** 
Primeiro criamos um novo arquivo dentro do diretório que estamos trabalhando.Então precisamos fazer uma referencia do nosso `html` para o css vamos fazer com que o `html` busque o arquivo externo e passe a aplicar na nossa página.Para isso usamos a tag `link`.

-  A tag completa fica link rel(relacionamento do link) "stylesheet" (valor-folha de etilo) href=(endereço de referência)"style.css" .

**Mudando a Cor dos Componentes**
 
Vamos usar nosso arquivo externo,inserindo a tag pai,`body` referenciando o nosso html,assim a propriedade color vai desaguar sobre as tags filhas.

É importante organizar as tags do nosso arquivo Css de acordo com a ordem do nosso documento html.

Dentro da tag `body` usamos a propriedade `background` e logo após colocamos seu valor,que no caso é uma cor.

```Css
body{
    background: #cccccc;
}

p{
    text-align: center;
}
```

Da mesma forma,alteramos a cor da tag `strong` individualmente para dar destaque a essa determinada parte do texto e para especificar um pouco mais aonde vai ser mudada a cor ,colocamos antes da tag o local que ela esta inserida.

```Css
body{
    background: #cccccc;
}

p{
    text-align: center;
}

em strong{
    color:red;
}
```
**Marcador de identificação id**: Utilizamos o id para ,referenciar uma tag do html no Css que possui uma caracteristica que só ela carrega,ou seja o que o id carrega é unico.

Para referenciar um identificador no Css usamos # + o nome do id.

```Css
p{
       text-align:center;
}

#missao{
       font-size:20px
}
```
**Tag img**: Agora vamos adicionar uma imagem na nossa página,para adicionar usamos a tag `<img>` ,dentro da tag `img` precisamos colocar o atributo `src`,assim conseguimos linkar a imagem a tag.

```Html
<img src="banner.jpg">
```

**Css para imagens**: Para a edição da imagem precisamos adicionar no html um identificador a tag `img` no caso colocamos o nome do arquivo.

```Html
<img id="banner" src="banner.jpg">
```
 No Css referênciamos o id ,e dentro das chaves colocamos o atributo `width` que significa largura e seu valor,para que a imagem se adapte a nossa página.

```Css
 #banner{
     width:100%
 }
```

**Tags de lista li ul e ol** : 

As Listas são divididas em duas:
*  <ul>: Listas não ordenadas.

*  <ol>: Listas ordenadas.

Primeiro decidimos se nossa lista vai ser ordenada ou não ordenada e depois listamos os itens que a vão compor. 

*  É necessário que dentro da `<ul>` ou `<ol>` ,listemos item por item e fazemos isso com a `<li>`.

```html
<ul>
    <li>Atendimento aos Clientes</li>
    <li>Espaço diferenciado</li>
    <li>Localização</li>
    <li>Profissionais Qualificados</li>
</ul>
```    
**Classes no css**

Usamos as classes ,no css para marcarmos os itens e para posteriormente colocarmos ,estilos neles sendo eles repetiveis ou seja podemos marcar todos os nossos itens com a mesma classe.

```html
<ul>
    <li class="itens">*Atendimento aos Clientes</li>
    <li class="itens">*Espaço diferenciado</li>
    <li class="itens">*Localização</li>
    <li class="itens">*Profissionais Qualificados</li>
</ul>
```
Depois que criamos esses itens e suas classes,vamos criar um tamanho especifico para eles e coloca-los
em itálico e vamos criar a referência para a `class` no Css.

```Css
.itens{
    font-style:italic
}
```
**Divisões de Conteúdo** :
Para fazer a divisão de conteúdo utilizamos a tag `<div>`,separando o texto em: 

*  Todo texto de Apresentação.
*  Local aonde vai ter todos os beneficios apresentados para o nosso cliente.

Por padrão a `<div>`não afeta na apresentação visual do nosso conteúdo,ela serve para marcar nosso
conteúdo e a partir do Css fazermos os efeitos os efeitos que quisermos.
>Após separar com a `<div>` o texto aplicamos a `class`,para editarmos,cada `<div>`.

* 1°parte
```html
  <div class="principal">
      <h1>Sobre a Barberia Alura</h1>

      <p>
        Localizada no coração da cidade a <strong>Barbearia Alura </strong> traz
        para o mercado o que há de melhor para o su cabelo e barba. fundada em
        2019,a Barbearia Alura já é destaque na cidade e conquista novos
        clientes a cada dia.
      </p>
```
* 2° parte
```html
  <div class="beneficios">
      <h2>Benefícios</h2>

      <ul>
       <li class="itens">*Atendimento aos Clientes</li>
       <li class="itens">*Espaço diferenciado</li>
       <li class="itens">*Localização</li>
       <li class="itens">*Profissionais Qualificados</li>
      </ul>
    </div>
```
Logo após precisamos referenciar essas classes no Css:

```Css
body{
    
}
 #banner{
     width:100%
 }

.principal{
    background: #cccccc;
}
```

```Css

.itens{
    font-style: italic;
}

.beneficios{
        background: #ffffff;
}

h2{
    text-align: center;
}
```
Logo após as divs ,adicionamos mais uma imagem no site que ficará ao lado da lista de beneficios e que vamos editar.

```Html
    <img src="beneficios.jpg">
```

**inline e Block**
Antes de falarmos sobre o inline e o block,precisamos editar a imagem que adicionamos em nosso código.
Primeiro vamos adicionar uma class nela ,posiilitando assim a edição no css. 

```html
<img src="beneficios.jpg"class="imagembeneficios">
```

Assim conseguimos colocar nossa imagem com 50% de seu tamanho na página.

```Css
.imagembeneficios{
    width:50%;
}
```
*  Block: comportamento que algumas tags possuem,caracterizado por ocupar toda linha da página (bloqueando todo conteúdo daquela linha.)

*  Inline:Comportamento que difere do block,pois não blockeia o conteúdo ,mas permite que tenha outros itens ao seu lado .

*  inline-block:essa terceira opção bloqueia um largura mas essa largura é fixa e nós que determinamos,sendo possivel editar o espaçamento externo e interno.

Então vamos aplicar o conceito de inline-block na nossa `<ul>` com o atributo display para entendermos mais um pouco, block ,inline e inline -block estão **todos ligados ao display**.

```Css
ul{
    display:inline-block;
}
```
Porém precisamos adicionar mais um atributo que é `vertical-align:top` para que nossa lista não fique ebaixo mas na parte de cima.

```Css
ul{
    display:inline-block;
    vertical-align:top;
}
```
Agora vamos adicionar na nossa lista de itens ,alterar a largura e a margem como ela é um item inline-block temos essa liberdade.

```Css
ul{
    display:inline-block;
    vertical-align:top;
    width:20%;
    margin-right:15%;
}

Agora vamos editar o espaçamento dos dois blocos principais.

```Css
.beneficios{
    background:#ffffff;
    padding:20px;
}
```
Teremos mais margens de respiro em volta do elemento.

```Css
.principal{
    background:#cccccc;
    padding:30px;
}
```

**Cabeçalho**
Para criar o nosso cabeçalho ,dentro da tag body,vamos criar a tag `<header>`,sendo o conteúdo principal da nossa pagina,vamos colocar dentro da tag `<header>` a tag de titúlo `<h1>`,e vamos alterar as tags dos titúlos que haviamos editado antes,de `<h1>` para `<h2>` e de `<h2>` para `<h3>`.

Porém o h1 e o h2 já possuiam atributos no Css ou seja nosso site ficou uma bagunça.

Para arrumá-lo vamos adicionar as classes no `<h2>` e `<h3>`:

```html
<h2 class="titulo-centralizado">Sobre a barbearia Alura</h2>

<h3 class="titulo-centralizado">Beneficios</h3>
```
No Css vamos apagar a declaração para o h2 e aonde temos a declaração para o `<h1>`,trocamos ela para classe que acabamos de adicionar no nosso html.

```Css
.titulo-centralizado{
    text-align:center
}
```

E para finalizar vamos dar um espaçamento interno no titulo principal ou seja `<h1>`,e faremos o mesmo processo de antes ,no html vamos criar uma classe para o `<h1>` e referênciar no Css depois.

```html
<h1 class="titulo-principal">Barbearia Alura</h1>
```
>No Css

```Css
.titulo-principal{
    padding-left: 20px;
}
```