---
layout: post
title: "Javascript Fundamentals - Objeto Array #6"
date: 2016-10-18 13:00:00
image: '/assets/img/'
description: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Uma jornada pelo objeto array, seus métodos e propriedades.'
archive: true
---

Os métodos que veremos hoje tem uma coisa em comum: eles verificam os itens de um array e retornam algo caso esse item (ou todos) passe por determinado teste. Apesar de serem bastante semelhantes, cada um é responsável por um tipo específico de verificação ou de retorno. 

```every()```, ```some()```, ```find()``` e ```findIndex()```.

### every()

Usado para **verificar** se **todos** os itens de um array passam em um determinado teste.

Passe como parâmetro uma função com esse teste. Nessa função, você pode receber o elemento e a posição, assim como em outros métodos de iteração. Caso todos os itens do array passem pelo teste, esse método retornará _true_. Caso contrário, _false_.

{% highlight js %}
var idades = [18, 21, 29, 32, 30];

// Verificando se todas as idades são maiores ou iguais a 18 anos
var check = idades.every(function(elemento) {
    return elemento >= 18;	
});

console.log(check);
> true
{% endhighlight %}

### some()

Usado para **verificar** se **algum** dos itens de um array passa em um determinado teste.

Esse método é bem parecido com o ```every()```. A única diferença é que se pelo menos um item do array passar pelo teste, o método retornará _true_. Se realmente nenhum item passar, o retorno será _false_.

{% highlight js %}
var grupos = ['negritude jr', 'karametade', 'exaltasamba', 'molejo'];

// Verificando se tem o clássico dos clássicos nesse array
var check = grupos.some(function(elemento) {
    return elemento === 'molejo';
});

console.log(check);
> true
{% endhighlight %}

Esse método é uma boa escolha para cenários onde você precisa verificar a existência de um determinado item dentro de um array. :)

### find()

Usado para **procurar** em um array o primeiro item que satisfaça um determinado teste.

Use como parâmetro uma função que contenha esse teste. Caso ele encontre um item que passe pelo teste, o método retornará o **valor** desse item.

{% highlight js %}
var nomes = ['Caue', 'Rick', 'Morty', 'Jerry', 'Summer'];

// Verificar se algum nome tem 6 letras
var check = nomes.find(function(elemento) {
    return elemento.length === 6;
});

console.log(check);
> "Summer"
{% endhighlight %}

### findIndex()

Usado para **procurar** em um array o primeiro item que satisfaça um determinado teste.

A única diferença entre esse método e o ```find()```, é que caso algum item passe pelo teste, o método retornará a sua **posição**.

{% highlight js %}
var nomes = ['Caue', 'Rick', 'Morty', 'Jerry', 'Summer'];

// Verificar se algum nome tem 6 letras
var check = nomes.findIndex(function(elemento) {
    return elemento.length === 6;
});

console.log(check);
> 4
{% endhighlight %}


---

> _Esse post faz parte de uma série. Quer ver as outras postagens? [Clique aqui]({% post_url 2016-10-10-javascript-fundamentals %})._