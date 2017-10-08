---
layout: post
title: "Javascript Fundamentals - Objeto Number #2"
date: 2016-10-30 17:00:00
image: '/assets/img/'
description: 'Uma jornada pelo objeto number, seus métodos e propriedades.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Uma jornada pelo objeto number, seus métodos e propriedades.'
archive: true
---

Hoje vamos finalizar mais um objeto dessa série! Os métodos que veremos retornam um novo valor com a alteração necessária sem modificar o original. Por isso, lembre-se sempre de salvar em uma nova variável. :)

`toFixed()`, `toPrecision()` e `toExponential()`.


### toFixed()

Usado para **controlar** a quantidade de casas decimais de um número.

{% highlight js %}
var foo = 42.685944;

// Convertendo para duas casas decimais
var bar = foo.toFixed(2);

console.log(bar);
> "42.69"
{% endhighlight %}

Passe como parâmetro um número, entre `0` e `20`, que represente a quantidade de casas decimais que você deseja. O valor retornado por esse método é uma _string_. Talvez seja necessário transformar em _number_ novamente caso queira ter um pouco mais de controle.

### toPrecision()

Usado para **controlar** o tamanho de um número.

Esse método é bem semelhante ao anterior. Porém, enquanto o `toFixed()` controla apenas o que acontece após a vírgula, esse método leva em consideração o número todo.

{% highlight js %}
var foo = 42.685944;

// Deixando o número com apenas 3 dígitos
var bar = foo.toPrecision(3);

console.log(bar);
> "42.7"
{% endhighlight %}

Passe como parâmetro o tamanho que você deseja que o novo número tenha. Esse método também retorna o valor como uma _string_.

### toExponential()

Usado para **converter** um número em sua notação exponencial.

{% highlight js %}
var foo = 42.685944;

// Convertendo para exponencial
var bar = foo.toExponential();

console.log(bar);
> "4.2685944e+1"
{% endhighlight %}

Semelhante aos demais métodos, o retorno é uma _string_. Esse método pode receber como parâmetro a quantidade de casas decimais que essa notação terá.

{% highlight js %}
var foo = 42.685944;

// Convertendo para exponencial
var bar = foo.toExponential(2);

console.log(bar);
> "4.27e+1"
{% endhighlight %}

---

> _Esse post faz parte de uma série. Quer ver as outras postagens? [Clique aqui]({% post_url 2016-10-10-javascript-fundamentals %})._