---
layout: post
title: "Javascript Fundamentals - Objeto Array #3"
date: 2016-10-13 18:00:00
image: '/assets/img/'
description: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
---

Hoje vamos conversar um pouco sobre os _métodos de acesso_. Diferente dos métodos que ja vimos, essas funções não modificam o array em si, elas retornam um novo array com as alterações necessárias. Por isso sempre precisamos salvar o retorno em alguma variável, pois é nessa variável que estará o array que realmente queremos, ok?

Como sempre, o spoiler do que veremos nesse post:

```concat()```, ```join()``` e ```slice()```.

### concat()

Usado para **concatenar** novos elementos em um array.

{% highlight js %}
var heros = ['Batman', 'Superman', 'Spiderman'];

// Adicionando o homem de ferro na brincadeira
var heros_new = heros.concat('Iron Man');

console.log(heros_new);
> ["Batman", "Superman", "Spiderman", "Iron Man"]

// Veja que o array "heros" não sofreu alterações!
console.log(heros);
> ["Batman", "Superman", "Spiderman"]
{% endhighlight %}

Podemos adicionar vários itens...

{% highlight js %}
var dc = ['Batman', 'Aquaman'];

// Adicionando vários itens
var dc_new = dc.concat('Arqueiro Verde', 'Lobo', 'Flash');

console.log(dc_new);
> ["Batman", "Aquaman", "Arqueiro Verde", "Lobo", "Flash"]
{% endhighlight %}

...e até mesmo um array :)
{% highlight js %}
var dc = ['Batman', 'Aquaman', 'Flash', 'Arqueiro Verde'];
var marvel = ['Spiderman', 'Iron Man', 'Hulk', 'Wolwerine'];

// Adicionando um array inteiro
var hq = dc.concat(marvel);

console.log(hq);
> ["Batman", "Aquaman", "Flash", "Arqueiro Verde", "Spiderman", "Iron Man", "Hulk", "Wolwerine"]
{% endhighlight %}

### join()

Usado para **juntar** os itens de um array em uma string.

{% highlight js %}
var letras = ['a', 'b', 'c', 'd'];

// Juntando todas as letras
var alfabeto = letras.join();

console.log(alfabeto);
> "a,b,c,d"
{% endhighlight %}

O javascript junta os itens separando tudo com uma vírgula. Caso queira algo diferente, basta passar como parâmetro:

{% highlight js %}
var letras = ['a', 'b', 'c', 'd'];

// Juntando todas as letras
var alfabeto = letras.join(' > ');

console.log(alfabeto);
> "a > b > c > d"
{% endhighlight %}

### slice()

Usado para **fatiar** um pedaço do array. 

{% highlight js %}
var jokenpo = ['pedra', 'papel', 'tesoura', 'lagarto', 'spock'];

// Fatiando "tesoura" e "lagarto"
var foo = jokenpo.slice(2, 4);

console.log(foo);
> ["tesoura", "lagarto"]
{% endhighlight %}

O **primeiro parâmetro** é onde você quer começar o corte. No caso, quero começar exatamente no item "tesoura". Então, basta eu passar como parâmetro a posição desse item (posição ```2```).

O **segundo parâmetro** é onde você quer terminar o corte. Fique atento porque ele não inclui o elemento da posição que você especificou. Então, se eu quero parar o corte no item "lagarto" (posição ```3```), eu preciso passar a posição ```4``` como parâmetro. Confuso? Na prática, basta você ver a posição do último item que você quer incluir no corte e somar 1. :)

Se você não colocar o segundo parâmetro, o corte será feito até o final do array.

Uma coisa interessante é que se você colocar apenas o primeiro parâmetro com um valor negativo, ele começa a cortar **de trás para frente**. Olha que bacana:

{% highlight js %}
var jokenpo = ['pedra', 'papel', 'tesoura', 'lagarto', 'spock'];

// Fatiando os dois últimos itens ("lagarto" e "spock")
var foo = jokenpo.slice(-2);

console.log(foo);
> ["lagarto", "spock"]
{% endhighlight %}

---

Ficamos por aqui novamente. O que acha de cada post ter de três a cinco funções no máximo? Deixe sua opinião aqui embaixo nos comentários e nos vemos amanhã! :)