# Módulo 4 do Curso de Html & Css

**Anotações do que foi visto no curso**

**Refazendo a página inicial**

Vamos iniciar a edição da nossa página, ao acessarmos `produtos.html`, copiaremos o `reset.css` e `style.css` para `index.html`.

```html
<link rel="stylesheet" href="reset.css">
<link rel="stylesheet" href="style.css">
```
Com a inserção desse código, as margens da página ficam maiores e os elementos ficam desorganizados.

O cabeçalho da página inicial é diferente do que temos na página de produtos, portanto copiaremos o cabeçalho de `proutos.html` e inseriremos em `index.html`.

```Html
<header>
            <div class="caixa">
                <h1><img src="logo.png"></h1>

                <nav>
                    <ul>
                        <li><a href="index.html">Home</a></li>
                        <li><a href="produtos.html">Produtos</a><li>
                        <li><a href="contato.html">Contato</a></li>
                    </ul>
                </nav>
            </div>
</header>
```
A página inicial também não possui rodapé, então novamente coletaremos o código de rodapé da página de produto, que deverá ser inserido entes da última `<div>` em `index.html`.

```Html
<footer>
            <img src="logo-branco.png">
            <p class="copyright">&copy; Copyright Barbearia Alura - 2019</p>
</footer>
```

Feito isso, precisamos melhorar a marcação que fizemos na página inicial, que estava muito simples. Sabemos que todo conteúdo precisa ser muito bem dividido e marcado, e para delimitar o conteúdo principal precisamos da tag `<main>`, semelhante a que temos na página de produto. Dito isso, envolveremos todas as informações principais nesta tag.

```html
<img id="banner" src="banner.jpg">

<main>
            <div class="principal">
                <h2 class="titulo-centralizado">Sobre a Barbearia Alura</h2>

                <p>Localizada no coração da cidade a <strong>Barbearia Alura</strong> traz para o mercado o que há de melhor para o seu cabelo e barba. Fundada em 2019, a Barbearia Alura já é destaque na cidade e conquista novos clientes a cada dia.</p>

                <p id="missao"><em>Nossa missão é: <strong>"Proporcionar auto-estima e qualidade de vida aos clientes"</strong>.</em></p>

                <p>Oferecemos profissionais experientes e antenados às mudanças no mundo da moda. O atendimento possui padrão de excelência e agilidade, garantindo qualidade e satisfação dos nossos clientes.</p>
            </div>

            <div class="beneficios">
                <h3 class="titulo-centralizado">Benefícios</h3>

                <ul>
                    <li class="itens">Atendimento aos Clientes</li>
                    <li class="itens">Espaço diferenciado</li>
                    <li class="itens">Localização</li>
                    <li class="itens">Profissionais Qualificados</li>
                </ul>

                <img src="beneficios.jpg" class="imagembeneficios">
            </div>
</main>
```
A imagem não foi inclusa dentro da tag, pois ela não faz parte do conteúdo principal, trata-se apenas de uma imagem de exibição e que deve estar em destaque e ocupar toda a extensão da tela no sentindo horizontal.

Em nosso site, temos uma descrição com o título "Sobre a Barbearia Alura". Trata-de se informações que são fechadas em si mesmas, como uma sessão. Em nosso código esse conteúdo está sendo envolvido por uma `<div>`, mas para casos assim utilizamos a tag `<section>`.

```Html
<section class="principal">
                <h2 class="titulo-centralizado">Sobre a Barbearia Alura</h2>

                <p>Localizada no coração da cidade a <strong>Barbearia Alura</strong> traz para o mercado o que há de melhor para o seu cabelo e barba. Fundada em 2019, a Barbearia Alura já é destaque na cidade e conquista novos clientes a cada dia.</p>

                <p id="missao"><em>Nossa missão é: <strong>"Proporcionar auto-estima e qualidade de vida aos clientes"</strong>.</em></p>

                <p>Oferecemos profissionais experientes e antenados às mudanças no mundo da moda. O atendimento possui padrão de excelência e agilidade, garantindo qualidade e satisfação dos nossos clientes.</p>
</section>
```
A diferença entre `<div>` e `<section>` é que no primeiro caso, trata-se apenas de uma divisão visual. Já no caso da `<section>` teremos uma divisão por conteúdo complexo, semanticamente homogêneo.Na parte de benefícios, também possuímos conteúdos fechados em si, neste caso também substituiremos a `<div>` por `<section>`.

```html
<section class="beneficios">
                <h3 class="titulo-centralizado">Benefícios</h3>

                <ul>
                    <li class="itens">Atendimento aos Clientes</li>
                    <li class="itens">Espaço diferenciado</li>
                    <li class="itens">Localização</li>
                    <li class="itens">Profissionais Qualificados</li>
                </ul>

                <img src="beneficios.jpg" class="imagembeneficios">
            </section>
```
Ao retornarmos para o navegador, perceberemos as sessões centralizadas, mas ainda resta fazermos ajustes nas imagens, lista de benefícios.

**Adaptando o Css**

Vamos começar fazendo a transposição de alguns itens ,o primeiro que vamos modificar é o nosso `id` sabemos que ele é muito forte então vamos alterá-lo para uma `class` é uma forma facil de sobreescrever ela  a força dela não é tão grande você consegue mudar o estilo e seguimos um padrão no nosso código.

```Html

 <img class="banner" src="reis-26-1_DAlXy0wng-unsplash 1 (1).png" />

 ```
 >Sempre que queremos falar de estilo usamos uma classe e sempre que queremos falar de comportamento usamos o identificador.


Logo após vamos ao nosso Css,no final do nosso documento vamos fazer referência a nossa classe `banner`,é muito recomendado utilizarmos comentários para nos localizar no código ou colocarmos algum lembrete.

* Editando a `class` .banner vamos aumentar a largura da imagem para 100% .

```Css
/*css da página inicial*/
.banner {
  width:100%;
}
```
* O próximo elemento a ser editado vai ser a `class` `titulo-centralizado`,é importante dizer que que a classe `titulo-centralizado` não possui um bom nome, afinal sempre que criamos uma classe do CSS é importante que ela seja específica e ao mesmo tempo o mais genérica possível. Quando temos um nome como "titulo centralizado", estamos imprimindo um comportamento, então se quiséssemos alinhar o título à esquerda, teríamos de modifcar o nome da classe, ou criar uma nova.Então vamos alterar o nome dessa class para `.titulo-principal`.

* Vamos alinhar nosso titulo ao centro com a tag `text-align:center` e depois vamos alterar nossa fonte,utilizando a propriedade `font-size`.

* As medidas proporcionais no CSS são um assunto crucial no mento de definir escalas, tamanho de fonte e assim por diante. Até agora em nosso projeto utilizamos pixel e percentual, no caso do percentual ela se trata de uma media proporcional, como notamos ao definir que a imagem do banner deveria o ocupar 100% de largura em relação a página, se quiséssemos que o banner ocupasse metade da largura da página, bastaria escrever 50%.

Se quisermos que a fonte de titulo-principal seja o dobro da fonte padrão, independe do tamanho dessa fonte padrão, utilizamos a medida `em`, a media proporcional para pixels. Se quisermos duas vezes o tamanho base (15 pixels), basta escrever `2em`.

* Incluiremos uma margem de 0 0 1em. É sempre interessante inserir um espaçamento que seja proporcional ao tamanho da fonte, o que facilita a leitura do usuário.

```css
.titulo-principal {
    text-align: center;
    font-size: 2em;
    margin: 0 0 1em;
}
```
* Agora vamos editar nossas tags de paragrafo criando uma margem para baixo proporcional ao tamanho da fonte.

```Css
.principal p {
    margin: 0 0 1em;
}
```
* Não podemos esquecer que toda vez que tivermos a tag `strong` a fonte tenha o peso em `negrito` e quando usarmos a tag `em` o estilo da fonte fique em `itálico`

```Css
.principal strong {
    font-weight: bold;
}

.principal em {
    font-style: italic;
}
```

* Na sections dos beneficios vamos mudar o nome da classe para "titulo-principal" igual ao titulo acima.

```Html
<section class="beneficios">
        <h3 class="titulo-principal">Benefícios</h3>
```
* E para finalizar vamos redimensionar nossa imagem ,indo até o Css vamos referenciar a classe "imagembeneficios" e aplicar na imagem como ela é proporcional a página,vamos aplicar o `width:60%` .

```Css
.imagembeneficios {
    width: 60%
}
```

**Usando o Float**

Para iniciar vamos começar editando o "sobre" e vamos colocar uma imagem no canto esquerdo do texto,então no nosso html,logo abaixo do nosso titúlo principal vamos aplicar a imagem.

```html
<img class="utensilios" src="utensilios.jpg" alt="Utensilios de um barbeiro.">
```
Agora vamos editar a dimensão dessa imagem referenciando a classe no Css após o seletor `.principal em`,tendo uma largura de `150px`.

```Css
.utensilios {
    width: 150px;
}
```
O próximo passo é fazer com que o texto englobe essa imagem. Conhecemos algumas formas de tratar esses elementos, a primeira é utilizar o `display` do elemento para `inline-block`, e então todos os parágrafos seguirão o mesmo modo. Neste caso específico esta abordagem não funcionará, pois o `display` altera o comportamento do elemento padrão, e neste caso queremos que a imagem ocupando uma área específica e que o texto ocupe a largura inteira da página, mas que ceda espaço para a imagem.

Estudamos também o `posicionamento(position) relativo`, que coleta o ponto inicial e a partir disso faz deslocamentos. Aprendemos ainda sobre o `posicionamento absoluto`, em que podemos deslocar o ponto inicial para qualquer lugar. Neste caso, a imagem ficará por cima do texto, descolada da apresentação. Em suma, trabalhar com position não resolverá nossos problemas.

Temos, ainda, mais uma forma de posicionar e tratar elementos: o `float`, em tradução livre "flutuação". Quando utilizamos este recurso,o elemento "descola" da página mas o que seria a sua sombra, continua sendo ocupada virtualmente, isto é, o texto respeita esse espaço ocupado.

Para fazermos nossa imagem "flutuar" acessaremos `style.css` e definiremos em utensilios qual é o lado que desejamos que a flutuação ocorra, neste caso, `left`.

```Css
.utensilios {
    width: 150px;
    float: left;
}
```
Só que quando usamos o float ele afeta todos os elementos que estão abaixo dele ,fazendo uma bagunça,por isso utilizamos a propriedade `clear` e vamos colocar ela na classe do item que vem abaixo do float ,`clear` tem uma função de delimitar o float como se fosse uma barreira,vamos limpar o `float` que está a esquerda.

```Css
.titulo-principal {
    text-align: center;
    font-size: 2em;
    margin: 0 0 1em;
    clear: left;
}
```
Conseguimos delimitar a ação do float, mas o texto continua muito junto à imagem. Em utensilios, adicionaremos uma margem de 20px para a direita, 20px para baixo e 0 para a esquerda e vamos reduzir a imagem para 120px .

```Css
.utensilios {
    width: 120px;
    float: left;
    margin: 0 20px 20px 0;
}
```

**Fontes externas**

Agora vamos aprender a utilizar as fontes externas ,é interessante que existem diversos tipos de fontes externas algumas exclusivas da apple,microsoft porém temos algumas gratuitas para utilizarmos.

E aonde vamos pegar essas fontes vai ser no site da google ,`https://fonts.google.com/` ,nesse site vamos selecionar a fonte que queremos e vamos inportar ela  através do código em html que eles disponibilizam no site.

* Primeiro copiamos o código no site do google fonts logo após,colamos na nossa `head`.

```html
 <head>
    <meta charset="UTF-8" />
    <title>Barbearia Alura</title>
    <link rel="styleshet" href="reset.css" />
    <link rel="stylesheet" href="style.css" />
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto&display=swap" rel="stylesheet">

  </head>
```
* Depois precisamos referenciar isso no nosso Css,como queremos que essa fonte esteja em todo conteúdo vamos colocar no seletor body.

```Css
body{
  font-family: 'Roboto', sans-serif;
}
```
**Trabalhando com Mapas**

Antes de importar os mapas para nossa página,precisamos inserir o titulo  com a `class="titulo-principal"`informando o elemento que vamos inserir ali e um breve texto para ambientar o usuário esses dois dentro de uma `section`.

* Logo após já podemos importar nosso mapa ,para isso vamos até o `maps.google.com` ,primeiro precisamos colocar o endereço desejado e depois precisamos exportar isso vamos até a opção `compartilhar ou incorporar um mapa` quando clicamos ela nos da a possibilidade de termos um link para aquele mapa especifico ou a parte de incorporar um mapa.

* Vamos utilizar a opção incorporar um mapa, copiar o html e colar no nosso documento,quando colamos podemos ver uma nova tag chamada `iframe` que é especifica para isso,ela abre uma janela no nosso site aonde dentro dela podemos delimitar seu tamanho altura ,tendo uma propriedade para exportarmos o endereço (**src**) e preencher aquela janela,podemos usar essa tag para diversos serviços que disponibilizam essa possibilidade.

* Também vamos editar o espaçamento do elemento dentro da tag iframe com width="100%" heigth="300" .

```html
<iframe src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!
1d3656953901466093!2d-46694118184466724!3d-2357009906780141!2m3!1
f0!2f0!3f0!3m2!1i1024!2i768!4f131!3m3!1m2!1s0x94ce577ceebc565f%3A
0x47c22a0d727acc8e!2sPagSeguro%20PagBank!5e0!3m2!1spt-BR!2sbr!4v1
648089561584!5m2!1spt-BR!2sbr" width="600" height="450" style="border:0;" allowfullscreen="" loading="lazy"></iframe>

```

* Vamos editar os elementos da `section="mapa"` la no documento style.css na ultima linha vamos referenciar a nossa classe `.mapa` e fazer a edição dos elementos.

```Css
.mapa{
    padding:3em 0;
}

.mapa p{
    margin: 0 0 2em;
    text-align:center;
}
```

**Importando Vídeo**

Agora vamos importar um video para nossa página,esse video será importado do youtube, e da mesma forma vamos até a opção compartilhar logo após vamos até "incorporar" assim vamos copiar o conteúdo do iframe e colar no nosso html,importando assim o video.

Se nos atentarmos na nossa página exemplo nosso video está centralizado,para centralizar ele vamos envolvê-lo em uma `div` e colocar a `class="video"` para poder editá-lo.

```Html
<div class="video">
        <iframe
          width="560"
          height="315"
          src="https://www.youtube.com/embed/wcVVXUV0YUY"
          title="YouTube video player"
          frameborder="0"
          allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
          allowfullscreen
        ></iframe>
      </div>
```
No Css vamos aplicar ao nosso video ,a largura de 560px a margin vai ser de `1em` para cima e para baixo e automática nas laterais.

```Css
.video{
  width: 560px;
  margin: 1em auto;
}
```
**Pseudo-Classes**

Nós já vimos alguns Pseudo-elementos , como `:hover`,`:active`,`visited`,`:required`,são propriedades que usamos para marcar melhor nossos elementos,agora vamos começar a tratar todo css da parte dos beneficios e usar os pseudo-elementos,a primeira coisa que vamos fazer é alinhar o conteúdo ao tamanho que queremos,ao ver a imagem e a lista o professor deduziu que a lista ocupa 40% e a imagem 60%.
Para editar esses dois elementos vamos utilizar uma `div` englobando eles ,e vamos aplicar uma `class="conteudo-beneficios"` para assim referenciarmos no css.

```Html
    <div class="conteudo-beneficios">
        <ul>
          <li class="itens">Atendimento aos Clientes</li>
          <li class="itens">Espaço diferenciado</li>
          <li class="itens">Localização</li>
          <li class="itens">Profissionais Qualificados</li>
        </ul>
        <img src="beneficios.jpg" class="imagembeneficios" />
  </div>   
```

* Na nossa lista vamos aplicar uma `class` para usarmos a classe ao invés da tag e na classe de imagem vamos alterar para `imagem-beneficios`.

```Html
    <div class="conteudo-beneficios">
        <ul class="lista-beneficios">
          <li class="itens">Atendimento aos Clientes</li>
          <li class="itens">Espaço diferenciado</li>
          <li class="itens">Localização</li>
          <li class="itens">Profissionais Qualificados</li>
        </ul>
        <img src="beneficios.jpg" class="imagem-beneficios" />
  </div>   
```
* No nosso Css já temos a classe `imagembeneficios` vamos corrigi-la e vamos criar o seletor `.conteudo-beneficios`,vamos aplicar a `width` de 640px; a margin automatica para os lados `margin: 0 auto;`e por últimos vamos criar nosso .lista-beneficios que terá 40% de largura.

```Css
.conteudo-beneficios{
    width:640px;
    margin:0 auto:
}
.lista-beneficios{
    width:40%;
}
.imagem-beneficios{
    width:60%;
}
```
* Ao recarregar, nossa lista ainda fica acima da nossa imagem,precisamos alterar o display afinal de contas a lista é um conteúdo `inline` porém o item da lista é um elemento `block` ocupando 100% da largura da página,para alterar isso vamos no nosso lista-beneficios e vamos aplicar a propriedade `display;inline-block` .
```Css
.conteudo-beneficios{
    width:640px;
    margin:0 auto:
}
.lista-beneficios{
    width:40%;
    display:inline-block;
}
.imagem-beneficios{
    width:60%;
}
```
* Recarregando a página  ela continua da mesma maneira,mas o display inline-block tem um pequeno detalhe que muda completamente a exibição e esse detalhe é o seguinte ele interpreta no nosso html,tudo que colocarmos inclusive o espaço vazio entre as tags `ul` e `div` ,então quando estamos usando o `inline-block`e queremos usar 100% da largura esses elementos precisam estar colados um do lado do outro .

```Html
<ul class="lista-beneficios>
          <li class="itens">Atendimento aos Clientes</li>
          <li class="itens">Espaço diferenciado</li>
          <li class="itens">Localização</li>
          <li class="itens">Profissionais Qualificados</li>
        </ul><img src="beneficios.jpg" class="imagembeneficios" />
```
* Agora sim nossa lista e nossa imagem estão uma do lado da outra,porém queremos alinhar nossa lista pela parte de cima e não a de baixo,então vamos usar o `vertical-align:top;`

```Css
.conteudo-beneficios{
    width:640px;
    margin:0 auto:
}
.lista-beneficios{
    width:40%;
    display:inline-block;
    vertical-align:top;
}
.imagem-beneficios{
    width:60%;
}
```
* Vamos aumentar um pouco do espaçamento externo do video para `2em`.

```Css
.video{
  width: 560px;
  margin: 1em auto;
}
```
* Logo após vamos criar uma section`.beneficios` e vamos aplicar a mesma configuração  da section `.mapa`,

```Css
.beneficios{
    padding:3em 0;
}
```
* Vamos aplicar mais dois itens na nossa lista ,pontualidade e limpeza.

```Html
    <div class="conteudo-beneficios">
        <ul class="lista-beneficios">
          <li class="itens">Atendimento aos Clientes</li>
          <li class="itens">Espaço diferenciado</li>
          <li class="itens">Localização</li>
          <li class="itens">Profissionais Qualificados</li>
          <li class="itens">Pontualidade</li>
          <li class="itens">Limpeza</li>
        </ul>
        <img src="beneficios.jpg" class="imagem-beneficios" />
  </div>   
```
* Também vamos editar os itens da nossa lista, criando um seletor `.itens`no Css para fazer um espaçamento entre os textos da lista usamos a propriedade `line-height` que é a altura da linha,a altura da linha normalmente é proporcional ao tamanho da fonte que é `line-height:1em;` mas vamos colocar como 1.5.

```Css
.itens{
    line-height:1.5;
}
```
* Agora vamos aplicar os pseudo-elementos,queremos que só o nosso primeiro item fique em negrito , porém precisamos ficar atentos pois se alterarmos a classe vamos editar todos os nossos itens,e se colocarmos uma única classe no item a ser alterado,vamos estar fazendo o html fazer o trabalho do Css,para isso vamos utilizar os pseudo-elementos, referenciando o seletor `.itens:` com os dois pontos para usarmos alguns pseudo-elementos,e para seleção de elementos especificos nós temos três opções a primeira delas é usar uma classe pseudo-elemento,nos vamos usar aqui a `.itens:first-child` esse pseudo-elemento vai pegar de todos os irmãos de todas as crianças de todos os childs o primeiro deles,nós temos seis itens que são irmãos na lista e o primeiro deles digo que o peso da fonte vai ser em negrito,com isso nós criamos via Css uma marcação para o primeiro item é como se criassemos aquela classe fazemos isso através dos pseudo-elementos.

```Css
.itens:first-child{
    font-weigth:bold
}
```
Dessa maneira, o primeiro item estará em negrito ao carregarmos o navegador. Dessa maneira criamos, via CSS, uma marcação. Além do first-child, temos a opção `last-child` que marcará o último item da lista. Isso é interessante, porque não precisaremos mais saber quantos itens existem na lista para passar configurações precisas, essa caracaterística é muito útil em manipulação de tabelas, por exemplo.
Temos também o `nth-child()`onde entre parênteses colocamos o numero do item desejado para alteração,podemos utilizar dentro dos parêntese o valor de `n` quer dizer que se entre parenteses temos `(2n)` eu estou me referindo a todos elementos pares da lista ou da tabela.


**Aplicanddo Gradiente**

Primeiramente, trabalharemos a sessão "Sobre a barbearia Alura", que chamamos de principal. Precisamos adequá-la ao estilo das demais sessões, para tanto, criaremos .principal em style.css. Adicionaremos o padding de 3em 0 e o background com um tom quase branco, cujo código é #FEFEFE.

```Css
.principal {
    padding: 3em 0;
    background: #FEFEFE;
} 
```
Em beneficios, inseriremos a cor cinza escuro:

```Css
.beneficios { 
    padding: 3em 0;
    background: #888888;
```
Notaremos que a cor cinza não ocupa toda a extensão da página, mas sim uma grande faixa central. Isso ocorre porque configuramos a centralização da página em `<main>`, o que não vai funcionar. Recortaremos o conteúdo de `.main` em style.css:

```Css
main {
    width: 940px;
    margin: 0 auto;
}
```
E então inseriremos esse conteúdo no elementos principal . Dessa maneira, o fundo cinza já ocupara toda a área da tela.

```Css
.principal {
    padding: 3em 0;
    background: #FEFEFE;
    width: 940px;
    margin: 0 auto;
}
```
Se inserirmos qualquer cor de fundo de mapa por meio da propriedade background, teremos complicações no layout, afinal a cor só ocupará uma faixa central. Se adicionarmos o `width` e `margin` com os valores de principal deformaremos o mapa, que passará a ocupar a página inteira, e não queremos isso.

Para evitar esse problema, em nosso código HTML criaremos uma nova `<div>` que envolverá o mapa, além disso, criaremos uma classe específica que se chamará `.mapa-conteudo`.

Em style.css, mapa-conteudo abrigará as propriedades `width` e `margin` com os valores específicos.

```Css
.mapa-conteudo {
    width: 940px;
    margin: 0 auto;

}
```
Dessa maneira, o mapa ficará centralizado, com as proporções que desejamos. Com essas modificações, estamos prontos para trabalhar com a propriedade background em mapa. Precisamos aqui ajustar a transição da cor branca para o cinza, então utilizaremos o linear-gradient() que receberá as cores que desejamos trabalhar. O interessante dessa propriedade é que podemos adiciconar quantas cores quisermos, que o CSS irá administrá-las automaticamente. É possível, inclusive, ajustar a inclinação das cores, por exemplo `45deg` e então ficarão posicionadas em 45º.

```Css
.mapa {
    padding:3em 0;
    background: linear-gradient(45deg, orange, blue, red, black);
}
```

Como estamos utilizando quatro cores no exemplo, há valores subentendidos em cada uma delas, na sequência: 0%, 25%, 50%, e 75% para a última cor da sequência. Mas podemos manipular esses valores de acordo com nosso interesse , como definir que orange, por exemplo, terá o valor de 50%.

```Css
.mapa {
    padding:3em 0;
    background: linear-gradient(45deg, orange 50%, blue, red, black);
}
```
Além do `degradê linear(linear-gradient)` temos ainda a opção `radial(radial-gradient)`, que organiza a transição de cores de maneira circular. Nosso site terá uma gradação de cinza linear

```Css
.mapa {
    padding:3em 0;
    background: linear-gradient(#FEFEFE, #888888);
}
```
**Pseudo-elementos**

Utilizaremos o título "Nosso estabelecimento" para entendermos as possibilidades do CSS. Se quisermos negritar apenas a primeira letra desse título? Com os conhecimentos que temos até agora, isso seria possível?

Não, pois estudamos seletores avançados de classe, identificadores, mas nada que possibilitasse a marcação de uma única letra. Contudo, essa é uma ação possível graças às atualizações e melhorias no CSS. Na tag titulo-principal, utilizaremos o pseudo-elemento first-letter para definir o peso da fonte.

```Css
.titulo-principal {
    text-align: center;
    font-size: em;
    margin: 0 0 1em;
    clear: left;
}

.titulo-principal:first-letter {
    font-weight: bold;
}
```
Ao carregarmos a página, teremos a primeira letra do título "Nosso estabelecimento" em negrito, isto é, a letra "N". Outra opção interessante, muito comum no mercado editorial, é configurar a primeira linha para itálico. Para tanto, ajustamos para que todos os parágrafos (p) terão a primeira linha (first-line) no estilo italic.

```Css
p:first-line {
    font-style: italic;
}
```
Conheceremos ainda outros dois pseudo-elementos do CSS: `after` e `before`. Esses dois elementos criam espaço para que o CSS atue antes ou depois de um determinado conteúdo. Continuaremos utilizando o título para entender como a sintaxe se dá:

```Css
.titulo-principal:before {
    content: "[";
}

.titulo-principal:after {
    content:"]"
}
```
Dessa maneira, ao recarregarmos a página o título estará envolvido por colchetes: "[Nosso estabelecimento]". É interessante mencionar que esse conteúdo - os colchetes - não são selecionáveis pelo mouse, trata-se apenas de uma informação visual e não um conteúdo manipulável. Utilizaremos os caracteres unicode para inserir estrelas na lista da sessão "Benefícios", que trabalhávamos na aula anterior.

Procuraremos no Google por "unicode star" e copiaremos o conteúdo da estrela que acharmos visualmente mais interessante. Em nosso CSS, trabalharemos na classe itens, utilizaremos o pseudo-elemento before para que antes do conteúdo da lista, haja uma estrela.

```Css
.itens:before {
    content: ""
}
```
Ao carregarmos a página, teremos as estrelas marcadas em cada item da lista. Novamente trata-se de um elemento não selecionável, apenas conteúdo de exibição.


**Seletores Avançados**

Nesta aula, estudaremos os seletores avançados, uma forma específica de fazermos seleção de elementos de maneira mais rebuscada. Suponhamos que no interior da `<main>`, antes de se iniciar a `<section>`, nós tenhamos um `<p>` com um conteúdo qualquer. Se retornarmos para o nosso CSS.

```Html
<main>
            <p> qualquer conteudo</p>

            <section class="principal">
                <h2 class="titulo-principal">Sobre a Barbearia Alura</h2>

                <img class="utensilios" src="utensilios.jpg" alt="Utensilios de um barbeiro." />

                <p>Localizada no coração da cidade a <strong>Barbearia Alura</strong> traz para o mercado o que há de melhor para o seu cabelo e barba. Fundada em 2019, a Barbearia Alura já é destaque na cidade e conquista novos clientes a cada dia.</p>

                <p id="missao"><em>Nossa missão é: <strong>"Proporcionar auto-estima e qualidade de vida aos clientes"</strong>.</em></p>

                <p>Oferecemos profissionais experientes e antenados às mudanças no mundo da moda. O atendimento possui padrão de excelência e agilidade, garantindo qualidade e satisfação dos nossos clientes.</p>
</section>
```
No CSS, como fazemos para marcar esse parágrafo de vermelho? Podemos tentar escrever:
```Css
main p {
    background: red;
}
```
Ao carregarmos no navegador, veremos que todos os parágrafos estarão marcados de vermelho, pois coletamos os parágrafos que estavam dentro da <section>, afinal coletamos todos os parágrafos que estão dentro da <main>. Como podemos selecionar um parágrafo de maneira individual?

Com os seletores avançados do CSS,podemos selecionar os filhos diretos de <main>, para tanto, utilizaremos o sinal >, e todo os outros parágrafos serão ignorados, afinal são filhos diretos da <section> e não de <main>.

```Css
main > p {
    background: red; 
}
```
Mas como selecionar o primeiro parágrafo que sucede uma imagem, por exemplo? Conseguimos selecionar o primeiro filho com o seletor que acabamos de conhecer, mas neste caso estamos falando do primeiro irmão que vem depois de um elemento.

Neste caso, usamos `img` como elemento âncora e para o primeiro irmão usamos o sinal de "+"

```Css
img + p { 
    background: blue;
}
```
> Para selecionar todos os parágrafos localizados depois de uma imagem usamos o seletor ~

```Css
img ~ p {
    background: yellow
} 
```
É importante lembrar que um seletor pode sobrescrever o outro, pois todos possuem a mesma força. Os seletores avançados nos ajudam a criar *estilos mais complexos* e utilizar o CSS de uma maneira incrível, com uma autonomia maior do HTML.

No CSS podemos, inclusive, excluir itens específicos. Se quisermos excluir todos os parágrafos que não compõe missao, escreveremos:
```Css
.principal p:not(#missao) {
    background: orange;
}
```
A exclusão é um elemento poderoso no CSS, principalmente quando realizamos manutenção em algum código que já existe e que não devemos modificar tanto o HTML.

**Cálculo com Css**

Nosso site deve estar preparado para dispositivos com diversos tamanhos de tela. Um grande problema enfrentado ao desenvolver um site harmonioso é justamente calcular a proporção das dimensões dos elementos em diferentes dispositivos.

Se Clicarmos sobre a imagem de utensílios de barbeiro com o botão direito do mouse, e selecionarmos a opção "Inspecionar" para acessarmos a ferramenta do desenvolvedor.

Em nosso CSS, verificaremos que o tamanho da imagem é de 120px, mas como podemos fazer com que esse tamanho seja proporcional? Basta mudar para percentual, isto é, 20% de largura tendo a tela como referência.

Para que a imagem sempre ocupe a medida correta em outros dispositivos, utilizamos a propriedade calc. O calculo que desejamos realizar é escrito entre parênteses, em que inserimos o primeiro valor, o tipo de operção e o resultado esperado.

```Css
.utensilios {
    width: calc(40% - 26px);
    float: left;
    Margin: 0 20px 20px 

}
```
Dessa forma, foi calculado precisamente 350px de largura para este elemento. É possível encadear quantas operações quisermos, no mesmo modelo de sintaxe.

```Css
.utensilios {
    width: calc(40% - (26px * 4);
    float: left;
    Margin: 0 20px 20px 

}
```
A propriedade calc nos dá o poder de fazer com o que cremos valores proporcionais específicos.

**Opacidade nos elementos**

Utilizaremos a imagem da sessão "Benefícios" para compreendermos o funcionamento da ferramenta de opacidade no HTML. Em Style.css , utilizaremos a propriedade `opacity` que pode ter valores **entre 0 a 1**, sendo que 0 o elemento estará totalmente oculto. Se quisermos exibir a imagem com opacidade de 30%, ajustaremos o valor da propriedade para 0.3.

```Css
.imagem-beneficios {
    width: 60%
    opacity: 0.3;
}
```
Esse recurso é interessante quando montamos composições visuais com elementos sobrepostos, ou para sugerir interações com o mouse ao utilizarmos o `hover.` Quando o mouse estiver posicionado sobre a imagem teremos 1 de opacidade.

```Css
.imagem-beneficios:hover {
    opacity: 1;
}
```
Temos ainda o recurso `transition`, em que podemos estabelecer uma transição da opacidade em determinados milissegundos.

```Css
.imagem-beneficios {
    width: 60%;
    opacity: 0.3;
    transition: 400ms;
}
```
Em nosso site, faremos com  que o comportamento padrão da imagem seja de opacidade 1, e no momento em que mouse estiver sobre ela a opacidade será de 0.3, o que irá gerar um belo efeito visual.

Atualmente, podemos utilizar opacidade em todos os elementos e em cores, vamos entender melhor como isso ocorre.

A cor de titulo-principal possui a cor padrão #00000, preto. Como podemos fazer com que essa cor que está em hexadecimal? se torne RGB? Isto é, a mesma cor escrita em outra linguagem? Do seguinte modo:

```Css
.titulo-principal {
    text-align: center;
    font-size: 2em;
    margin: 0 0 1em;
    clear: left;
    color: rgb(0,0,0);
}
```
Com CSS 3, podemos utilizar mais uma camada - a de opacidade, chamada alfa - nas cores em RGB. Para tanto, utilizamos o rgba e então definir os valores que quisermos.

```Css
.titulo-principal {
    text-align: center;
    font-size: 2em;
    margin: 0 0 1em;
    clear: left;
    color: rgb(0,0,0,0.3);
}
```
Esse recurso pode ser utilizado em todas as cores: de fundo, texto, borda e assim por diante.

**Sombra nos Elementos** 

Continuaremos a usar a imagem da sessão de "Benefícios". A sombra é resultado de um efeito de "luz" que lançaremos sobre o elemento. O nome da propriedade que utilizaremos para gerar esse efeito é `box-shadow`, que possui a propriedade do eixo X, y e uma cor. 

Queremos deslocar 10px no eixo X e Y, a cor que utilizaremos será preto.

```Css
.imagem-beneficios {
    width: 60%;
    opacity: 1;
    transition: 400ms;
    box-shadow: 10px 10px #000000;
}
```
>Ao recarregarmos a página, teremos uma sombra projetada, quadrada.

Podemos melhorar a qualidade estética dessa sombra ao adicionarmos uma terceira propriedade chamada blur, em que podemos aplicar um nível de desfoque específico, no caso, vamos inserir um valor de 5px. Quanto maior a quantidade de pixels que inserirmos, mais claro sera o efeito de desfoque.

```Css
.imagem-beneficios {
    width: 60%;
    opacity: 1;
    transition: 400ms;
    box-shadow: 10px 10px 5px #000000;
}
```
>Ao recarregarmos a página, veremos o efeito aplicado na sombra da imagem.

Temos ainda uma quarta propriedade que configura a intensidade da borda a partir do tamanho do elemento, isto é, **o tamanho da sombra projetada**. Neste caso, inseriremos 20px:

```Css
.imagem-beneficios {
    width: 60%;
    opacity: 1;
    transition: 400ms;
    box-shadow: 10px 10px 5px 20px #000000;

}
```
>No navegador, a sombra sugirá expandida.

Podemos adicionar várias sombras em um mesmo elemento, basta que o conteúdo esteja separado por uma vírgula. Essa nova sombra terá valores negativos e terá a cor amarela.

```Css
.imagem-beneficios {
    width: 60%;
    opacity: 1;
    transition: 400ms;
    box-shadow: 10px 10px 5px 20px #00000, -10px -10px yellow;

}
```
>Será projetada uma sombra por debaixo da anterior.

Podemos, ainda, inserir uma terceira sombra com a cor `rgba()` com a camada de opacidade e borda vermelha.

```Css
.imagem-beneficios {
    width: 60%;
    opacity: 1;
    transition: 400ms;
    box-shadow: 10px 10px 5px 20px #00000, -10px -10px yellow, -20px 20px rgba(255,0,0,0.5);

}
```
>Ao recarregarmos a página teremos três sombras.

Outra possibilidade no CSS 3 é criar sombras internas. Utilizaremos a própria sessão de benefícios para exempliciar esse efeito, que será utilizado em box-shadowe se chama inset. Seu posicionamento será a partir do centro do elemento e terá a cor vermelha.
```Css
.beneficios {
    padding: 3em 0;
    background: #888888;
    box-shadow: inset 0 0 #FF0000;
}
```
Ao carregarmos a página, não notaremos qualquer mudança. Isso se deve pelo fato de que a sombra possui o mesmo tamanho do elemento. Para que ela se torne perceptível, criaremos um espaçamento de 30px.

```Css
.beneficios {
    padding: 3em 0;
    background: #888888;
    box-shadow: inset 0 0 30px #FF0000;
}
```
 Apagaremos todas as sombras coloridas e manteremos apenas a sombra leve em `imagem-beneficios`.

```Css
.imagem-beneficios {
    width: 60%;
    opacity: 1;
    transition: 400ms;
    box-shadow: 10px 10px 10px 0 #000000;
}
```
Para fechar o tópico de sombras, por último aprenderemos a inserir sombras em textos. Em titulo-principal, utilizaremos a propriedade text-shadow, que recebem os valores que já conhecemos.

```Css
.titulo-principal {
    text-align: center;
    font-size: em;
    margin: 0 0 1em;
    clear: left;
    text-shadow: 2px 2px #FF0000; 
}
```
>Será criada uma sombra para o título.

**Meta Tag de Viewport**

Hoje em dia, a maior parte do fluxo de usuários na internet é proveniente de celulares, portanto um site não responsivo a tal necessidade é um problema.

Para testarmos a usabilidade do site, abriremos a ferramenta do desenvolvedor por meio do atalho "Ctrl + Shift + I" . No painel de ferramentas, teremos um ícone que representa tablets e celulares, a "Toggle device toolbar" , que também pode ser acessada pelo atalho "Ctrl + Shift + M".

No momento em que habilitamos essa opção, nosso site passa a se comportar como se estivesse sendo visualizado via celular: o conteúdo é compartimentando em 940px, o mínimo para esse tipo de plataforma. Atualmente, temos alguns problemas nesse tipo de visualização: a logo marcar está pequena,o menu está pouco legível assim como o conteúdo da lista de benefícios.

Primeriamente, precisamos compreender quantos pixels existem na tela para trabalhamos em uma melhor exibição. Atualmente, nossa tela se adapte ao tamanho disponibilizado pelo navegador, sendo o mínimo 940px. No caso de celulares o panorama é diferente: mesmo que a resolução do dispositivo seja de 2000px de largura, a quantidade de pixels existentes na tela sempre será diferente. Esses valores são chamados de DPI, isto é, a densidade de pixels por polegada.

Geralmente, os celulares possuem 320px de largura de tela,alguns maiores oscilam entre 350px e 480px. Portanto se o mínimo é 940px, teremos um valor discrepante. Uma informação crucial é saber quantos pixels possui a tela do usuário.

Trabalharemos com uma nova tag <meta>, mas dessa vez com propriedade e valor name="viewport" embutidas. Queremos, ainda, saber a largura do dispositivo, e para isso usaremos a propriedade content com o valor width=device-width.

```Html
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width">
    <title>Barbearia Alura</title>
    <link rel="stylesheet" href="style-home.css">
    <link href="https://fonts.googleapis.com/css?family=Montserrat&display=swap" rel="stylesheet">
</head>
```
Ao reabrirmos o navegador, veremos que o site se comporta de maneira diferente. A forma como os elementos etão distribuídos em relação ao fundo, o conteúdo é de 940px, mas a visualização mobile é de 375px, que corresponde a um IphoneX. Na pare superior da tela ainda podemos rotacionar a tela para horizontal e ver como a página se comporta.

Precisaremos, então, adaptar o CSS para que ele funcione nessa tela. Precisamos entregar para telas até 450px um estilo diferente, e faremos isso por meio de media queries. Perguntaremos ao navegador qual é o tamanho da tela em questão e, se for aquele que desejamos, entregaremos o estilo correto.

Para realizar isso, utilizaremos o @media, com o valor do tipo de tela screen e a pesquisa. Todas as telas que tenham até 450, terão esse estilo diferente, reescrito. Para exempliciar, colocaremos no background um estilo da cor vermelha.

```Css

@media screen and (max-width: 480px) {
    body {
        background: red;
    }
}
```
Ao regarregarmos a página veremos a modificação aplicada.Sabemos como o CSS pode responder a situações mobile, nas próximas aulas adaptaremos nosso conteúdo para entregar um site responsivo.

**Adaptar uma página para celular**

Primeiramente nos atentaremos para o cabeçalho, que possui 940px de altura. Se inserirmos uma altura automática, o posicionamento dos elementos que compõe a sessão se deforma, portanto essa não é uma boa saída para solucionar a questão. Em style.css mudaremos a altura da caixa para auto. Quando elaboramos layouts responsivos, precisamos trabalhar exclusivamente no elemento que será modificado.

Faremos o mesmo procedimento para principal, conteudo-beneficios, mapa-conteudo e video.

```Css
@media screen and (max-width: 480px) { 
    .caixa, .principal, .conteudo-beneficios, .mapa-conteudo, .video {
        width: auto;
    }
}
```
Precisaremos ainda fazer uma pequena alteração na classe video, e anterar o width para 100%, assim evitamos uma deformação no layout.

Feito isso, faremos as alterações necessárias no cabeçalho da página, e a primeira adaptação que faremos é centralizar o `<h1>` Em nosso CSS, escreveremos:

```Css
h1 {
    text-align: center;
}
```
Feito isso, queremos que o menu - que até o presente momento está em posição absoluta - volte a ser estático. Então em nosso CSS escreveremos:
```Css
nav {
    position:static;
}
```
Por fim, faremos alterações na lista de benefícios, de forma que a imagem e texto fiquem melhor posicionados.

```Css
.lista-beneficios, imagem-beneficios {
    width: 100%
}
```