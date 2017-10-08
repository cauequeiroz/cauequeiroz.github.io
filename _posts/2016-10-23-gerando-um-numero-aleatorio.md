---
layout: post
title: "Gerando um número aleatório entre x e y"
date: 2016-10-23 13:00:00
image: '/assets/img/'
description: '...e realmente entendendo o que está acontecendo.'
tags:
- javascript
categories:
- Javascript
twitter_text: 'Gerando um número aleatório entre x e y'
---

Sempre que precisei gerar um número aleatório entre _x (mínimo)_ e _y (máximo)_ o caminho foi o seguinte: Google > StackOverflow > Ctrl+C na fórmula > Sublime > Ctrl+V. Mas, e se eu pudesse de uma vez por todas entender o que acontece por trás dos panos e eu mesmo escrever essa fórmula quando necessário?

Hoje, além de te mostrar uma fórmula bem bacana para gerar esse número, gostaria de te explicar todo o raciocínio usado para se chegar nessa fórmula. :)

## Resultado final

Caso não tenha interesse e só queira a fórmula, o resultado final será esse:

{% highlight js %}
var randomNumber = function(min, max) {
    return Math.floor( Math.random() * (max - min + 1) + min );
}
{% endhighlight %}

---

Antes de começarmos essa conversa, precisamos entender o funcionamento de dois métodos do [Objeto Math](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Math) que serão usados para chegarmos no resultado final.

`Math.random()`: Usado para gerar um número aleatório entre 0 e 1.

Esse método não inclui o número máximo na contagem - no caso, 1 - e vamos precisar levar isso em consideração mais para frente. Então teremos um número gerado entre 0 e 0.999999(...). 

`Math.floor()`: Usado para arredondar um número para baixo.

Basicamente ele retorna o primeiro número inteiro menor que o número que queremos arredondar. Seguindo esse raciocínio, o número `2.98` seria arredondado para `2`.

{% highlight js %}
// Gerando um número aleatório
var foo = Math.random();

console.log(foo);
> 0.9876368262553472

// Arredondando um número
var bar = Math.floor(2.98);

console.log(bar);
> 2
{% endhighlight %}

## Por trás da fórmula

Não será nada muito complexo o caminho para se chegar no resultado final, apenas vamos precisar abstrair um pouco as coisas, pensar nos resultados possíveis de cada etapa e ir evoluindo com calma até chegarmos onde queremos. Vamos lá?

**Objetivo:** Gerar um número inteiro (sem decimal) entre _1 (mínimo)_ e _5 (máximo)_.

Sabemos que o `Math.random()` gera um número entre 0 e 0.9999(...). O primeiro passo será multiplicar esse resultado pelo número máximo que queremos.

{% highlight js %}
Math.random() * max
{% endhighlight %}

Quando fazemos isso, mudamos o range de resultados. Se usarmos o número `5` como exemplo os resultados serão entre `0` e `4.99999(...)`.

- Se `Math.random()` for `0`: 0 * 5 = **0**
- Se `Math.random()` for `0.42`: 0.42 * 5 = **2.1**
- Se `Math.random()` for `0.89`: 0.89 * 5 = **4.45**
- Se `Math.random()` for `0.9999`: 0.9999 * 5 = **4.99**

Temos alguns problemas ainda: não está gerando números redondos, o mínimo é zero e o máximo, apesar de chegar bem perto do nosso valor, ainda é menor.

Primeiro vamos parar de gerar números com casas decimais arredondando o resultado para baixo:

{% highlight js %}
Math.floor( Math.random() * max )
{% endhighlight %}

Com todos os números sendo arredondados, o nosso range de resultados está entre `0` e `4`.

- Se `Math.random()` for `0`: 0 * 5 = 0 => **0**
- Se `Math.random()` for `0.42`: 0.42 * 5 = 2.1 => **2**
- Se `Math.random()` for `0.65`: 0.65 * 5 = 3.25 => **3**
- Se `Math.random()` for `0.9999`: 0.9999 * 5 = 4.99 => **4**

Se somarmos o valor mínimo que queremos (1) ao resultado, transformamos o nosso range de `[0, 4]` para `[1, 5]`.

{% highlight js %}
Math.floor( Math.random() * max + min )
{% endhighlight %}

- Se `Math.random()` for `0`: 0 * 5 = 0 => 0 => **1**
- Se `Math.random()` for `0.42`: 0.42 * 5 = 2.1 => 2 => **3**
- Se `Math.random()` for `0.65`: 0.65 * 5 = 3.25 => 3 => **4**
- Se `Math.random()` for `0.9999`: 0.9999 * 5 = 4.99 => 4 => **5**

Com isso, já conseguimos gerar um número aleatório entre _1 (mínimo)_ e _x (máximo)_ e finalizamos a primeira parte da nossa fórmula! Simples, não? :)

Porém, nossa fórmula não funcionará se você tentar usar como valor mínimo algo diferente 1:

- Se `min` for `1`: conseguimos resultados entre [1, 5]
- Se `min` for `4`: conseguimos resultados entre [4, 8] (?)

Estranho, né? O que usamos atualmente como `min` ainda não é realmente o valor mínimo. Como tudo é arredondado para baixo, precisamos de alguma forma incluir o valor máximo nas possibilidades de resultado. Quando somamos um (+1) conseguimos isso. Então em vez de o máximo ser `4.99` (que acaba se tornando `4`), nossa conta chega até `5.99` (que se torna `5`, o que realmente queremos como máximo). Coincidentemente, o resultado mínimo que seria `0` se torna `1`.

Se queremos definir um valor mínimo diferente de `1`, precisamos fazer uma pequena correção: subtrair esse valor do valor máximo e somar `1` (pelos motivos explicados no último parágrafo):

{% highlight js %}
// Antigo
Math.floor( Math.random() * max + min )

// Novo
Math.floor( Math.random() * (max - min + 1) + min )
{% endhighlight %}

Com isso, chegamos ao fim da explicação. Esse é o resultado final da nossa fórmula e já pode ser usado sempre que quiser gerar um número aleatório entre _x (mínimo)_ e _y (máximo_).

{% highlight js %}
var randomNumber = function(min, max) {
    return Math.floor( Math.random() * (max - min + 1) + min );
}
{% endhighlight %}

---

É realmente complicado, no começo, abstrair as coisas para gerar fórmulas genéricas que possam ser usadas em qualquer cenário. Mas, com bastante estudo e dedicação, esse tipo de coisa vai ficando cada vez mais fácil! Espero que a explicação tenha ficada clara e simples, e que tenha te ajudado a entender o que acontece por trás dos bastidores nessa fórmula. :)

> _Quer estudar cada método e propriedade dos objetos no Javascript? [Clique aqui]({% post_url 2016-10-10-javascript-fundamentals %})._