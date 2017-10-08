---
layout: post
title: "Javascript Fundamentals - Objeto Array #5"
date: 2016-10-17 19:00:00
image: '/assets/img/'
description: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
archive: true
---

Hoje vamos começar a falar sobre os _métodos de iteração_. Cada um deles será responsável por percorrer todos os itens do array, como em um _loop_. O que acontecerá? Cada método tem sua particularidade, nós veremos cada uma delas!

```forEach()```, ```filter()``` e ```map()```.

### forEach()

Usado para **percorrer** todos os itens de um array.

Esse método é um pouco mais complexo do que os anteriores. A primeira coisa que você precisa saber é que ele fará um _loop_ e percorrerá cada item do array executando uma função. Para isso, passamos como parâmetro essa função. No momento elas estará vazia, apenas entenda que essa função será chamada para cada item.

{% highlight js %}
var nomes = ['Caue', 'Luke', 'Walter', 'Obi-wan'];

nomes.forEach(function() { });
{% endhighlight %}

Perfeito, sabemos que essa função será chamada para cada item do array. Agora precisamos receber esse item de alguma forma, afinal, estamos percorrendo esse array com algum objetivo, certo? Imagine que nosso objetivo seja simplesmente imprimir na tela cada item. Para isso, basta receber o elemento como um parâmetro.

{% highlight js %}
var nomes = ['Caue', 'Luke', 'Walter', 'Obi-wan'];

// Imprimindo o item
nomes.forEach(function(elemento) {
    console.log(elemento);
});

> Caue
> Luke
> Walter
> Obi-wan
{% endhighlight %}

Podemos também receber a posição desse item em um segundo parâmetro. 

{% highlight js %}
var nomes = ['Caue', 'Luke', 'Walter', 'Obi-wan'];

// Percorrendo todos os elementos
nomes.forEach(function(elemento, posicao) {
    console.log( posicao + ' - ' + elemento );
});

> 0 - Caue
> 1 - Luke
> 2 - Walter
> 3 - Obi-wan
{% endhighlight %}

O nome desses parâmetros não importa muito, apenas fique atento para receber o **elemento no primeiro parâmetro** e a **posição no segundo**. É bem comum vermos códigos usando a nomenclatura _elem_/_value_ e _index_ para isso. :)

### filter()

Usado para percorrer os elementos de um array e **retornar**, em um novo array, apenas os itens que passaram por determinado teste.

Assim como o ```forEach()```, esse método também recebe uma função que será executada para cada item. Essa função nos dá o elemento e a posição se usarmos os respectivos parâmetros. O que temos de diferente agora é que, dentro da nossa função, escreveremos um teste. Estamos filtrando o array. O novo array será formado apenas pelos itens que passaram nesse teste. Confuso? Vamos para um exemplo prático.

{% highlight js %}
var idades = [8, 21, 18, 5, 27, 42];

// Criando um array com as idades maiores ou iguais a 18 anos
var adultos = idades.filter(function(elemento) {
    return elemento >= 18;
});

console.log(adultos);
> [21, 18, 27, 42]
{% endhighlight %}

### map()

Usado para percorrer os elementos de um array e **executar** uma determinada função em cada um dos itens.

{% highlight js %}
var numeros = [2, 3, 4, 5];

// Essa função recebe um número e retorna o dobro dele
var dobrar = function(numero) {
    return numero * 2;
};

// Dobrando cada item do array usando a função que criamos
var dobrados = numeros.map(dobrar);

console.log(numeros);
> [2, 3, 4, 5]
console.log(dobrados);
> [4, 6, 8, 10]
{% endhighlight %}

Esse método retornará um novo array com as alterações, ou seja, o array original não será modificado.

---

> _Esse post faz parte de uma série. Quer ver as outras postagens? [Clique aqui]({% post_url 2016-10-10-javascript-fundamentals %})._