---
layout: post
title: "Javascript Fundamentals - Objeto Number #1"
date: 2016-10-25 07:00:00
image: '/assets/img/'
description: 'Uma jornada pelo objeto number, seus métodos e propriedades.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Uma jornada pelo objeto number, seus métodos e propriedades.'
archive: true
---

O próximo objeto que vamos estudar será o **Number**. Ele é bastante simples, tem poucas propriedades e métodos. Acredito que em dois posts conseguimos conversar bem sobre ele. :)

`MAX_VALUE`, `MIN_VALUE`, `POSITIVE_INFINITY`, `NEGATIVE_INFINITY` e `NaN`.

Veremos também dois métodos:  
`toString()` e `valueOf`.


### MAX_VALUE

Usado para **gerar** o maior número possível representado no javascript. Qualquer valor acima disso é representado como `Infinity`.

{% highlight js %}
// Qual o maior número possível?
var highest = Number.MAX_VALUE;

console.log(highest);
> 1.7976931348623157e+308
{% endhighlight %}

### MIN_VALUE

Usado para **gerar** o menor número possível representado no javascript. Ao contrário do que se pode pensar, ele não retorna o maior número negativo possível. O retorno é o número positivo mais próximo de zero. Qualquer valor positivo abaixo disso é representado como `0`.

{% highlight js %}
// Qual o menor número possível?
var lowest = Number.MIN_VALUE;

console.log(lowest);
> 5e-324
{% endhighlight %}

### POSITIVE_INFINITY

Essa propriedade **retorna** o infinito positivo. Lembra do valor acima do `MAX_VALUE`? É exatamente esse.

{% highlight js %}
// Infinito positivo
var positiveInfinity = Number.POSITIVE_INFINITY;

console.log(positiveInfinity);
> Infinity
{% endhighlight %}

### NEGATIVE_INFINITY

Essa propriedade **retorna** o infinito negativo. O menor número possível, incluindo números negativos dessa vez.

{% highlight js %}
// Infinito negativo
var negativeInfinity = Number.NEGATIVE_INFINITY;

console.log(negativeInfinity);
> -Infinity
{% endhighlight %}

### NaN

Essa propriedade **retorna** o valor `NaN`. Esse valor significa `Not-a-Number` e representa...algo que não é um número (elementar, meu caro Watson).

{% highlight js %}
// Exemplo mais complexo desse universo (e dos paralelos também :p)
var valueNaN = Number.NaN;

console.log(valueNaN);
> NaN
{% endhighlight %}

### .toString()

Usado para **transformar** um _number_ em uma _string_. Esse é um dos métodos genéricos presentes em todos os outros objetos.

{% highlight js %}
var idade = 21;

// Transformando em uma string
var texto = idade.toString();

console.log(texto);
> "21"
{% endhighlight %}

### .valueOf()

Usado para **retornar** o valor primitivo de um objeto Number. Esse é um dos métodos genéricos presentes em todos os outros objetos. Um exemplo prático:

{% highlight js %}
var numero = new Number(21);

// Fazendo uma rápida verificação no tipo...
console.log(typeof numero);
> object

// ...agora obtendo o valor primitivo desse objeto
var foo = numero.valueOf();

console.log(typeof foo);
> number
{% endhighlight %}

---

> _Esse post faz parte de uma série. Quer ver as outras postagens? [Clique aqui]({% post_url 2016-10-10-javascript-fundamentals %})._