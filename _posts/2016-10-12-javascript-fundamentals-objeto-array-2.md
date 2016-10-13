---
layout: post
title: "Javascript Fundamentals - Objeto Array #2"
date: 2016-10-12 18:00:00
image: '/assets/img/'
description: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
---

Quero começar esse post agradecendo pelo feedback de vocês. Divulguei ontem esse blog (e essa série) em alguns grupos do facebook e a recepção da comunidade foi simplesmente incrível! Recebi alguns comentários bem bacanas, sugestões e dicas para essa minha nova jornada. **Vocês são fodas!** Estou bastante empolgado e motivado com tudo isso. :)

Lembrando que essa série tem como objetivo produzir uma explicação simples, direta e no nosso idioma dos recursos do Javascript. Conteúdo mais aprofundado ou até mesmo resolução de problemas reais utilizando a linguagem fica para futuras séries, tudo bem?

---

Sem mais delongas, vamos para o código. Hoje vamos conversar um pouco sobre as seguintes funções:

```reverse()```, ```sort()``` e ```splice()```.

### reverse()

Usado para **inverter** os itens de um array.

{% highlight js %}
var heisenberg = ['name', 'my', 'Say'];

// Invertendo os itens
heisenberg.reverse();

console.log(heisenberg);
> ["Say", "my", "name"]
{% endhighlight %}

### sort()

Usado para **ordenar** os itens de um array. Com strings, os itens serão colocados em ordem alfabética:

{% highlight js %}
var xuxa = ['B de baixinho', 'C de coração', 'A de amor', 'D de docinho'];

// Colocando os itens em ordem alfabética
xuxa.sort();

console.log(xuxa);
> ["A de amor", "B de baixinho", "C de coração", "D de docinho"]
{% endhighlight %}

Já com números, os itens são colocados em ordem crescente. Infelizmente na prática a teoria é outra e o javascript considera, por exemplo, 45 menor que 7.

{% highlight js %}
var numeros = [4, 3, 7, 1, 45];

// Colocando os itens em ordem crescente
numeros.sort();

console.log(numeros);
> [1, 3, 4, 45, 7]
{% endhighlight %}

Isso acontece porque todos os itens são convertidos para string. Então o javascript verifica posição por posição até encontrar alguma diferença e definir qual é a relação entre os itens. No caso, "45" é menor que "7" porque "4" (primeira posição) vem antes de "7".

Para resolver esse problema podemos passar como parâmetro uma função que explique como queremos essa ordenação:

{% highlight js %}
var numeros = [4, 3, 7, 1, 45];

// Colocando os itens em ordem crescente
numeros.sort(function(a, b) {
    return a - b;
});

console.log(numeros);
> [1, 3, 4, 7, 45]
{% endhighlight %}

Perfeito, não? Essa função simplesmente pega os dois itens que o javascript está comparando no momento e subtrai um pelo outro.

- Se o retorno dessa conta for **zero**, então são dois números _iguais_.
- Se o retorno dessa conta for **positivo**, então ```a``` é _maior_ que ```b```.
- Se o retorno dessa conta for **negativo**, então ```a``` é _menor_ que ```b```.

### splice()

Usado para **remover** itens de um array.

{% highlight js %}
var nomes = ['Caue Queiroz', 'Luke Skywalker', 'Han Solo', 'Princesa Leia'];

// Me deixando sozinho com a Princesa Leia ( ͡° ͜ʖ ͡°)
nomes.splice(1, 2);

console.log(nomes);
> ["Caue Queiroz", "Princesa Leia"]
{% endhighlight %}

O primeiro parâmetro é onde você quer **iniciar o corte**. No caso, minha intenção era começar removendo o ```Luke Skywalker```. Ele estava na posição ```1``` (começa no 0 a contagem, lembra?), então simplesmente usei esse valor no primeiro parâmetro.

O segundo parâmetro é **quantos itens** você quer remover. A ideia era remover o ```Luke Skywalker``` e o ```Han Solo```, ou seja, ```2``` itens. Bem simples, não?

Duas informações importantes sobre esse segundo parâmetro:

- Caso ele seja **0**: nenhum item será removido.
- Caso você **não use** ele: todos os itens serão removidos (a partir da posição do primeiro parâmetro, claro).

{% highlight js %}
var nomes = ['Caue Queiroz', 'Luke Skywalker', 'Han Solo', 'Princesa Leia'];

// Me deixando...sozinho :(
nomes.splice(1);

console.log(nomes);
> ["Caue Queiroz"]
{% endhighlight %}

Por fim, você ainda consegue com esse método adicionar alguns itens a partir da posição do primeiro parâmetro. Para isso, basta listar o que você quer adicionar **após o segundo parâmetro**:

{% highlight js %}
var nomes = ['Caue Queiroz', 'Luke Skywalker', 'Han Solo', 'Princesa Leia'];

// Removendo o Luke e o Han Solo, mas adicionando outras pessoas no lugar
nomes.splice(1, 2, 'Mestre Yoda', 'Darth Vader', 'Chewbacca');

console.log(nomes);
> ["Caue Queiroz", "Mestre Yoda", "Darth Vader", "Chewbacca", "Princesa Leia"]
{% endhighlight %}

Nesse caso, além de remover os itens como no primeiro exemplo, ele adicionou os itens listados depois do segundo parâmetro!

---

Assim finalizamos os métodos responsáveis por _modificar_ um array. Fique a vontade para comentar o que está achando da série, ou se tem alguma dica bacana de uso dos métodos já estudados! Nos vemos amanhã. :)