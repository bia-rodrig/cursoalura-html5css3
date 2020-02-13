# HTML5 e CSS3

## Primeiro texto

HTML - Hyper Text Markup Language

* HTML - Titulos:
```html
<h1></h1>
<h2></h2>
...
<h6></h6>
```
* HTML - Paragrafo
```<p></p>```

* HTML - Texto de testaque (negrito)
``` <strong></strong>```

* HTML - Itálico
```<em></em>```

## Estrutura básica

**<!DOCTYPE html>**
a exclamação faz com que a TAG seja reonhecida como DOCTYPE. E HTML informa que está usando a ultima versão do html.
Se fosse usar uma versão antiga, teria que informar a versão (html3, html4, etc).

```html
<html lang="pt-br">
</html>
```
html: tag de conteúdo
lang: linguagem
pt-br: português (en: ingles)


## Passando dados para o navegador

```<meta charset="UTF-8">```
meta: passa informações para o navegador
charset: conjunto de caracteres

```<title>Titulo do navegador</title>```

## Separando conteúdo

* HTML - cabeçalho (navegador)
```<head></head>: informações que passa ao navegador ```

* HTML - "corpo" do site 
```<body></body>: o que o usuário visualiza```

## Trabalhando com css

CSS 
Folha de estilo em cascata. É a estilização dos elementos do site.

-   inline: afeta somente o elemento que tiver o style
    
-   head: afeta a pagina inteira
    
-   externo: um arquivo só para o css com o link no html, que poderá ser usado em várias páginas diferentes(forma mais comum)


* CSS - Referencia ao css:
```<link rel="stylesheet" href="style.css">```

* CSS - Selecionando elementos
	* tag{}
	* #id{}
	* .class{}

* CSS - fundo cinza:
```css
body{
	background: #CCCCCC;
}
```
O CSS deve acompanhar a estrutura do HTML.
No HTML, body vem antes do p, então no CSS, a referencia a body, deve vir antes de p.

## Estilizando

* HTML - Adicionar imagem:
```<img src="arquivo_principal" alt="Erro ao carregar imagem">```

* Cores
hexadecimal = 0123456789ABCDEF

RGD = Red Green Blue

# _ _ _ _ _ _

R | G | B

0 = ausência  F = Máximo

#000000 - Preto  #FFFFFF - Branco

## Dimensões
* CSS - Altura (distorce a imagem)
	- height: 100px ou 30%;

* CSS - Largura
	- width: 100% ou 20px;

#### Padding
- Espaçamento interno
- Pode ser todos os lados, só pra cima, só pra baixo ou só para os lados.
	- Se colocar um padding para todos os lados, aumenta o tamanho do elemento.
```css
padding: 0 0 0 0; /*top right bottom left*/
padding: 10px; /*10 nos 4 cantos*/

```

### Margin 
- Espaçamanto externo
- Entre a borda do elemento e a parte externa (outro elemento ou margem da pagina)
- Se colocar margin em todos os cantos, tambem altera o tamanho do elemento como um todo
Borda - finalização do elemento
```css
margin 100px auto; /*100 top e bottom/ automatico right e left*/
```

* CSS - Imagem ocupando toda a largura da página:
```css
width: 100%
```

## Listas e divisões

* HTML - Listas não-ordenadas
```html
<ul>
	<li>item da lista</li>
</ul>
```

* HTML - Listas Ordenadas
```html
<ol>
	<li>item da lista</li>
</ol>
```

## Classes no CSS
Utiliza o mesmo estilo em diversos elementos. É só marca-los com a mesma classe
```css
.nome_classe{
	estilização aqui
}
```

## Divisões
Blocos de conteúdos, separados com a tag ```<div></div>```.
As divisões não afetam os conteúdos visualmente. 

*CSS - alinhamento do texto
```text-align: center;```



## RESET navegador
reset.css - arquivo que reseta as estilizações padrões dos navegadores.
A declaração desse css, deve vir primeiro que o css utilizado na pagina. 

## Display

**block** - Ocupa toda a linha da página. Se diminuir o tamanho de um elemento block, ainda assim, ele vai ocupar a página toda.
**inline** - Aceita outros elementos na mesma linha. Mas não deixa alterar o espaçamento interno e externo.
**inline-block** -  bloqueia a largura exata do elemento, mas deixa o usuario mexer nos espaçamentos.

## Alinhamento
Por padrão, os elementos são alinhados pela parte inferior. Para mudar isso, use o ```vertical-align: top```

```css
ul{
  display: inline-block;
  vertical-align: top;
  width: 20%; /*define o tamanho que a lista vai ter na pagina*/
  margin-right: 15%; /* espaçamento entre a lista e a imagem*/
}
```

## Cabeçalho
* HTML - Cabeçalho da pagina (que o usuário consegue visualizar)
```<header></header>```
vai dentro da tag <body>
Qualquer tipo de elemento, pode ser inserido neste cabeçalho

* HTML - Links
```<a href="index.html">Home</a>```
a: tag para link
href: caminho para o link
Home: o titulo do link (que ficará visível para o usuário)

* CSS - Texto em maiúscula
```text-transform: uppercase;```

* CSS - Remover sublinhado dos links
```text-decoration: none;```

## Posições dos elementos
A posição do elemento, é em relação ao corpo da página. Definindo como relative ou como absolute, o elemento será trazido para "frente" do resto dos elementos.

* Posição  estática: é a posição inicial padrão do elemento - canto superior esquerdo e junto ao body.

![](imagens/position_static.png)


* Posição relativa: é a posição inicial a partir da posição estática, mas uma posição "à frente" do resto do body.
* 
Exemplo:
```css
.elementoX{
	position: relative;
	top: 10px;
	left: 20px
}
```
O início do elemento, será 10 pixels abaixo e 20 pixels par a direita do ponto inicial padrão dele. 


![](imagens/position_relative.png)


* Posição absoluta: muda o ponto inicial padrão do elemento, mas na parte da "frente" do resto do body.
* 
![](imagens/position_absolute.png)

## Posicionando o Cabeçalho
```css
nav{
position: absolut;
top: 0;
right: 0
/*isso deixa o elemento no canto superior direito da pagina*/	
}
```

Para centralizar os elementos do cabeçalho, é preciso que tenha uma "caixa" envolvendo-os.  Então é necessário colocá-los dentro de uma ```<div></div>``` com uma classe.
```css
.caixa{
width: 940px; /*padrão web*/
}
```
Só com essa configuração, os elementos ainda não estão dentro da caixa. É preciso inseri-los dentro dela.
O ponto absoluto, é em relação à página. Então, como o **nav** está com posicionamento absoluto, ele está na "frente" dos outros elementos da página. Será necessário que a caixa tambem tenha uma position (que com isso vai traze-la para "frente"), para que a caixa envolva o **nav**.
```css
.caixa{
	width: 940px;
	position: relative;
	margin: 0 auto;
}
```
A margem definida, irá deixar a caixa no centro da tela (0 top e bottom/ auto right e left). 

O menu (nav) é absoluto e a caixa (div) é relativo. Como os dois "estão na frente do body", o nav passa aser absoluto em relação à caixa. 

Código HTML:
```html
<body>
	<header>
		<div class="caixa">
			<nav>
				HOME PRODUTOS CONTATO
			</nav>
		</div>
	</header>
</body>
```

Agora definir um espaço entre os elementos do cabeçalho e as laterais da pagina, para que os elementos da caixa, nunca encoste nas laterais
```css
header{
	padding: 20px; /*espaçamento interno do cabeçalho*/
}
```

* CSS - arredondas borda
* ```border-radius: 10```

## Elementos produtos

* Para posicionar a lista de produtos um ao lado do outro
```<ul class="produtos"></ul>```

```css
.produtos li {
	display: inline-block;
	text-align: center;
	width: 30%;
	vertical-align: top;
	margin: 0 1.5%;
	padding: 30px 20px;
	box-sizing: border-box;
	border: 2px solid #000000;
	border-radius: 10px;
}
```

* Alterar a cor da borda ao passar o mouse por cima
```css
.produtos li:hover {
	border-color: #C78C19;
}
```

## Pseudo-classes

É possível utilizar o css para mapear o que o usuário está fazendo e, a partir da iteração do usuário, mudar o comportamento do elemento na página.

Exemplo HTML
```html
<ul class="produtos">
	<li>
		<h2>Cabelo</h2>
	</li>	
	<li>
		<h2>Barba</h2>
	</li>
</ul>
```




* **:hover**
Quando o mouse está em cima do elemento
```css
produtos li:hover{
	border-color: red;
	/* quando o mouse ta em cima da area do list-item, muda a cor da borda do produto para vermelho */
}
produtos li:hover h2{
	text-size: 30px;
	color: green;
	/*quando o mouse ta em cima da area do list-item, aumenta e muda a cor do texto h2 */
}
```


* **:active**
Quando está com o click do mouse pressionado
```css
produtos li:active{
	border-color: yellow;
	/* quando clica na area do list-item, muda a cor da borda para amarelo*/
}
```

* CSS - colocar imagem
```background: url("caminho_da_imagem.jpg");```

## Caracteres especiais

COPYRIGHT

Número Unicode: U+00A9

```html
Código HTML: &#169; (& # 1 6 9 ; )
```
```css
CSS-Code: \00A9
```
```
Entidade: &copy;
```

## CSS - Seletores Avançados 

Os seletores avançados possuem a mesma força, o que significa que quem vier depois no css, é o que vai valer.

**Lista das forças (do mais fraco para o mais forte):**
4 - tag
3 - classe
2 - id
1 - código inline (dentro da tag)

### Selecionar filhos diretos

* **Selecionando todos paragrafos que são filhos diretor do *main* **
Exemplo HTML:
```html
<main>
	<p>Paragrafo 1</p>
	<div>
		<p>Paragrafo 2</p>
	</div>
	<p>Paragrafo 3</p>
</main>
```
Seleção no CSS:
```css
main > p{
	estilização aqui
}
```

* **Selecionar o primeiro parágrafo após uma imagem**
```html
<div>
	<img src="imagem.jpg">
	<h1>Esse é um título</h1>
	<p> Esse é o parágrafo </p>
</div>
```
Seleção no CSS:
```css
img + p{
	estilicação aqui
}
```
* **Selecionar todos os paragrafos após uma imagem**
Seleção no CSS:
```css
img ~ p{
	estilização aqui
}
```

* **Selecionar o paragrafo que não tem id "ingles"**
Exemplo HTML:
```html
<p id="portugues"> Bom dia </p>
<p id="ingles"> Good morning </p>
<p id="espanhol"> Buenos dias </p>
```
Seleção no CSS:
```css
p:not(#ingles){
	estilização aqui
}
```

## Cálculos com CSS
Serve para posicionamento de elementos dinamicamente em diversos dispositivos diferentes.
```css
#imagem_teste{
width: calc(40% - 26px);
/*
calc: formula (matemática básica)
40%: o tamanho total da imagem
-: operador (nesse exemplo, menos)
26px: quantidade que quer subtrair*/
}
```