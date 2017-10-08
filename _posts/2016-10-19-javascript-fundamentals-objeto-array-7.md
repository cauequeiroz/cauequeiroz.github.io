---
layout: post
title: "Javascript Fundamentals - Objeto Array #7"
date: 2016-10-19 23:00:00
image: '/assets/img/'
description: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
archive: true
---

Hoje chegamos ao fim do primeiro objeto estudado nessa série! Além de vermos os dois últimos métodos de iteração, teremos também uma propriedade e um método que apesar de ser bem simples, deve ser chamado de uma forma um pouco diferente das que usamos até aqui. Vamos lá?

```reduce()```, ```reduceRight()```, ```.length``` e ```Array.isArray()```.

### reduce()

Usado para **reduzir** o array em um único item usando determinado critério.

Passamos como parâmetro uma função com esse critério. Vamos ver um exemplo prático antes de conversar com mais calma sobre como isso funciona:

{% highlight js %}
var numeros = [1, 2, 3, 4, 5];

// Quanto fica a soma de todos os itens do array?
// (1 + 2 + 3 + 4 + 5)
var soma = numeros.reduce(function(total, atual) {
    return total + atual;
});

console.log(soma);
> 15
{% endhighlight %}

Basicamente, esse método fará um loop por todos os elementos do array executando a função que passamos como parâmetro. Nessa função, você recebe o que chamamos de **total**, que nada mais é do que o item anterior (ou o resultado de tudo que já aconteceu) e o item atual do loop. No exemplo acima pedimos para o javascript, a cada volta do loop, somar o item anterior com o atual.

Então os itens vão sendo eliminados um a um, o resultado vai se acumulando, até o array ser reduzido a somente um item. Algo mais ou menos assim:

- [1, 2, 3, 4, 5] => 1 + 2 = 3
- [_(3)_, 3, 4, 5] => 3 + 3 = 6
- [_(6)_, 4, 5] => 6 + 4 = 10
- [_(10)_, 5] => 10 + 5 = **15**

Caso ache necessário, você pode receber no **terceiro parâmetro** a posição do item atual.

Você também tem a possibilidade de começar todo o processamento com um valor inicial. Para isso, passe esse valor como segundo parâmetro do método ```reduce()``` (e não da função que tem o critério):

{% highlight js %}
var numeros = [1, 2, 3, 4, 5];

// Quanto fica a soma de todos os itens do array?
// (1 + 2 + 3 + 4 + 5)
var soma = numeros.reduce(function(total, atual) {
    return total + atual;
}, 10); // <- aqui, ó.

console.log(soma);
> 25
{% endhighlight %}

Dessa vez, o resultado foi **25**. Os itens do array foram somados, porém a contagem começou já com o valor 10.

### reduceRight()

Usado para **reduzir** o array em um único item usando determinado critério.

{% highlight js %}
var numeros = [1, 2, 3, 4, 5];

// Quanto fica a soma de todos os itens do array?
// (5 + 4 + 3 + 2 + 1)
var soma = numeros.reduceRight(function(total, atual) {
    return total + atual;
});

console.log(soma);
> 15
{% endhighlight %}

A única diferença desse método para o ```reduce()```, é que dessa vez o loop será feito **da direita para a esquerda**.

- [1, 2, 3, 4, 5] => 5 + 4 = 9
- [1, 2, 3, _(9)_] => 9 + 3 = 12
- [1, 2, _(12)_] => 12 + 2 = 14
- [1, _(14)_] => 14 + 1 = **15**

### length

Usado para **verificar** o tamanho do array.

{% highlight js %}
var hogwarts = ['Harry', 'Rony', 'Hermione', 'Dobby'];

// Quantas pessoas tem em Hogwarts?
var total = hogwarts.length;

console.log(total);
> 4
{% endhighlight %}

Essa é simplesmente uma propriedade do array. Não é um método, logo não precisa ser chamado com `()` e nem receber qualquer tipo de parâmetro.

### Array.isArray()

Usado para **verificar** se determinada variável é um array.

{% highlight js %}
var numeros = [1, 2, 3, 4, 5];
var letras = 'abcde';

// A variável "números" é um array?
var foo = Array.isArray(numeros);

console.log(foo);
> true

// ...e a variável "letras"?
var bar = Array.isArray(letras);

console.log(bar);
> false
{% endhighlight %}

Esse método é diferente de todos que vimos até agora. Ele é usado diretamente no **objeto array**, e não em suas instâncias (os arrays que criamos). Passe como parâmetro a variável que gostaria de verificar se é ou não um array! :)

---

Chegamos ao fim da nossa jornada com o Objeto Array. Com exceção de alguns métodos novos do ES6, conversamos sobre todos os métodos e propriedades desse objeto. O que acharam desse formato? O feedback de vocês é muito importante...sugestões e críticas serão levadas em consideração para os próximos estudos dessa série. Deixe nos comentários o que você achou e até a próxima!

> _Esse post faz parte de uma série. Quer ver as outras postagens? [Clique aqui]({% post_url 2016-10-10-javascript-fundamentals %})._