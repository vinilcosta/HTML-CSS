# Módulo 3 do Curso Html & Css

Anotações do que foi visto no curso.


**Começando a paǵina de Contato** 

Para iniciar vamos ,copiar todo `header` e o `footer` da página produtos.html  e dentro da tag `title` vamos alterar para contato-Barbearia Alura e vamos adicionar a tag `main` logo depois vamos alterar o nome das páginas de Css do nosso projeto para organiza-lo melhor.

**Criando os campos básicos**
 
 Iniciamos colocando no nosso `main` a tag de formulário que é a `form` e dentro do formulário nós temos a entrada de dados do usuário e para isso aplicamos a tag `input` e o input tem sempre um tipo no caso queremos  obter o nome do usuário então vamos usar a tag `input` com o tipo `text` ou seja o usuário vai digitar texto em um campo.

 ```html
 <main>
     <form>
         <input type="text">
     </form>
 </main>
 ```
 E precisamos colocar um nome para aquele campo,se queremos que o usuário coloque o nome dele precisamos deixar claro para ele isso,e para isso vamos usar uma etiqueta que se chama `<label>`,o `label` e o `input` sempre andam juntos,e como eu ligo os dois ?,primeiro no `input` vamos inserir um `id` e no `label` adicionamos um `for` para um pertencer ao outro.

```html
 <main>
     <form>
         <label for="nomesobrenome"></label>
         <input type="text" id="nomesobrenome">
     </form>
 </main>
 ```
Quando temos um campo muito pequeno ou muitas informações para serem entradas é sempre **importante** ter esse par andando juntos.

E vamos criar mais um novo `input` com o tipo texto e um `label` junto dele ,esse input vai ser responsável pelo e-mail do usuário.

```html
 <main>
     <form>
         <label for="nomesobrenome"></label>
         <input type="text" id="nomesobrenome">

         <label for ="email">Email</label>
         <input type="text" id="email">
     </form>
 </main>
 ```
 E vamos colocar mais uma entrada de dados ou seja mais um `input`,para entrada de dados de telefone do usuário.

 ```html
 <main>
     <form>
         <label for="nomesobrenome"></label>
         <input type="text" id="nomesobrenome">

         <label for ="email">Email</label>
         <input type="text" id="email">

         <label for ="telefone">Telefone</label>
         <input type="text" id="telefone">
     </form>
 </main>
 ```
 Agora vamos precisar enviar esses dados,vamos criar um outro `input` sem `label`,do tipo `submit` ou seja envio, aonde mando os dados para servidor ou mando para email ou para uma próxima página, se quisermos que o botão submit tenha como palavra principal "enviar" ou "enviar formulário" precisamos aplicar o `value` e dentro do value colocamos a palavra que queremos. 
 
 ```html
 <main>
     <form>
         <label for="nomesobrenome">Nome e Sobrenome</label>
         <input type="text" id="nomesobrenome">

         <label for ="email">Email</label>
         <input type="text" id="email">

         <label for ="telefone">Telefone</label>
         <input type="text" id="telefone">

         <input type="submit" value="Enviar formulário">
     </form>
 </main>
 ```
 
 **Estilos para formulário**

 Nesse momento vamos editar nosso html,através do nosso Css ,uma das coisas que reparamos, inclusive olhando as páginas anteriores, é que queremos o conteúdo com 940 pixels de largura e que ele esteja sempre centralizado ,assim vamos na pagina style.css e alterar isso no main.

 ```Css
 main{
     width:940px;
     margin:0 auto;
 }
 ```
 Começando a página do contato, quero que a minha tag do formulário `form ` tenha uma margem superior de 40 pixels, para os lados 0, e inferior de 40 pixels `margin: 40px 0;`. Eu quero que tenha um espaço entre o fim do cabeçalho e o início do meu formulário, e entre do meu formulário e o início do rodapé.

 ```Css
 form{
  margin:40px 0;   
 }
 ```
 * Agora vamos alterar o display de todos os nossos `imputs` e `label` como eles estão `inline` ,vamos alteral-los para `block`,deixando assim um abaixo do outro 
 * Também vamos alterar o tamanho da fonte de cada label usamos o `font-size`.
 * E aumentar o espaço da `label` e o campo que vem logo abaixo dela usando a propriedade margin.
 * E no `input` a mesma coisa vamos aumentar o espaço pra baixo atavés da propriedade `margin` .
 * E agora vamos mexer dentro dos nossos `input`  através do padding colocando 10px para cima e para baixo e 25px para os lados o que vai alterar nosso `input submit`.
 * E ainda vamos mexer na largura do campo do nosso `input`,aplicando a propriedade `width: 50%` do tamanho da página.

 ```Css
 form{
  margin:40px 0;   
 }

 form label{
     display:block;
     font-size:20px;
     margin:0 0 10px;
 }

 form input{
     display:block;
     margin: 0 0 20px;
     padding: 10px 25px;
     width:50%;
 }
 ```
 **Formulários mais Complexos**

Iniciamos nossos formulários mais complexos com a tag `<textarea>` diferente da tag `<input>` essa tag nos da a possibilidade de colocar mais de uma linha de texto,o `<textarea>` diferente da tag `<input>` ,é uma tag de conteúdo,entao abrimos e fechamos ela.

```html
<textarea></textarea>
```

Quando eu salvo o `<textarea>` no meu html ,no navegador temos a possibilidade de alterar seu tamanho enquanto estamos na página,porém vamos configurar nosso `<textarea>` colocando quantas colunas e quantas linhas de texto essa caixa vai ter.

```html
<textarea cols="30" rows="10"></textarea>
```
Após salvar vemos que nossa caixa de texto esta mais quadrada ,porém precisamos deixar a caixa do `<textarea>` do tamanho dos `<input>` então vamos aumentar a quantidade de colunas para "70".

```html
<textarea cols="70" rows="10"></textarea>
```
O próximo passo é adicionar o `<label>` para identificarmos o que nosso `<textarea>` faz e vamos adicionar um `id` no elemento `<textarea>`.

```Html
<label for ="mensagem">Mensagem</label>
<textarea cols="70" rows="10" id="mensagem"></textarea>
```
Agora vamos para o **campo selecionar**,começamos inserindo o `<input>` do tipo `radio`(tem a função de colocar as bolinhas de opção) com o `value=email`,acima do input vamos fazer o mesmo processo que é colocar o label.

```Html
<label for="radio-email">Email</label>
<input type="radio" value="email" id="radio-email">
```
E agora vamos criar mais dois `input` do tipo `radio` para o Telefone do usuário e o outro para o Whatsapp.

```Html

<label for ="radio-telefone">Telefone</label>
<input type="radio" value="telefone" id="radio-telefone">

<label for="radio-whatsapp">Whatsapp</label>
<input type="radio" value="whatsapp" id="radio-whatsapp">
```
 Quando eu clico, ele me deixa marcar mais de uma opção. Quando nós criamos um `<input>` do tipo `radio`, ele precisa ter uma única identificação, um único termo para que eles todos permaneçam sempre um marcado. Todos eles precisam fazer parte de um grupo, para que a configuração de quando um clica o outro desclica funcione.

 Para isso precisamos inserir uma nova propriedade em cada um dos `<input>` o nome dela é `name` e o valor dessa propriedade também será o mesmo `name=contato`, essa configuração faz com que todos passem a ser do mesmo grupo e quando clicarmos em um desmarca o outro.

 ```Html
<label for="radio-email">Email</label>
<input type="radio" name="contato" value="email" id="radio-email">

<label for ="radio-telefone">Telefone</label>
<input type="radio"  name="contato" value="telefone" id="radio-telefone">

<label for="radio-whatsapp">Whatsapp</label>
<input type="radio" name="contato"value="whatsapp" id="radio-whatsapp">

<input type="submit" value="Enviar formulário">

```

Logo após vamos adicionar uma tag de paragrafo `<p>` para adicionar um titulo para nossos `<input>` e esse grupo de conteúdo faz parte do mesmo simbolo que é essa seleção, para isso vamos adicionar uma `<div>` para que eu saiba que todas essas linhas são referentes aquela única entrada de dados.


 ```Html
 <div>
     <p>Como prefere nosso contato?</p>
    <label for="radio-email">Email</label>
    <input type="radio" name="contato" value="email" id="radio-email">

    <label for ="radio-telefone">Telefone</label>
    <input type="radio"  name="contato" value="telefone" id="radio-telefone">

    <label for="radio-whatsapp">Whatsapp</label>
    <input type="radio" name="contato"value="whatsapp" id="radio-whatsapp">
</div>


<input type="submit" value="Enviar formulário">

```
E por último vamos criar uma checkbox,onde eu marco e desmarco algum item, e nesse caso, “Gostaria de receber nossas novidades por e-mail?” vamos criar essa label com esse conteúdo.]

>Um detalhe muito interessante: quando eu tenho um label e eu tenho um input e eles formam um par, o que nós fizemos até agora foi criar o identificador no input e colocar um for no label, para que eles se comuniquem.

Mas existe uma estratégia que pode ser feita para poupar esse trabalho,que é adicionar o `input` dentro do `label`,eu vou criar um `input` do tipo checkbox dentro desse `label` aqui.

```Html
<div>
    <label for="radio-email">Email</label>
    <input type="radio" name="contato" value="email" id="radio-email">

    <label for ="radio-telefone">Telefone</label>
    <input type="radio"  name="contato" value="telefone" id="radio-telefone">

    <label for="radio-whatsapp">Whatsapp</label>
    <input type="radio" name="contato"value="whatsapp" id="radio-whatsapp">
</div>

<label><input type="checkbox">Gostaria de receber nossas novidades por e-mail</label>

<input type="submit" value="Enviar formulário">
```

**Css para formulários Complexos**

A primeira coisa que iremos é fazer com que nosso `textarea` seja do mesmo tamanho do nosso `input`,alteramos o textarea para que ele seja um pouco maior e tenha mais conteúdo escrito porém não alteramos visualmente o tamanho do elemento.

* No Css ja haviamos criado uma configuração para o nosso formulário input e vamos replicar essa configuração para outro elemento,para fazer isso usamos a virgula e as configurações vão ser replicadas para qualquer outro seletor de Css .

```Css
form input,form textarea {
  display: block;
  margin: 0 0 20px;
  padding: 10px 25px;
  width: 50%;
}
```
* Como fizemos acima vamos aplicar as mesmas configurações de Css para as nossas tags `<p>` como aplicamos para nossos `label`.

```Css
form label,form p {
  display: block;
  font-size: 20px;
  margin: 0 0 10px;
}
```
* Se repararmos  no nosso  exemplo de Checkbox temos nosso input antes do `<label>` para alteramos isso  no nosso `radiobox` precisamos alterar a apresentação visual do nosso html,como fizemos no `checkbox` vamos colocar nosso `input` dentro do `label`.

```Html
<div>
            <p>Como prefere nosso contato?</p>
            <label for="radio-email"><input type="radio" name="contato" value="email" id="radio-email" />Email</label>
           

            <label for="radio-telefone"><input type="radio" name="contato" value="telefone" id="radio-telefone"/>Telefone</label>
            

            <label for="radio-whatsapp"><input type="radio" name="contato" value="whatsapp" id="radio-whatsapp"/>Whatsapp</label>
            
</div>
```
* Porém se observarmos nosso  `input` estão ocupando uma linha inteira pois no nosso Css a configuração do display  de todos `input` esta como block,precisamos alterar essa configuração e como fazemos para deixar essa configuração menos genérica e mais especifica? vamos usar as classes e aplicar em cada `imput` e `textarea` que queremos essa configuração.

```Css
.input-padrão {
  display: block;
  margin: 0 0 20px;
  padding: 10px 25px;
  width: 50%;
}
```

* E agora aplicamos no nosso html só nos `input` que desejamos que fiquem na configuração `block`.

```Html

<form>
          <label for="nomesobrenome">Nome e Sobrenome</label>
          <input type="text" id="nomesobrenome" class="input-padrao"/>

          <label for="email">Email</label>
          <input type="text" id="email"class="input-padrao" />

          <label for="telefone">Telefone</label>
          <input type="text" id="telefone"class="input-padrao" />

          <label for="mensagem">Mensagem</label>
          <textarea cols="70" rows="10" id="mensagem" class="input-padrao"></textarea>

```
* Para finalizar vamos editar nossa `checkbox` com a `margin` para cima e para baixo de 20px.

```Css
.checkbox{
    margin: 20px 0;
}
```
>É importante quando pensarmos no CSS, tentarmos colocar as configurações o mais específicas possível, porque quando colocamos elas muito genéricas usando a classe, sempre que vamos fazer algo mais complexo, aquilo nos atrapalha.

**Hierarquia no Css**

Sabemos que temos diversas formas de aplicar estilo no Css seja por **classe** **id** ou somente pela **tag**, Mas o que acontece, por exemplo, se usarmos dois seletores de tags? Se usarmos o “form p {”, e aqui “color: blue;”? Qual dos dois terá prioridade para aplicar a cor? A primeira cor aplicada vai ser azul e por cima vamos passar o vermelho? Ou primeiro vamos passar o vermelho e depois o azul? Salvando e recarregando a página, vemos que a cor aplicada é o azul. E por que isso acontece? Quando temos duas tags, nós temos o dobro da força do seletor. Todo seletor é configurado a partir de uma força. E como se aplica mais ou menos isso?

* A **tag** tem como se fosse uma força *1*, a **classe** uma força *10*, e o **identificador** uma força *100*. Toda vez que temos um **seletor** daquele tipo, “p”, isso quer dizer que a força desse seletor é 1. Quando temos o “form p” a força disso é *1+1*, a força disso é *2*. Então *2*, como é mais forte que o *1*, o estilo aplicado vai ser o segundo, do “form p”.

* O que acontece então se aqui colocarmos a classe “teste” aplicada naquele “p” com a cor, por exemplo, amarela? Salvamos e recarregamos isso aqui no navegador, a cor do nosso texto fica amarelo, porque a classe tem uma força *10*, ela é superior a esses dois marcadores que colocamos aqui. Então “.teste 10”.

* E o que acontece se criamos um marcador com a seguinte configuração: “p.teste {“? Ou seja, só os parágrafos que têm aquela classe vão ter essa cor. E aí eu crio a cor laranja. Nós somamos, a classe tem a força *10*, e a tag tem a força *1*, então com *11* ele vai ser mais forte que o teste especificamente. E recarregando nossa página, o texto fica em laranja.

* Por último, o mais forte deles é o **identificador**. Então se eu uso o identificador aqui e coloco que a cor dele é rosa, no meu navegador, a cor do meu texto vai ser rosa, porque o identificador tem a força *100*. Então sempre que estamos criando CSS, precisamos pensar em o quão específico é o nosso marcador e o quão forte ele vai ser para que não seja sobrescrito por qualquer outro, e que não cometamos nenhum erro no nosso código.

> Essa é uma forma de entendermos brevemente como funciona mais a especificidade do CSS e tomarmos melhores decisões na hora de criar o CSS do nosso projeto.

**Selecionando opções**

Para finalizar os campos complexos do nosso formulário,vamos inserir um campo de seleção de itens.

* Logo abaixo da `div` que possui nosso `radio-button` vamos criar outra div que irá comportar nosso campo de seleção.

* Na criação do campo de seleção vamos usar a tag `select` de seletor .

* E dentro do seletor vamos colocar as tags `option` ou opções que são um campo de conteúdo, vão ser tres option cada uma vai receber um conteúdo diferente uma Manhã outra Tarde outra Noite.

```Html

<div>
    <select>
        <option>Manhã</option>
        <option>Tarde</option>
        <option>Noite</option>
    </select>
</div>
* Acima do nosso campo seletor vamos inserir um tag `p` recebendo a frase "qual horario prefere ser atendido?"

```Html
    <div>
        <p>Qual horário prefere ser atendido?</p>
        <select>
            <option>Manhã</option>
            <option>Tarde</option>
            <option>Noite</option>
        </select>
    </div>
```    
> E é assim fazemos para ter essa opções em estilo dropdown .

**Inputs para celulares**

Quando falamos de formulário ,existem algumas coisas muito importantes que o HTML5 criou para facilitar a vida de quem está usando o celular,por exemplo.

Sempre estamos em contato com nosso celular de alguma forma por isso é muito importante que nossa página, nosso formulário e nossos campos estejam adaptados para isso.

Existe um site chamado `Mobile Input Types` ele nos mostra visualmente qual o resultado esperado quando estamos usando um tipo de *HTML5 input* em um celular.

* Quando temos um `input` do tipo `texto`, o esperado é que o teclado permaneça o mesmo, ele seja o teclado padrão do celular.

* Mas, em compensação, quando nós temos um e-mail, nós podemos botar o tipo do `input` o tipo `e-mail`, e o que isso faz de diferente? Isso faz com que o teclado do celular seja mudado, e que ao invés de termos uma barra de espaço muito grande, a barra de espaço é dividida e agora nós temos um arroba, um ponto. Em alguns teclados e sistemas operacionais, nós temos inclusive um “.com”. Isso facilita demais a vida do usuário na hora de cadastrar o seu e-mail.

* Nós também temos um tipo `telefone`, um `input` tipo `tel`. E o que ele faz? Troca o teclado para teclado numérico, o teclado que geralmente estamos digitando para entrar um número de telefone para ligar para alguém.

* Temos ainda o `input` do tipo `number`, onde ele muda para o teclado de número, ele joga opção do teclado para o teclado de número, e o usuário consegue entrar os dados muito facilmente. Onde é muito comum vermos isso, ou o ideal seria vermos isso? Quando temos que entrar, por exemplo, o nosso CEP ou o nosso CPF em algum formulário de compra de um site. O ideal é que se `input` seja do tipo `number`, para que possamos, no teclado numérico do celular, entrar com os dados muito mais rapidamente.

* O `input` do tipo `password` não é novo, mas é extremamente comum. Ele transforma todo o conteúdo que estamos digitando em um asterisco ou em uma bolinha para que alguém olhando nossa tela ou alguém espionando aquilo não consiga ver diretamente nossa senha.

* Temos ainda o `input` do tipo `data`, que abre o seletor de data do telefone e eu posso rolar para achar o dia, mês e ano. Temos ainda `input datetime`, que, além da data, abre o teclado, onde eu escolho o dia, as horas e segundos. Temos ainda o `input` do tipo `month`, que é o mês, e eu posso selecionar o mês e o ano.

* O `input` do tipo `busca`, que vira uma caixa de busca. E uma mudança bem sutil é que ao invés de ser “Go” ou “Done”, o campo de envio vira “Pesquisar”, “Buscar”.

E agora vamos mudar no nosso HTML o nosso `input` e-mail para o tipo `email`,e o nosso input de telefone para o tipo `tel`,facilitando assim a vida do usuário.

```Html 
<label for="email">Email</label>
        <input type="email" id="email" class="input-padrao" />

        <label for="telefone">Telefone</label>
        <input type="tel" id="telefone" class="input-padrao" />
```
**Dados importantes nos inputs**

Agora vamos melhorar ainda mais nosso formulário.

* Campos obrigatórios: No HTML5 sempre que temos um input e queremos que ele seja preenchido podemos colocar uma palavra reservada que se chama `required` que quer dizer obrigatório,voltando para nosso site nada é mudado mas se tentamos enviar o formulário ele volta ao campo que precisa ser preenchido ou seja antes de enviar o formulário aquele campo precisa ser preenchido.

```Html

 <label for="nomesobrenome">Nome e Sobrenome</label>
        <input type="text" id="nomesobrenome" class="input-padrao" required/>

        <label for="email">Email</label>
        <input type="email" id="email" class="input-padrao" required/>

        <label for="telefone">Telefone</label>
        <input type="tel" id="telefone" class="input-padrao" required />

        <label for="mensagem">Mensagem</label>
        <textarea
          cols="70"
          rows="10"
          id="mensagem"
          class="input-padrao"
          required
        ></textarea>
```
>Adicionando em cada campo de preenchimento do nosso site        
 
* Sugestão de preenchimento: Para auxilio do usuário podemos adicionar as sugestões de preenchimentos ,para isso precisamos usar uma propriedade chamada `placeholder` ou seja ela esta ocupando aquele espaço até que o usuario comece a digitar,vamos inserir essa propriedade no input de telefone também.

```Html

<label for="nomesobrenome">Nome e Sobrenome</label>
        <input type="text" id="nomesobrenome" class="input-padrao" required/>

        <label for="email">Email</label>
        <input type="email" id="email" class="input-padrao" required placeholder="seuemail@dominio.com"/>

        <label for="telefone">Telefone</label>
        <input type="tel" id="telefone" class="input-padrao" required placeholder="(xx)xxxxx-xxxx"/>

        <label for="mensagem">Mensagem</label>
        <textarea
          cols="70"
          rows="10"
          id="mensagem"
          class="input-padrao"
          required
        ></textarea>
```
* E agora no nosso radio-Button vamos deixar uma opção sempre assinalada,e a primeira opção vai ser a do whatsapp,para fazer isso vamos até nosso input do whatsapp e vamos colocar a palavra reservada chamada `checked` ou seja estamos sugerindo que esteja marcado.

```Html
 <label for="radio-whatsapp"
            ><input
              type="radio"
              name="contato"
              value="whatsapp"
              id="radio-whatsapp"
              checked
            />Whatsapp</label
```

* E para finalizar ,quando temos uma `checkbox` e queremos que ela esteja marcada, vamos até o input da `checkbox` e escrevemos novamente a palavra reservada `checked`.

```Html
 <label
          ><input type="checkbox" class="checkbox" checked/>Gostaria de receber nossas
          novidades por e-mail</label
        >
```

**Melhorando a Semântica do formulário**

Dentro do formulário, quando queremos agrupar os campos e quando queremos ter um título para isso, temos tags específicas, que deixam nosso formulário melhor escrito. A primeira é a divisão, quando temos um campo e um texto, ou vários campos referentes a alguma coisa, não usamos a tag `div`, usamos a tag `fieldset`. Ela é referente à configuração de um ou mais campos referentes a um assunto específico,quando podemos usar ela além do que já estamos usando ? quando por exemplo temos o preenchimento de dados do cartão de crédito todos os dados do cartão podem estar dentro de um `fieldset`.

```Html
<fieldset>
          <p>Como prefere nosso contato?</p>

          <label for="radio-email">
            <input
              type="radio"
              name="contato"
              value="email"
              id="radio-email"
            />Email</label
          >

          <label for="radio-telefone"
            ><input
              type="radio"
              name="contato"
              value="telefone"
              id="radio-telefone"
            />Telefone</label
          >

          <label for="radio-whatsapp"
            ><input
              type="radio"
              name="contato"
              value="whatsapp"
              id="radio-whatsapp"
              checked
            />Whatsapp</label
          >
</fieldset>
```

E dentro de um `fieldset` não temos paragráfos ,temos titúlo e um titúlo de um fieldset é chamado de `legend`.

```Html
<fieldset>
          <legend>Como prefere nosso contato?</legend>

          <label for="radio-email">
            <input
              type="radio"
              name="contato"
              value="email"
              id="radio-email"
            />Email</label
          >

          <label for="radio-telefone"
            ><input
              type="radio"
              name="contato"
              value="telefone"
              id="radio-telefone"
            />Telefone</label
          >

          <label for="radio-whatsapp"
            ><input
              type="radio"
              name="contato"
              value="whatsapp"
              id="radio-whatsapp"
              checked
            />Whatsapp</label
          >
</fieldset>
```
Salvando no nosso formulário todos elementos que eram `p`,perderam a formatação,então vamos ate o Css e configurar a tag `legend`.

```Css
form label,form legend {
  display: block;
  font-size: 20px;
  margin: 0 0 10px;
}
```

Sempre que temos imagem na nossa página precisamos ter muita atenção Imagina que um usuário com baixa visão está acessando nosso site. 

Ele não vai conseguir identificar que nessa imagem aqui tem um desenho ultra complexo da silhueta de um cabelo, de um óculos, está escrito Alura. Ele não vai conseguir ver isso aqui de forma completa. 
Ele vai conseguir usar o nosso site perfeitamente, mas ele não vai conseguir ter a identificação visual do que é aquilo.

E quando estamos falando disso, todas as nossas imagens, por exemplo, a nossa imagem do cabeçalho, ela só tem a fonte, onde aquela imagem está sendo buscada. Mas um dos campos muito importantes quando estamos falando de acessibilidade é o campo “alt” em imagens.

“Alt” é uma alternativa para quem não consegue ver aquela imagem ou se aquela imagem não está carregando corretamente, qual a alternativa daquilo? E usamos o áudio para descrever aquela imagem. Aqui vamos, por exemplo, escrever “Logo da Barbearia Alura.


```Html
 <header>
      <div class="caixa">
        <h1><img src="logo.png" alt="logo da barbearia alura" /></h1>
        <nav>
          <ul>
            <li><a href="index.html">Home</a></li>
            <li><a href="produtos.html">Produtos</a></li>
            <li><a href="contato.html">Contatos</a></li>
          </ul>
        </nav>
      </div>
    </header>

A mesma coisa nós vamos fazer na imagem de rodapé. Vamos adicionar um “alt” que vai ter o mesmo conteúdo, “Logo da Barbearia Alura”. É importante fazermos isso para que nosso site tenha a melhor acessibilidade possível, que ele seja o mais simples, o mais correto e melhor de ser navegado.

```Html
<footer>
      <img src="logo-branco.png" alt="Logo da barbearia alura" />
      <p class="copyright">&copy; Copyright Barbearia Alura - 2019</p>
      <p></p>
</footer>
```

**O que são transições**

Para iniciar e entender um pouco sobre transições vamos criar uma classe no `input` com tipo `submit`,para referencia-lo no Css e fazermos a edição.

```Html
 <input type="submit" value="Enviar formulário" class="enviar" />
```
Logo após vamos editar a largura do botão e queremos que ele fique com o tamanho de 40% da pagina usando o `width`,logo após isso vamos editar o espaçamento interno do botão com o `padding` seu valor sendo `15px 0;` queremos também que esse botão tenha a cor de fundo laranja usamos então a propriedade `background` com o valor `orange`,e para dar um contraste a cor do texto vai ser branca com a propriedade `color`,vamos alterar o tipo da fonte para negrito usando a propriedade `font-weight-bold` e vamos aumentar a fonte com a propriedade `font-size`queremos também que ele não tenha a borda padrao usando a propriedade `border:none` e por último vamos arredondar os cantos com a propriedade `border-radius`.

```Css 
.enviar{
    width:40%;
    padding:15 px 0;
    background:orange;
    color:white;
    font-weight:bold;
    font-size:18px;
    border:none;
    border-radius:5px;
}
```
Nosso botão já está exelente e agora quando eu passo o mouse por cima eu quero que a cor de fundo mude um pouco e que a cor seja um laranja escuro vamos usar a propriedade `hover` ou seja quando o mouse está por cima .

```Css 

.enviar:hover{
   background:darkorange;
}
```
Agora eu quero a transição demore um pouco por exemplo 1 segundo de uma cor para a outra,isso é possivel através da propriedade `transition:1s` e que  vai ser uma transição do meu `background` e para finalizar eu quero que sempre que meu cursor estiver por cima  do meu `input` o meu vizualizador seja a mãozinha por isso usamos a propriedade `cursor:pointer`.

```Css 
.enviar{
    width:40%;
    padding:15 px 0;
    background:orange;
    color:white;
    font-weight:bold;
    font-size:18px;
    border:none;
    border-radius:5px;
    transition:1s background;
    cursor:pointer;
}
```
**Entendendo Transformações**

Uma das coisas mais legais do CSS3 é que ele trouxe facilidade para o desenvolvedor, que antes precisava fazer cambalhotas para conseguir resolver alguns problemas. Um deles é quando eu estou com o elemento e passo o mouse por cima dele, eu quero aumentar esse elemento em 20%.

Vamos analisar só o nosso botão e o que significa isso de aumentar 20% do elemento. Eu preciso aumentar a largura em 20%, eu preciso proporcionalmente aumentar a fonte em 20%, ainda preciso aumentar o espaçamento interno em 20%, preciso aumentar o raio da minha borda em 20. Ou seja, são cálculos demais para se fazer na mão. O CSS3 trouxe a solução para isso: existe uma nova propriedade chamada “transform” que tem algumas características e que resolve isso para nós.

Então, no nosso CSS, quando colocarmos o mouse por cima do botão de enviar, eu quero que ele aumente em 20%. Para isso, eu vou usar a propriedade `transform` e o valor dentro dela é o `scale`, ou seja, de escala e medida, e eu quero que ele aumente 20%. Aqui fazemos um cálculo proporcional, eu quero multiplicar ele por 1.2, `transform: scale(1.2);`. Quando salvo isso e carrego no navegador, agora quando passa o mouse por cima do elemento,` ele aumenta em 20% proporcionalmente todas as coisas`, sem eu precisar fazer conta nenhuma.

 ```Css 

.enviar:hover{
   background:darkorange;
   transform:scale(1.2);
}
```

Mas reparem que essa transição está muito bruta. Como que nós fazemos para que essa transição que estamos usando no background seja feita para todos os itens? Aqui adicionamos que a transição do background vai acontecer em um segundo. Eu posso colocar que a transição de todos os elementos vai demorar um segundo para acontecer. E quando eu salvo isso e carrego no navegador, ele demora um segundo para aumentar proporcionalmente no meu formulário, e um segundo para voltar proporcionalmente ao tamanho adequado.

 ```Css 
.enviar{
    width:40%;
    padding:15 px 0;
    background:orange;
    color:white;
    font-weight:bold;
    font-size:18px;
    border:none;
    border-radius:5px;
    transition:1s all;
    cursor:pointer;
}
```

E o que é mais possível fazer com o transform? Existe uma outra propriedade chamada `rotate` que inclina o meu item quantos graus eu quiser. E aqui vamos colocar 70 graus. Nós usamos a medida de graus em inglês que são “degrees”, `transform: rotate(70deg);`. Quando carrego isso aqui e passo o mouse por cima do elemento, ele roda o meu item em 70 graus; e quando tira o mouse, ele volta para original.

  ```Css 

.enviar:hover{
   background:darkorange;
   transform:scale(1.2);
   transform: rotate(70deg);
}
```

Reparem que ele parou proporcionalmente, e por que isso aconteceu? No CSS a leitura é sempre feita de cima para baixo. O último item sobrescreve o anterior, então aqui, como temos duas propriedades iguais, a última que vai ser lida. Essa aqui vai ser lida e vai ser ignorada. Como que eu faço então para somar essas duas propriedades no transform? Eu simplesmente adiciono uma depois da outra, com um espaço. Se eu salvar isso aqui e recarregar no meu navegador, ele vai aumentar e rodar.

 ```Css 

.enviar:hover{
   background:darkorange;
   transform:scale(1.2) rotate(70deg);
}
```

E aqui eu posso colocar qualquer coisa. Eu posso colocar para rodar mil graus, eu posso colocar para aumentar por três vezes, que ele vai fazer. Não é isso que queremos para o nosso usuário. Queremos para o nosso usuário só que esse item aumente em 20%.

**Tabela básica**
 Agora vamos iniciar a criação de uma tabela, a tabela é um item extremamente trabalhoso de se fazer, embora seja muito simples. Ela exige que criemos muitas tags, mas muito fáceis de entender.

 * Abaixo do nosso formulário vamos iniciar nossa tabela, a tag da tabela é a `<table>`, mas o que é uma tabela ? é uma sequencia de linhas e de colunas e é isso que vamos fazer com o css.

 * Uma linha é desgnada como uma `<tr>`(table-row) e na nossa tabela teremos quatro linhas e em cada uma das linhas teremos duas celulas e as celulas se chamam `<td>`,a primeira linha geralmente é um cabeçalho e colocamos o que aquela coluna terá como conteúdo exemplo "dia" e "horário".

```Html
 <table>
     <tr>
         <td>Dia</td>
         <td>Horário</td>
     </tr>
     <tr>
        <td>Segunda</td>
        <td>8h ~ 20h</td>
     </tr>
     <tr>
         <td>Quarta</td>
         <td>8h ~ 20h</td>
     </tr>
     <tr>
         <td>Sexta</td>
         <td>8h ~ 20h</td>
     </tr>
 </table>
 ```
 E assim iniciamos a criação da nossa tabela.

 **Tags Semânticas para tabelas**

 Para estruturar nossa tabela de uma forma semântica separamos ela em três o cabeçalho o conteúdo e o rodapé como na nossa página principal.

 * O cabeçalho chamamos de <thead> dentro dele vamos colocar a nossa primera linha ue é a que dita o que nossa tabela vai ter como conteúdo e dentro do cabeçalho para dizer que é uma tag do caeçalho substituimos a tag `td` pela `th`,também temos outra repartição que é a <tbody> que irá comportar o conteúdo da tabela.

 ```Html
 <table>
     <thead>
         <tr>
             <th>Dias</th>
             <th>horarios</th>
         </tr>
     </thead>        
<tbody>
    <tr>
        <td>Segunda</td>
        <td>8h ~ 20h</td>
     </tr>
     <tr>
         <td>Quarta</td>
         <td>8h ~ 20h</td>
     </tr>
     <tr>
         <td>Sexta</td>
         <td>8h ~ 20h</td>
     </tr>
</tbody>
 </table>
```
Ao salvar a unica coisa que muda é que nossa tabela centraliza porém ela já está mais semântica.

**Estilos na tabela**

* Vamos primeiro ao nosso Css e começar a editar nossa tabela,iniciamos  criando a referencia para tag da tabela.

* Colocamos dentro do seletor table a propriedade margin para criarmos um espaçamento externo de 20px para cima e 40px para baixo.

* Agora vamos colocar uma cor de fundo o nosso `thead` ,criamos um seletor  para ele e colocamos a propriedade `background:#555555;`para complementar vamos deixar a cor da fonte branca `color:white;` e o peso da fonte vai ser negrito `font-weight:bold;`.

* Agora vamos mecher nos itens da minha tabela ou seja no `td`,vamos aplicar neles uma borda de 1px sendo ela solida da cor preta `border:1px solid #000000;` e iremos aplicar essa configuração nos itens do cabeçalho também ou seja no `th`.

* E para finalizar vamos aplicar um espaçamento interno usamos então a propriedade `padding` vamos colocar um espaçamento lateral de 15 pixels e, para cima e para baixo, de 8 pixels, “padding: 8px 15px;”.

```Css

table{
    margin: 20px 0 40px;
}
thead{
    background:#555555;
    color:white;
    font-weight:bold;
}
td,th{
    border:1px solid #000000;
    padding:8px 15px;
}
```