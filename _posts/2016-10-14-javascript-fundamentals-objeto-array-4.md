---
layout: post
title: "Javascript Fundamentals - Objeto Array #4"
date: 2016-10-14 15:00:00
image: '/assets/img/'
description: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
archive: true
---

Hoje vamos finalizar os _métodos de acesso_. Lembrando que esses métodos não modificam o array, e sim retornam **um novo array** com as alterações propostas pela função. Por isso, não se esqueça de salvar esse retorno em uma variável, ok?

```toString()```, ```toLocaleString()```, ```indexOf()``` e ```lastIndexOf()```.

### toString()

Usado para **transformar** o array em uma string. Os itens são separados por uma vírgula.

{% highlight js %}
var foo = ['Rick', 'and', 'Morty'];

// Transformando em uma string
var bar = foo.toString();

console.log(bar);
> "Rick,and,Morty"
{% endhighlight %}

Esse é um método genérico presente em todos os objetos. Quando estiver manipulando um array, de preferência pelo método ```join()```.

### toLocaleString()

Usado para **transformar** o array em uma string.

A única diferença entre esse método e o ```toString()```, é que esse leva em consideração convenções locais para fazer a transformação. Isso fica bem claro quando temos, por exemplo, uma data no nosso array:

{% highlight js %}
var date = new Date();
var example = ['item 1', 'item 2', date];

// Usando o método toString
var foo = example.toString();

console.log(foo);
> "item 1,item 2,Fri Oct 14 2016 14:30:09 GMT-0300 (E. South America Standard Time)"

// Usando o método toLocaleString
var bar = example.toLocaleString();

console.log(bar);
> "item 1,item 2,14/10/2016 14:30:09"
{% endhighlight %}

Esse também é um método genérico presente em outros objetos da linguagem.

### indexOf()

Usado para **verificar** a posição de um item em um array.

{% highlight js %}
var people = ['harry', 'rony', 'wally', 'hagrid'];

// Onde está o Wally? (ba dum tsss)
var foo = people.indexOf('wally');

console.log(foo);
> 2
{% endhighlight %}

Se o javascript encontrar o item, o retorno será a exata posição deste item. Caso o contrário, o retorno será -1. Se o item aparecer algumas vezes no array, apenas a posição da primeira ocorrência é considerada, ok?

Esse método aceita um **segundo parâmetro**. Você pode passar uma posição e o javascript começará a busca a partir disso:

{% highlight js %}
var letras = ['a', 'b', 'c', 'd', 'e', 'f', 'g'];

// Começando a busca a partir da 4ª posição
var foo = letras.indexOf('b', 4);

console.log(foo);
> -1
{% endhighlight %}

Como o item "b" está na posição ```1```, não foi encontrado nada a partir da posição especificada (```4```).

Assim como em outros métodos, se você passar um valor negativo nesse segundo parâmetro a busca será feita **de trás para frente**:

{% highlight js %}
var letras = ['a', 'b', 'c', 'd', 'e', 'f', 'g'];

// Buscando nas três últimas posições
var foo = letras.indexOf('f', -3);

console.log(foo);
> 5
{% endhighlight %}

### lastIndexOf()

Usado para **verificar** a posição de um item em um array.

Diferente do método ```indexOf()```, esse método inicia a busca de trás para frente e retorna a última ocorrência do item pesquisado.

{% highlight js %}
var letras = ['a', 'b', 'a', 'd', 'a', 'f', 'g'];

// Buscando o item "a"
var foo = letras.lastIndexOf('a');

console.log(foo);
> 4
{% endhighlight %}

O método anterior retornaria a posição ```0``` (primeira ocorrência do item "a"). Como você pode ver, esse método retorna a posição ```4``` (última ocorrência do item "a").

O **segundo parâmetro** desse método é, semelhante ao método anterior, a posição que você quer que a busca se inicie. Porém, é preciso levar em conta que essa busca já funciona de trás para frente. Use valores negativos, caso contrário a busca será feita em todo o array. Por exemplo:

{% highlight js %}
var letras = ['a', 'b', 'a', 'd', 'a', 'f', 'g'];

// Buscando o item "a" iniciando na 4ª posição de trás para frente
var foo = letras.lastIndexOf('a', -4);

console.log(foo);
> 2
{% endhighlight %}

Como especificamos que a busca começa na 4ª posição (de trás para frente, não esqueça disso), a última ocorrência de "a" é o item da posição ```2```. Não é mais o item da posição ```4```, pois ele está dentro do _range_ de itens do fim do array que foi desconsiderado.

---

> _Esse post faz parte de uma série. Quer ver as outras postagens? [Clique aqui]({% post_url 2016-10-10-javascript-fundamentals %})._