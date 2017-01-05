BOTLUCAS

No bot que eu fiz existe três opções que ele pode retornar uma resposta como foi pedido no teste.

A primeira ele pode dar oi e lembrar dos nomes,Código abaixo:

<?xml version="1.0" encoding="UTF-8"?>
<aiml version="2.0">
<category>
<pattern>Oi</pattern>
<template>Olá, Como você vai?</template>
</category>

<category>
<pattern>Meu nome é *</pattern>
<template>Eae <set name="name"><star/></set>, Do que você precisa agora?</template>
</category>

<category>
<pattern>Será que você sabe como eu me chamo</pattern>
<template>
<random>
<li><get name="name"></get>!</li>
<li>Amigo, o seu nome é <get name="name"></get></li>
<li>Não ta nem se lembrando do seu nome <get name="name"></get></li>
</random>
</template>
</category>


</aiml>

A segunda ele pode contar números,Código abaixo:

<?xml version="1.0" encoding="UTF-8"?>
<aiml version="2.0">
 <category>
<pattern>Você consegui contar de <set>number</set> até <set>number</set></pattern>
<template><think><set var="count">0</set></think>
<condition var="count">
<li><value><star/></value></li>
<li><set var="count"><map><name>successor</name><get name="count"/></map></set>
<loop/></li>
</condition></template>
</category>
</aiml>

a terceira ele retorna uma pergunta quando ele não entende o que você falou, código abaixo:

<?xml version="1.0" encoding="UTF-8"?>
<aiml version="2.0">
<category>
<pattern>se o boi bate no meu carro, o paraíso é logo ali</pattern>
<template>Não entendi, você pode falar de outro jeito?</template>
</category>
</aiml>
