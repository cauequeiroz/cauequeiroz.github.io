---
layout: post
title: "Javascript Fundamentals - Objeto String #1"
date: 2016-11-02 19:00:00
image: '/assets/img/'
description: 'Uma jornada pelo objeto string, seus métodos e propriedades.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Uma jornada pelo objeto string, seus métodos e propriedades.'
archive: true
---

Hoje começamos a conversar sobre um dos objetos mais importantes do javascript: o **Objeto String**. Em diversos cenários você precisará trabalhar com strings em seu código. Sem dúvidas nenhuma, conhecer os métodos oferecidos pela linguagem vai aumentar e muito as suas possibilidades de uso! :)

`charAt()`, `charCodeAt()`, `concat()`, `endsWith()` e `includes()`.

### charAt()

Esse método **retorna** o caractere em uma determinada posição de uma string.

{% highlight js %}
var team = 'Golden State Warriors';

// Qual o caractere na 3 posição?
var foo = team.charAt(3);

console.log(foo);
> "d"
{% endhighlight %}

Passe como parâmetro a posição desejada. Lembrando que a contagem desse index começa na posição `0`.

### charCodeAt()

Esse método **retorna** o valor unicode do caractere em uma determinada posição de uma string.

{% highlight js %}
var team = 'Golden State Warriors';

// Qual o unicode do caractere na 3 posição?
var foo = team.charCodeAt(3);

console.log(foo);
> 100
{% endhighlight %}

Semelhante ao método anterior, passe como parâmetro a posição desejada.

### concat()

Usado para **concatenar** duas ou mais strings.

{% highlight js %}
var firstName = 'Harry';

// Formando o nome completo do bruxão
var wizard = firstName.concat(' Potter');

console.log(wizard);
> "Harry Potter"
{% endhighlight %}

Passe como parâmetro uma ou mais strings que deseja juntar. Em questões de performance, é extremamente recomendado que você junte strings usando o operador `+` ou `+=` no lugar desse método.

### endsWith()

Usado para **verificar** se uma string finaliza com uma determinada string.

{% highlight js %}
var frase = 'babuínos bobocas balbuciando em bando';

// A string finaliza com 'bando'?
var foo = frase.endsWith('bando');

console.log(foo);
> true
{% endhighlight %}

Passe como parâmetro a string que quer comparar a semelhança.

Você também pode usar como **segundo parâmetro** uma posição final. Quando esse parâmetro não é passado, é usado o tamanho total da string base como fazer a comparação. Podemos pedir para considerar apenas as primeiras 28 posições (`babuínos bobocas balbuciando`):

{% highlight js %}
var frase = 'babuínos bobocas balbuciando em bando';

// A string finaliza com 'balbuciando'?
var foo = frase.endsWith('balbuciando', 28);

console.log(foo);
> true
{% endhighlight %}

### includes()

Esse método é usado para **verificar** se existe um determinado termo em uma string.

{% highlight js %}
var quote = "I’m in the empire business";

// Existe o termo 'empire' nessa frase?
var foo = quote.includes('empire');

console.log(foo);
> true
{% endhighlight %}

Passe como parâmetro o termo que deseja verificar. Esse método é _case sensitive_, ou seja, faz diferença se o que for pesquisado está em maiúscula ou minúscula.

Você pode passar como **segundo parâmetro** uma posição para a busca iniciar a partir dela.

Não costumo colocar aqui métodos que não possuem suporte completo dos browsers, porém esse método já pode ser utilizado se você levar em conta que ele não funciona no Internet Explorer.

---

> _Esse post faz parte de uma série. Quer ver as outras postagens? [Clique aqui]({% post_url 2016-10-10-javascript-fundamentals %})._