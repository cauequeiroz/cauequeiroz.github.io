---
layout: post
title: "Javascript Fundamentals - Objeto String #2"
date: 2016-11-03 11:00:00
image: '/assets/img/'
description: 'Uma jornada pelo objeto string, seus métodos e propriedades.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Uma jornada pelo objeto string, seus métodos e propriedades.'
---

Continuando nossa conversa sobre o Objeto String, hoje veremos os seguintes métodos:

`indexOf()`, `lastIndexOf()`, `trim()`, `repeat()` e `split()`. 

### indexOf()

Método usado para **verificar** a ocorrência de uma determinada string em outra.

{% highlight js %}
var foo = "Where's Wally?";

// ...onde está o wally?
var bar = foo.indexOf('Wally');

console.log(bar);
> 8
{% endhighlight %}

O retorno será a exata posição onde se inicia determinada string. Caso não encontre nada, o retorno será `-1`. Esse método é _case sensitive_, não se esqueça disso.

Você pode passar como **segundo parâmetro** uma posição inicial para a busca ser feita.

### lastIndexOf()

Método usado para **verificar** a última ocorrência de uma determinada string em outra.

{% highlight js %}
var tvshow = 'westworld';

// Qual a última ocorrência do "w"?
var foo = tvshow.lastIndexOf('w');

console.log(foo);
> 4
{% endhighlight %}

Semelhante ao método anterior, esse também retorna a exata posição da última ocorrência e é _case sensitive_.

Você pode passar como **segundo parâmetro** uma posição inicial para a busca ser feita, lembrando que nesse método a string base é lida do fim para o início.

### trim()

Usado para **remover** os espaços no começo e no final de uma string.

{% highlight js %}
var foo = '   Caue Queiroz         ';

// Removendo os espaços
var bar = foo.trim();

console.log(bar);
> "Caue Queiroz"
{% endhighlight %}

### repeat()

Usado para **repetir** uma determinada string.

{% highlight js %}
var horror = "Bloody Mary ";

// Não faça isso na frente do espelho, sério.
var foo = horror.repeat(3);

console.log(foo);
> "Bloody Mary Bloody Mary Bloody Mary"
{% endhighlight %}

Passe como parâmetro a quantidade de vezes que quer repetir a string. Importante lembrar que esse é um método novo da linguagem e ainda não funciona no Internet Explorer e no Opera.

### split()

Esse método é usado para **separar** uma string em várias partes.

{% highlight js %}
var series = 'Supernatural Narcos GoT Spartacus';

// Grando um array de series
var arr = series.split(' ');

console.log(arr);
> ["Supernatural", "Narcos", "GoT", "Spartacus"]
{% endhighlight %}

Como visto, o retorno será um array com os itens separados.

Passe como parâmetro o que deseja usar para quebrar a string. Nesse exemplo, a cada espaço encontrado a string será quebrada. Mas pode ser qualquer outra coisa, até mesmo uma expressão regular. :)

Você pode passar como **segundo parâmetro** um limite. A string só será quebrada `x` vezes, baseada nesse valor.

{% highlight js %}
var series = 'Supernatural Narcos GoT Spartacus';

// Grando um array de series
var arr = series.split(' ', 2);

console.log(arr);
> ["Supernatural", "Narcos"]
{% endhighlight %}

---

> _Esse post faz parte de uma série. Quer ver as outras postagens? [Clique aqui]({% post_url 2016-10-10-javascript-fundamentals %})._