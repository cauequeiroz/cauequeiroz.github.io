---
layout: post
title: "Javascript Fundamentals - Objeto Array #1"
date: 2016-10-11 18:00:00
image: '/assets/img/'
description: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
---

Vamos começar nossa jornada de estudos com o **objeto array**. Apesar de não ser muito a intenção dessa série, antes de partir para as primeiras funções vou explicar brevemente o que é um array, como criar um e acessar seus itens. Não será nada muito aprofundado, mas será o suficiente para quem ainda não tem muita familiaridade com isso conseguir acompanhar os próximos posts. :)

## Introdução

Um array nada mais é do que um objeto que te permite armazenar diversos itens. Esses itens podem ser uma _string_, um _number_, um _boolean_, um objeto e até mesmo outro array! Caso ainda não consiga ver uma utilidade prática para isso, vou te mostrar um rápido exemplo:

{% highlight js %}
var nome1 = 'Caue Queiroz';
var nome2 = 'Luke Skywalker';
var nome3 = 'Han Solo';
{% endhighlight %}

Olha quanta variável criamos para armazenar informações parecidas. Com um array podemos fazer isso de uma forma muito melhor.

{% highlight js %}
var nomes = ['Caue Queiroz', 'Luke Skywalker', 'Han Solo'];
{% endhighlight %}

A partir do momento que você cria um array você consegue acessar os seus itens através de suas respectivas posições. É muito importante lembrar que essa contagem de posições começa no número 0, e não no 1, ok?

{% highlight js %}
console.log(nomes[0]);
> 'Caue Queiroz'
console.log(nomes[1]);
> 'Luke Skywalker'
console.log(nomes[2]);
> 'Han Solo'
{% endhighlight %}

Bem simples, não? Realmente não tem muito segredo para criar e acessar os itens de um array. Com o tempo (e com alguns problemas) você vai perceber como esse tipo de recurso da linguagem é extremamente valioso.

## Funções

Vamos começar conversando sobre os métodos que são responsáveis por _modificar_ um array.

```unshift()```, ```push()```, ```shift()``` e ```pop()```.

### unshift()

Usado para **adicionar** um ou mais elementos **no início** de um array. Coloque como parâmetro o que deseja adicionar.

{% highlight js %}
var nomes = ['Caue Queiroz', 'Luke Skywalker', 'Han Solo'];

// Adicionando "Obi-wan" no início do array
nomes.unshift('Obi-wan');

console.log(nomes);
> ["Obi-wan", "Caue Queiroz", "Luke Skywalker", "Han Solo"]
{% endhighlight %}

### push()

Usado para **adicionar** um ou mais elementos **no final** de um array. Coloque como parâmetro o que deseja adicionar.

{% highlight js %}
var nomes = ['Caue Queiroz', 'Luke Skywalker', 'Han Solo'];

// Adicionando "Obi-wan" no final do array
nomes.push('Obi-wan');

console.log(nomes);
> ["Caue Queiroz", "Luke Skywalker", "Han Solo", "Obi-wan"]
{% endhighlight %}

### shift()

Usado para **remover** o **primeiro** item de um array.

{% highlight js %}
var nomes = ['Caue Queiroz', 'Luke Skywalker', 'Han Solo'];

// Removendo o primeiro item
nomes.shift();

console.log(nomes);
> ["Luke Skywalker", "Han Solo"]
{% endhighlight %}

Caso precise saber qual item foi removido, essa função tem como retorno esse item.

{% highlight js %}
var nomes = ['Caue Queiroz', 'Luke Skywalker', 'Han Solo'];

// Removendo o primeiro item e salvando em uma variável
var removido = nomes.shift();

console.log(nomes);
> ["Luke Skywalker", "Han Solo"]
console.log(removido);
> "Caue Queiroz"
{% endhighlight %}

### pop()

Usado para **remover** o **último** item de um array.

{% highlight js %}
var nomes = ['Caue Queiroz', 'Luke Skywalker', 'Han Solo'];

// Removendo o último item
nomes.pop();

console.log(nomes);
> ["Caue Queiroz", "Luke Skywalker"]
{% endhighlight %}

Caso precise saber qual item foi removido, essa função tem como retorno esse item.

{% highlight js %}
var nomes = ['Caue Queiroz', 'Luke Skywalker', 'Han Solo'];

// Removendo o último item e salvando em uma variável
var removido = nomes.pop();

console.log(nomes);
> ["Caue Queiroz", "Luke Skywalker"]
console.log(removido);
> "Han Solo"
{% endhighlight %}

---

Como tivemos uma pequena introdução hoje, vou finalizar por aqui com esses quatro métodos. Percebeu o padrão, né? Eles são responsáveis por adicionar/remover elementos no início/final de um array.

No próximo post continuamos, e talvez até terminamos, os métodos que modificam um array. Até lá! :)




