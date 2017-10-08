---
layout: post
title: "Javascript Fundamentals - Objeto String #3"
date: 2016-11-04 14:00:00
image: '/assets/img/'
description: 'Uma jornada pelo objeto string, seus métodos e propriedades.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Uma jornada pelo objeto string, seus métodos e propriedades.'
---

É muito bom escrever um post por dia, mas confesso que estou ficando sem ter o que falar na introdução de cada post! haha Vamos lá, mais alguns métodos do Objeto String. :)

`toUpperCase()`, `toLowerCase()`, `startsWith()`, `replace()` e `substr()`.

### toUpperCase()

Esse método é usado para **converter** todas as letras para maiúsculas.

{% highlight js %}
var foo = 'estou gritando com você.';

// Vamos deixar um pouco mais expressiva essa frase?
var bar = foo.toUpperCase();

console.log(bar);
> "ESTOU GRITANDO COM VOCÊ."
{% endhighlight %}

### toLowerCase()

Método usado para **converter** todas as letras para minúsculas.

{% highlight js %}
var foo = 'AINDA ESTOU GRITANDO COM VOCÊ.';

// ...é, chega de gritar, não?
var bar = foo.toLowerCase();

console.log(bar);
> "ainda estou gritando com você."
{% endhighlight %}

### startsWith()

Usado para **verificar** se uma string começa com uma determinada string.

{% highlight js %}
var frase = 'babuínos bobocas balbuciando em bando';

// A string começa com 'babuínos'?
var check = frase.startsWith('babuínos');

console.log(check);
> true
{% endhighlight %}

Passe como parâmetro a string que quer comparar a semelhança.

Você também pode usar como **segundo parâmetro** uma posição inicial. Quando esse parâmetro não é passado, é usado a posição `0` da string base como referência para fazer a comparação. Podemos pedir para considerar apenas a partir da posição 9 (`bobocas balbuciando em bando`):

{% highlight js %}
var frase = 'babuínos bobocas balbuciando em bando';

// A string começa com 'bobocas'?
var check = frase.startsWith('bobocas', 9);

console.log(check);
> true
{% endhighlight %}

### replace()

Método usado para **substituir** um trecho da string por outro.

{% highlight js %}
var melhorSerie = 'How I met your friends';

// Algo de errado não está certo, vamos corrigir.
var correct = melhorSerie.replace('friends', 'mother');

console.log(correct);
> "How I met your mother"
{% endhighlight %}

O **primeiro parâmetro** é a string (ou uma expressão regular) que você deseja usar como referência para a substituição.

O **segundo parâmetro** é a string que você quer que seja colocada no lugar. Você também pode passar uma função que será executada para cada ocorrência do primeiro parâmetro encontrada. Para saber mais sobre o uso dessa função, [clique aqui](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace#Specifying_a_function_as_a_parameter).

### substr()

Usado para **capturar** um trecho específico de uma string.

{% highlight js %}
var name = 'Game of Thrones';

// Capturando apenas a palavra "Thrones"
var foo = name.substr(8, 7);

console.log(foo);
> "Thrones"
{% endhighlight %}

O **primeiro parâmetro** é a posição que você quer iniciar a captura. Se você passar um valor negativo, o javascript contará as posições do fim para o começo da string. No nosso exemplo, a palavra "Thrones" começa na posição `8`.

O **segundo parâmetro** é quantas posições a partir da inicial você deseja capturar. Novamente, no nosso exemplo usamos o valor `7`, que é a quantidade de letras da palavra "Thrones".

---

> _Esse post faz parte de uma série. Quer ver as outras postagens? [Clique aqui]({% post_url 2016-10-10-javascript-fundamentals %})._