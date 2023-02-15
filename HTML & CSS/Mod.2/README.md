# Módulo 2 do Curso Html & Css

Anotações do que foi visto no curso.


**Cabeçalho com imagem e lista**:

* Dentro da nossa nova página ,o cabeçalho tem como informação principal uma logo e uma lista,dentro do    nosso `body`vamos utilizar a tag `header`para criação do espaço ,então começamos fazendo uso do `<h1>`para marcar nossa imagem,ou seja estamos dando bastante importância para esse conteúdo,assim vamos colocar  a tag `img` dentro da tag `h1`.

```html
<header>
    <h1><img src="logo.png"></h1>
</header>
```

* E agora iremos criar uma lista não ordenada,dentro do `header`.

```html
<header>
    <h1><img src="logo.png"></h1>

    <ul>
        <li>Home</li>
        <li>Produtos</li>
        <li>Contatos</li>
    </ul>
</header>
```


**Utilizando a tag a**  

Em cada item da nossa lista no cabeçalho,vamos adicionar links ,para que possamos navegar entre páginas,usamos para isso a tag `anchor`ou `<a>`que é uma tag de conteúdo,para que a tag `<a>` nos leve para outra pagina precisamos indicar um link como referencial de endereço através do `href`.

```html
<header>
    <h1><img src="logo.png"></h1>

    <ul>
        <li><a href="../Mod.1/index.html">Home</a></li>
        <li><a href="produtos.html">Produtos</a></li>
        <li><a href="">Contatos</a></li>
    </ul>
</header>
```
> Assim com a tag `a` podemos transitar entre as páginas que queremos.

**Aplicando Css no cabeçalho**

*  Iniciamos alterando a cor de fundo do nosso cabeçalho para cinza através da tag background.

```Css 
header {
    background: #bbbbbb
}
```
*  Agora vamos trabalhar na nossa lista,alterando a forma que ela é exibida, no momento ela está no formato `block`,vamos alterar para o in-line,e para isso nós passamos a usar a tag `<nav>`,sabemos que todos os sites possuem um menu de navegação todo site possui uma estrutura de links para serem navegadas entre o site por isso foi criada a tag `<nav>` para simplificar tudo.E toda essa parte do código relacionada a navegação do menu vai ser envolvida pela tag `<nav>`.

```html
<nav>
    <ul>
         <li><a href="index.html">Home</a></li>
        <li><a href="produtos.html">Produtos</a></li>
        <li><a href="contato.html">Contatos</a></li>
    </ul>
</nav>        
```
*  E agora podemos editar a forma que nossa lista é exibida através do Css.

```Css
nav li {
    display:inline;
}
```
*  Também queremos que os textos da nossa lista de navegação fiquem em maiúsculo para isso precisamos ir até o Css e editar a tag `nav a`usando a propriedde `text-transform:`:

```Css
nav a{
    text-transform: uppercase;
}
```
*  Vamos alterar a cor do texto para preto.

```Css
nav a{
    text-transform: uppercase;
    color: #000000;
}
```
*  Também vamos editar a fonte para negrito, com o Css através da propriedade `font-weight` e o valor `bold` e vamos alterar o tamanho da fonte usando a propriedade `font-size`,também precisamos tirar o sublinhado do nosso texto para isso usamos a propriedade `text-decoration` com o valor `none`:

```Css
nav a {
     text-transform: uppercase;
     color: #000000;
     font-weight: bold;
     font-size: 22px;
     text-decoration:none;
}
```
*  E por último vamos aumentar o espaçamento entre os itens,mas para isso vamos editar o item e não o link que está dentro do item:

```Css

nav li{
    display:inline;
    margin:0 0 0 15px;
}
```
**Limpando o Css**

O navegador pré configura o Css colocando vários estilos o que não é nada bom ,assim foi criado pela comunidade o reset.css sendo um arquivo Css que limpa tudo o que o navegador cria,para usar um arquivo externo Css no nosso html precisamos fazer um link , é importante se atentar para ordem que colocamos o link na nossa head, pois o reset.css ta limpando tudo o que o navegador fez ,possibilitando que todas nossas configurações feitas no arquivo produtos.css funcionem.


```html
<head>
    <meta charset="UTF-8" />
    <title>Produtos - Barbearia Alura</title>
    <link rel ="stylesheet" href="reset.css">
    <link rel="stylesheet" href="produtos.css" />
  </head>
```

**Aprendendo sobre Posicionamento no Css**

* Posição estatica:Posição inicial que o elemento está (posição padrão).
```Css
position:static;
```
* Posição Relativa:Uma nova Posição que é relativa a posição inicial.
```Css
position:relative;
```
* Posição absoluta:Posicionamento absoluto em relação a página ou ao cabeçalho.

```Css
position:absolute;
```

**Posicionando o cabeçalho**

E agora vamos começar a ajustar o posicionamento do nosso menu no cabeçalho.

```Css
nav{
    position:absolute;
    top:110;
    right:0;

}
```

Porém se observarmos bem nosso logo esta colado no canto esquerdo e o menu no direito,para mudarmos isso precisamos que dentro do nosso cabeçalho tenha alguma coisa que limite todo esse conteúdo,para isso vamos usar uma `div` dentro do nosso cabeçalho que vai envolver o nosso `h1` e o nosso `nav`.

```html
<header>
   <div> 
     <h1><img src="logo.png" /></h1>
          <nav>
            <ul>
                <li><a href="index.html">Home</a></li>
                <li><a href="produtos.html">Produtos</a></li>
                <li><a href="">Contatos</a></li>
            </ul>
        </nav>
    </div>    
</header>
```
E vamos nomear essa `div` colocando uma classe nela que vamos chamar de caixa,é essa caixa que irá ficar no meio centralizando todo conteúdo.

```html
<header>
   <div class ="caixa"> 
     <h1><img src="logo.png" /></h1>
          <nav>
            <ul>
                <li><a href="index.html">Home</a></li>
                <li><a href="produtos.html">Produtos</a></li>
                <li><a href="">Contatos</a></li>
            </ul>
        </nav>
    </div>    
</header>
```

E vamos dar um tamanho fixo para essa `div`,então vamos ao css referenciar a classe caixa ,vamos dar uma largura fixa ,e não acontece nada pois o menu não  esta dentro da caixa ,temos que entender que quando algo está com o posicionamento absoluto ele fica absoluto em relação a página ou seja o novo ponto inicial dele é qualquer ponto que selecionamos no navegador.

Quando queremos que ele tenha posicionamento absoluto porém dentro de uma caixa precisamos que essa caixa levante que ela tambem tenha um posicionamento só que um posicionamento relativo.

```Css
.caixa{
    position:relative;
    width:940px;
}
```
Agora nosso menu está dentro da caixa!

faltando somente centralizar a caixa,sabendo que a margem da esquerda precisa ser a mesma que a da direita,para centralizar de uma forma mais prática temos uma propriedade que calcula as duas margens sozinha que é a `auto`.

```Css
.caixa{
position:relative;
width:940px;
margin:0 auto;
}
```

Pra cima e para baixo os valores da margem serão zero e da direita e esquerda cálculo automatico ajustando a caixa do nosso menu,finalizando precisamos ajustar o tamanho do nosso cabeçalho aumentando um pouco o espaçamento interno para cima e para baixo.

```Css
header{
    background:#bbbbbb
    padding:20px 0; 
}
```
Usamos o padding porque queremos que tudo dentro do nosso cabeçalho esteja nesses limites não queremos que nada no nosso cabeçalho chegue na margem queremos que entre a margem e o conteudo tenha os 20 px em cima e embaixo,finalizando o cabeçalho.

**Aprendendo a usar o main**

No nosso código já fizemos a parte do cabeçalho,que é o `header`,agora temos uma tag especifica que também é semântica para o conteúdo principal que se chama `main` que na sua tradução significa principal ou seja o conteúdo mais importante.

 > E dentro do main vamos colocar o conteúdo que vamos apresentar ,cabelo,barba,cabelo+barba.


  **Construindo o conteúdo principal da nossa página produtos**

  Para iniciar a construção da parte mais importante da nossa página,vamos fazer uma lista não ordenada.

  >Cada item da nossa lista vai ser envolvido pela tag `h2` pois nosso header já possui uma tag h1,e precisamos dar ênfase aos nossos titulos.

  ```Html
  <main>
      <ul>
          <li><h2>Cabelos</h2></li>
          <li><h2></h2></li>
          <li><h2></h2></li>  
       </ul>
 <main>
 
 ```

  >E em cada um dos itens vamos adicionar além da tag de titulo `h2` ,uma imagem (tag `img`),e dois textos com a tag `<p>` e vamos adicionar as imagens a cada item.

 ```Html
 <main>
      <ul>
          <li>
              <h2>Cabelos</h2>
              <img src="cabelo.jpg">
              <p>
              <p>    
          </li>
          <li>
              <h2>Barba</h2>
              <img src="barba.jpg">
              <p></p>
              <p></p>    
          </li>
          <li>
              <h2>Cabelo+Barba</h2>
              <img src="cabelo+barba.jpg">
              <p></p>
              <p></p>
          </li>  
       </ul>
 <main>
 
 ```
> E logo após vamos adicionar a descrição de cada item da nossa página e os preços.

```Html
 <main>
      <ul>
          <li>
              <h2>Cabelos</h2>
              <img src="cabelo.jpg">
              <p>Na tesoura ou máquina, como o cliente preferir</p>
              <p>R$ 25,00</p>    
          </li>
          <li>
              <h2>Barba</h2>
              <img src="barba.jpg">
              <p>Corte e desenho profissional de barba</p>
              <p>R$18,00</p>    
          </li>
          <li>
              <h2>Cabelo+Barba</h2>
              <img src="cabelo+barba.jpg">
              <p>Pacote completo de cabelo e barba </p>
              <p>R$35,00</p>
          </li>  
       </ul>
 <main>
 
 ```

 **Reforçando o inline-block**

A primeira coisa que precisamos fazer para configurar a parte visual no nosso html é fazer a conexão dele com o Css porém queremos fazer a edição de alguns itens  juntos ,vamos utilizar as classes,para editar cada item da lista de forma igual.

```html
<ul class="produtos">
          <li>
              <h2>Cabelos</h2>
              <img src="cabelo.jpg">
              <p>Na tesoura ou máquina, como o cliente preferir</p>
              <p>R$ 25,00</p>    
          </li>
          <li>
              <h2>Barba</h2>
              <img src="barba.jpg">
              <p>Corte e desenho profissional de barba</p>
              <p>R$18,00</p>    
          </li>
          <li>
              <h2>Cabelo+Barba</h2>
              <img src="cabelo+barba.jpg">
              <p>Pacote completo de cabelo e barba </p>
              <p>R$35,00</p>
          </li>  
       </ul>
```
* No Css vamos referenciar a classe e editar o display de cada item através das `<li>` .

```Css

.produtos li {
    display:inline-block;
}
```

* Para centralizar nosso conteúdo vamos usar a mesma configuração que usamos na div(.caixa) acima,referenciando a classe e somente os itens que estão na `<ul>`.

```Css
.produtos{
    width:940px;
    margin:0 auto;
}
```

* Iremos também centralizar nosso texto,colocando a propriedade text-align,em cada item através das `<li>`.

```Css
.produtos li {
    display:inline-block;
    text-align:center;
}
```
* E agora precisamos que haja uma certa distribuição entre os itens,pois estão colados,e queremos deixar o tamanho de todos iguais ,aproximadamnte um terço do conteudo,porém ele não entende esse número pois entende em percentual temos 100% da nossa página cada um dos itens vão ocupar 30% da largura.

```Css
.produtos li {
    display:inline-block;
    text-align:center;
    width:30%;
}
```
* Um dos problemas do inline-block e que ele alinha os itens pela linha de baixo para concertarmos isso ,precisamos usar a propriedade `vertical-align:` e o valor `top`.

```Css
.produtos li {
    display:inline-block;
    text-align:center;
    width:30%;
    vertical-align:top;
}
```
* Porém nossos itens vão ficar colados no nosso cabeçalho,precisando aumentar o espaçamento interno.

```Css
.produtos{
    width:940px;
    margin:0 auto;
    padding:50px 0;
}
```
* E agora precisamos editar os titulos dos nossos produtos para isso

```Css
.produtos h2{
    font-size:30 px;
    font-weight:bold;
}
```
* E agora vamos editar a parte do nosso preço,que é o paragrafo porém temos duas tags `<p>` iguais ,para especificar cada uma vamos aplicar as classes,que vais se chamar "produto-preco" .

```Html
 <h2>Cabelos</h2>
              <img src="cabelo.jpg">
              <p>Na tesoura ou máquina, como o cliente preferir</p>
              <p class="produto-preco">R$ 25,00</p>
```
* E vamos referenciar a classe no css e editar.

```Css
.produto-preco{
    font-size:22px;
    font-weight: bold;
}
```
* Agora vamos especificar a nossa outra tag `<p>` com as classes,que no caso o seu nome é `produto-descricao`.

```Css

.produto-descricao{
    font-size:18px;
}


.produto-preco{
    font-size:22px;
    font-weight: bold;
}
```

**Ajustando o tamanho dos elementos** 

Vamos iniciar observando que nossos itens ainda estão muito colados,queremos dar espaço entre um e outro,para isso vamos usar a propriedade `margin` (que é o espaçamento externo ).

```Css
.produtos li {
    display: inline-block;
    text-align:center;
    width:30%;
    vertical-align:top;
    margin: 0 1.5%;
}
```
Agora vamos alterar o espaçamento interno dos nossos elementos ,pois o texto está colado na margem,colocando a propriedade `padding` sendo seu valor 30px para ima e para baixo e 20px para as laterais.

```Css
.produtos li {
    display: inline-block;
    text-align:center;
    width:30%;
    vertical-align:top;
    margin: 0 1.5%;
    padding:30px 20px;
}
```
Ao salvar o navegador aplicou os 30% de largura mais os 20px então temos que alterar a forma como ele pensa para que o espaçamento lateral esteja dentro do percentual e para isso vamos usar a propriedade `box-sizing` com isso os nossos 30% são definitivos,são sempre a largura e os 20px de espaçamento interno estão dentro desses 30%.

```Css
.produtos li {
    display: inline-block;
    text-align:center;
    width:30%;
    vertical-align:top;
    margin: 0 1.5%;
    padding:30px 20px;
    box-sizing:border-box;
}
```
E agora vamos editar a vizualização dos nossos preços pois estão muito colados na descrição ,então vamos adicionar a propriedade `margin` para aumentar o espaçamento externo,para cima de 10px para os lados 0 e para baixo também 0.

```Css
 .produto-preco{
    font-size:22px;
    font-weight: bold;
    margin:10px 0 0;
 }
 ```

 **Aplicando Bordas**

 Agora vamos definir as bordas dos nossos elementos,e na classe ".produtos li" vamos  usar as propriedades,border-color(cor da borda),border-width(largura da borda),border-style(tipo de borda).

 ```Css
.produtos li {
    display: inline-block;
    text-align:center;
    width:30%;
    vertical-align:top;
    margin: 0 1.5%;
    padding:30px 20px;
    box-sizing:border-box;
    border:2px solid #000000;
}
```
**Bordas Arredondadas**

Para arredondar as bordas dos elementos é simples vamos utilizar a propriedade do Css chamada `border-radius:`.

```Css
.produtos li {
    display: inline-block;
    text-align:center;
    width:30%;
    vertical-align:top;
    margin: 0 1.5%;
    padding:30px 20px;
    box-sizing:border-box;
    border:2px solid #000000;
    border-radius:10px;
}
```
**Pseudo-classes de estado**

Nesse tópico vamos aprender a alterar o comportamento dos itens ao passarmos nosso cursor por cima de cada um deles,e vamos começar usando a propriedade `hover` e a propriedade `text-decoration`, que se escreve assim:

```Css
nav a:hover {
    color:#c78c19;
    text-decoration:underline;
}
```
 **Aplicando hover e Active**

 Vamos aplicar o hover em outro elemento que é o nosso conteúdo principal e que está dentro do `.produtos li` e também o `active` que tem como função alterar a cor do elemento quando clico nele.

 ```Css

 .produtos li:hover{
     color:#c78c19;
 }

.produtos li:active{
    color:#088c19;
}
```
E agora queremos que o `h2` quando passarmos o cursor em cima do `li` dos`.produtos` tenha a letra de mais ou menos 34px,como no exemplo a seguir :

```Css
.produtos li:hover h2{
    font-size:34px;
}
```
**Rodapé**

Para finalizar nossa página vamos iniciar o rodapé,com a tag `footer` no final do código depois do `header` e do `body`,no footer vamos aplicar uma `img` e uma tag `p`:

```html
<footer>
    <img src="logo-branco.png">
    <p>Copyright Barbearia Alura - 2019<p>
</footer> 
```
Logo após vamos usar nosso Css para iniciar a edição do nosso rodapé ,vamos aplicar a propriedade `text-align` e a `background` porém no valor da background vamos aplicar uma imagem de fundo,mesmo ela sendo uma imagem pequena o Css ele aplica ela em todo espaço ate preenche-lo e vamos aplicar o `padding` para aumentar o espaço interno.

```Css
footer{
    text-align:center;
    background:url("bg.jpg");
    padding:40px 0;
}
```

**Adicionando caracteres especiais**

Para iniciar vamos ate nossa tag `<p>` e aplicar uma classe nela chamada `copyright`,para podermos fazer a edição no css:

```Css
.copyright{
    color:#FFFFFF;
    font-size: 13px;
    margin:20px 0 0;
}
```
Por ultimo vamos usar um caracter parecido com um @ mas tem um c no meio,para usa-lo precisamos uma usar linguagem chamada unicode,no site `unicode table`,tem todas as especificações desse simbolo e vamos aplica-lo no nosso Html:

```Html
<footer>
    <img src="logo-branco.png">
    <p class="copyright"> &copy; Copyright Barbearia Alura - 2019<p>
</footer> 
```