# Estudos-python


 Link para ínicio dos estudos: [python 101](https://python101.pythonlibrary.org/)

Guia: Criar um resumo para cada capítulo e testar os comandos do tutorial diretamente no terminal do vscode (comando `python3` para iniciar). -> Para acessar, usamos CTRL+SHIFT+P e buscamos Create New Terminal

Notas: Se quisermos verificar algum teste no compilador, igual fazemos nas linhas de comando, usamos print("comando") caso este comando apareça alguma mensagem feita pelo python.

### 1) Capítulo 1: Programação IDLE 
- __Usando IDLE__

 Python, por ser uma linguagem interpretativa, utiliza de elementos próprios e não utiliza outros como compiladores. No caso, um que é utilizado é o chamado **IDLE**, que funciona como um editor de código, destacando, depurando e até mesmo preenchendo automaticamente algumas áreas do código.

- __Sobre comentários__

Comentários são de extrema importância para caso alguém queira fazer algum comentário em alguma linha de código, tanto para relembrar algo ou para fazer alguma observação.


### 2) Capítulo 2: Tudo sobre strings

- __Como criar uma string__

 De início podemos fazer strings usando aspas duplas simples e triplas, sendo que as aspas triplas (''') nos proporcionam a opção de continuar a string em outra linha do comando. Outra forma também é utilizando o comando str (informação) no qual podemos guardar as informações já registradas em outro lugar em uma string, esse método é conhecido como **fundição** *(1)*. Strings são imutáveis, ou seja, mesmo se atribuirmos uma definição diferente, mas para um mesmo nome de string, sua **identidade** muda, não sendo mais o mesmo ID daquela string anterior na qual definimos *(2)*.

_(1)_
```
>>> meu_número  =  123 
>>> minha_string  =  str ( meu_número )
```
_(2)_
```
>>> minha_string  =  "abc" 
>>> id ( minha_string ) 
19397208 
>>> minha_string  =  "def" 
>>> id ( minha_string ) 
25558288 
>>> minha_string  =  minha_string  +  "ghi" 
>>> id ( minha_string ) 
31345312
```
- __Concatenar (ou somar) strings__

 Em python para somar strings, ou seja, ajuntar uma na outra, apenas é necessário definir cada uma que queiramos somar, e uma que utilizaremos para guardar, e depois utilizar o operador **soma (+)**.

```
>>> string_one  =  "Meu cachorro comeu" 
>>> string_two  =  " meu dever de casa!" 
>>> string_três  =  string_um  +  string_dois
```
- __Métodos string__

 Por uma string ser um objeto me python, podemos modificar uma string utilizando comandos simples como **upper() lower() strip()** e etc. Estes comandos modificam nossa string e o conteúdo dela, e para saber todos os comandos possíveis utilizamos um comando específico _(3)_. Os métodos que começam e terminam com "__" não são muito utilizados, mas caso queiramos saber para o que cada um serve 
basta utilizar outro comando _(4)_.

_(3)_
```
 >>> dir(my_string)
 ```
_(4)_
 ```
 >>> help(my_string.capitalize)
```
- __Fatiamento de strings__

 Fatiamento de string é um método utilizado para mostrar apenas algumas **partes específicas** da string na qual queremos **visualizar**, em visualização fica mais fácil de entender como demonstrado no bloco de código _(5)_. No caso, podemos fatiar especificando o ínicio, o final, ou ambos. Isso vai depender do que queremos que saia no final. Também podemos acessar caracteres individuais de uma string utilizando `printf(minha_string[n])`, sendo n o número do caractere.

_(5)_
```
>>> my_string = 'I like Python!'
>>> my_string[:1]
'I'
>>> my_string[0:12]
'I like Pytho'
>>> my_string[0:13]
'I like Python'
>>> my_string[0:14]
'I like Python!'
>>> my_string[0:-5]
'I like Py'
>>> my_string[:]
'I like Python!'
>>> my_string[2:]
'like Python!'
```
- __Formatação de string__

 Também conhecida como substiuição, a formatação serve para substituir os valores de uma string base. Na maioria das vezes, você inserirá strings dentro de strings, no entanto, você também inserirá números inteiros e flutuantes em strings com bastante frequência. Aqui temos um exemplo usual de como isso ocorre na prática _(6)_, aqui basicamente mudamos nosso %s para %(lang)s, que é basicamente o %s com uma variável dentro dele. Outro exemplo de substituição é utilizando **format**, no qual aparenta ser mais completo como a seguir _(7)_. Este último exemplo usa um dicionário como usamos no modelo anterior (que são as definições de x e y). No entanto, temos que extrair o dicionário usando o asterisco duplo para que funcione corretamente aqui.

_(6)_
```
>>> print ( " %(lang)s é divertido!"  %  { "lang" : "Python" })
'Python é divertido!'
```

_(7)_
```
>>> "Python é tão simples quanto {0}, {1}, {2}" . format ( "a" ,  "b" ,  "c" ) 
'Python é tão simples quanto a, b, c' 
>>> "Python é tão simples quanto {1}, {0}, {2}" . format ( "a" ,  "b" ,  "c" ) 
'Python é tão simples quanto b, a, c' 
>>> xy  =  { "x" : 0 ,  "y" : 10 } 
>>> print ( " Faça um gráfico de um ponto onde x={x} e y={y}" . format ( ** xy )) 
Faça um gráfico de um ponto onde x=0 e y=10
```

Há muitas outras coisas que você pode fazer com strings, como especificar uma largura, alinhar o texto, converter para bases diferentes e muito mais. Certifique-se de dar uma olhada em algumas das referências no fim do capítulo desta aula.


### 3) Capítulo 3: Listas, Tuplas e Dicionários

- __Listas__

 Uma lista é semelhante a um "array" e pode ser criada de duas maneiras:

```
>>> minha_lista  =  [] 
>>> minha_lista  =  list ()
```
Uma lista contém elementos como strings, inteiros e objetos, podendo conter todos misturados inclusive. O que podemos fazer também, é criar listas de listas:

```
>>> minha_lista_nested  =  [ minha_lista ,  minha_lista2 ] 
>>> minha_lista_nested 
[[1, 2, 3], ['a', 'b', 'c']]
```

Podemos também usar diferentes métodos para combinar duas listas como o método __extend__ ou apenas utilizando o operador __+__:

```
>>> minha_lista  =  [ 1 ,  2 ,  3 ] 
>>> minha_lista2  =  [ "a" ,  "b" ,  "c" ] 
>>> combo_list  =  minha_lista  +  minha_lista2 
>>> combo_list 
[1, 2, 3, ' a', 'b', 'c']
```

Outra coisa que podemos fazer é classificar uma lista usando o comando __lista.sort()__, porém, se tentarmos atribuir uma lista classificada a outra variável qualquer teremos como resultado __None__ (ou NULL), ou seja, não podemos atribuir ela a uma variável diferente.

Além disso, também podemos "fatiar" uma lista com os mesmos comandos que usamos nas strings.

- __Tuplas__

Tuplas são semelhante a listas, mas são criadas com parenteses ao invés de colchetes. A diferença é que uma tupla é __imutável__, como podemos ver no exemplo a seguir:

```
>>> my_tuple = (1, 2, 3, 4, 5)
>>> my_tuple[0:1]
(1, 2, 3)
>>> another_tuple = tuple()
>>> abc = tuple([1, 2, 3])
```
O código acima demonstra uma maneira de criar uma tupla com cinco elementos. Também mostra que podemos fatiar tuplas. No entanto, não podemos classificar uma. Os dois últimos exemplos mostram como criar tuplas usando a palavra-chave tuple, o primeiro apenas cria uma tupla vazia, enquanto o segundo exemplo possui três elementos dentro dela. 

O ultimo exemplo (abc) é também um exemplo de __fundição__, no qual podemos alterar ou converter um item de um tipo de dado para outro (nesse caso de uma lista para uma tupla), e para reverter isso, basta utilizar o comando reverso `abc = lista(abc)`.

- __Dicionários__

Um dicionário é basicamente uma __tabela hash__, podem ser chamados também de memorias associativas ou matrizes associativas. Os dicionarios são indexados com __chaves__ que podem ser de qualquer tipo imutável (uma string, um número, etc). Podemos obter uma lista de chaves utilizando o método __keys__. Para verificar se um dicionário tem uma chave, podemos usar a palavra-chave __in__. Um exemplo de criação de dicionário: 

```
>>> my_dict = {}
>>> another_dict = dict()
>>> my_other_dict = {"one":1, "two":2, "three":3}
>>> my_other_dict
{'three': 3, 'two': 2, 'one': 1}
```
Os dois primeiros exemplos mostram como criar um dicionário vazio, já o último contém elementos (chaves e suas correspondentes) dentro. Para acessar um valor em um dicionário basta usar `my_other_dict ["chave"]`. Para verificar se existe uma chave no dicionário, utilizamos o "in" comentado anteriormente dessa forma: `"chave" in my_other_dict`. Para acessar uma lista de todas as chaves presentes em um dicionário usamos `my_other_dict.keys()`.

Embora isso provavelmente não importe muito agora, em uma situação real de trabalho, os segundos importam. Quando temos milhares de arquivos para processar, esses pequenos truques podem economizar muito tempo a longo prazo.


### 4) Capítulo 4: Declarações condicionais

- __Instrução IF__

 A instrução if no python é simples,porém, devemos tomar cuidado com os __espaços__ e executar o if primeiro e depois a mensagem. Usando como exemplo as variáveis temos: 

```
if var1 > var2 :
    print("Verdadeiro")
else :
    print("Falso")
```
- __Operações Booleanas__

 Analoga a outras linguagens de programação, as operações booleanas utilizam das operações __or__, __and__ e __not__, vejamos um exemplo de utilização:

```
x  =  10 
y  =  10 
if  x  ==  10  and  y  ==  15 : 
    print ( "Esta afirmação era verdadeira" ) 
else : 
    print ( "A afirmação era falsa!" )
```
Podemos também usar os operadores booleanos para verificar elementos de listas:

```
my_list = [1, 2, 3, 4]
x = 10
if x not in my_list:
    print("'x' não foi adicionado a lista")
```

- __Verificando se não há nada__

 Em python uma string, tupla ou lista vazia também é avaliada como __False__, assim como a __None__. O valor None é usado para representar a ausência do valor. Vejamos um exemplo:

```
empty_list = []
empty_tuple = ()
empty_string = ""
nothing = None

if empty_list == []:
    print("It's an empty list!")

if empty_tuple:
    print("It's not an empty tuple!")

if not empty_string:
    print("This is an empty string!")

if not nothing:
    print("Then it's nothing!")
```
As primeiras quatro linhas configuram quatro variáveis. A seguir, temos quatro condicionais para testá-las. O primeiro verifica se a lista_vazia está realmente vazia. A segunda condicional verifica se o empty_tuple contém algo. As duas últimas condicionais estão fazendo o oposto da segunda, a terceira verifica se a string está vazia e a quarta verifica se a variável nothing é realmente nula.

O operador not significa que estamos verificando o significado oposto. Em outras palavras, estamos verificando se o valor NÃO é Verdadeiro.

- __Caracteres especiais__

Em python temos também caracteres especiais como __\n__ que pula linhas em um print e também __\t__ que da um "tab" em um print.


### 5) Capítulo 5 - Loops

- __Loop For__

Usamos o loop em Python todas vez que desejamos iterar algo repetidas vezes, e essas repetições são dadas por "n" vezes. Usaremos a função __range__ para entendermos como funciona, neste formato: `range(n)`. Esta função pega um número inteiro (n) e retorna um "range object". A função range também aceita um valor __inicial__, __final__ e um valor de __etapa__, nesta ordem. Aqui vai um exemplo:

```
>>> range(5,10)
range(5, 10)
>>> list(range(1, 10, 2))
[1, 3, 5, 7, 9]
```
Entendendo a função range, podemos finalmente criar um laço de repetição usando o __for__ em qualquer __programa__ usando python, aqui vai um exemplo:

```
for number in range(5):
print(number)
```
Saída do código acima:
```
0
1
2
3
4
```
Podemos perceber que `range(5)`=`[0, 1, 2, 3, 4]`. Podemos também usar um loop for com um dicionário, no qual ele percorre sobre as chaves dentro daquele dicionário:
```
a_dict = {"one":1, "two":2, "three":3}
for key in a_dict:
    print(key)
```
Saída do código acima:
```
three
two
one
```
Agora, sabemos que as chaves podem ser classificadas, podemos fazer isso também antes de iterá-las. Podemos ver como funciona no código abaixo:
```
>>> a_dict = {1:"one", 2:"two", 3:"three"}
>>> keys = a_dict.keys()
>>> keys = sorted(keys)
>>> for key in keys:
       print(key)
```
Saída do código acima:
```
1
2
3
```
Primeiro, criamos um dicionário que possui números inteiros para chaves. Em seguida, extraímos as chaves do dicionário (sempre que usarmos __keys()__, isso retornará uma lista não ordenada de chaves). Com isso, temos uma visão das chaves do dicionário, classificamos e então usamos o loop para percorrê-las.

Para avançarmos um pouco mais no conceito de loops, usaremos agora um algoritmo que implementa um loop que imprime apenas números pares. Para isso, também implementaremos uma condicional:
```
>>> for number in range(10):
        if number % 2 == 0:
            print(number)
```
Saída do código acima:
```
0
2
4
6
8
```
Utilizando o operador de módulo __%__ juntamente com a estrutura de condição, pudemos identificar todos os números pares presentes dentro do range (10), caso quisermos aumentar a quantidade de números pares, basta aumentar o range.

- __Loop While__

O loop while no Python é semelhante ao da linguagem C, repetindo o que estiver no loop 'n' vezes, dependendo de uma condição estabelecida:

```
>>> i = 0
>>> while i < 10:
        print(i)
        i = i + 1
```
Existe uma forma de sair de um loop sem que a condição seja completada, que é usando o comando `break`. No exemplo abaixo, conseguimos ver isso na prática analisando o código e sua saída:
```
>>> while i < 10:
        print(i)
        if i == 5:
            break
        i += 1
```
Saída do código acima:
```
0
1
2
3
4
5
```
O atalho `+=` é muito útil nesses tipos de programas, e também podemos usar com qualquer outro operador matemático além da adição.

O break embutido é conhecido como uma ferramenta de controle de fluxo. Existe outro chamado `continue` que é usado basicamente para __pular uma iteração__ ou continuar com a próxima iteração. Esta é uma maneira de usá-lo:
```
i = 0

while i < 10:
    if i == 3:
        i += 1
        continue

    print(i)

    if i == 5:
        break
    i += 1
```
- __Else em Loops__

A instrução else em loops só será executada se o loop for __concluído com sucesso__. O principal uso da instrução else é para __pesquisar itens__, como no código a seguir:
```
my_list = [1, 2, 3, 4, 5]

for i in my_list:
    if i == 3:
        print("Item found!")
        break
    print(i)
else:
    print("Item not found!")
```


### 6) Capítulo 6: Compreensões do Python

A linguagem Python possui alguns métodos para criar listas e dicionários conhecidos como compreensões. Existe também um terceiro tipo de compreensão para a criação de um conjunto Python. Neste capítulo aprenderemos como usar cada tipo de compreensão. 

- __Compreensões de lista__

A compreensão de lista é basicamente um loop for que produz uma estrutura de __lista__. Podemos visualizar isso melhor com um exemplo simples: `>>> x = [i for i in range(5)]`. Com isso se dermos um `print(x)` isso nos resultará uma lista contendo os inteiros de 0 até 4, isso pode ser útil quando queremos criar uma lista muito rapidamente. Seguimos para outro exemplo onde precisamos analisar um arquivo e procurar algo em particular, podemos usar uma comprrensão de lista como uma espécie de filtro.

Uma outra utilização importante das compreensões de lista é a capacidade de __converter elementos mutaveis__:
```
>>> x = ['1', '2', '3', '4', '5']
>>> y = [int(i) for i in x]
>>> y
```
Saída do código acima:
```
[1, 2, 3, 4, 5]
```

Também há ocasiões em que é necessário criar uma compreensão de lista aninhada. Uma razão para fazer isso é nivelar várias listas em uma. Este exemplo vem da documentação do Python:
```
>>> vec = [[1,2,3], [4,5,6], [7,8,9]]
>>> [num for elem in vec for num in elem]
```
Saída do código acima:
```
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

- __Compreensões de dicionário__

São muito semelhantes a uma compreensão de lista na forma como são organizados, vejamos o exemplo a seguir:
```
>>> print( {i: str(i) for i in range(5)} )
```
Saída do código acima:
```
{0: '0', 1: '1', 2: '2', 3: '3', 4: '4'}
```
Esse código cria um dicionário onde a chave __i__ é mapeada para o valor __str(i)__ para cada valor i em __range(5)__, range(5) gera uma sequência de números de 0 a 4. Em Python, __str(i)__ é uma função que __converte o valor de i__ para uma __string__. Em outras palavras, str(i) transforma um número inteiro i em uma representação de string desse número, por exemplo, __se i for 5__ então __str(i) será '5'__.

Agora podemos nos perguntar como poderíamos usar a compreensão de um dicionário na vida real. Uma das respostas é a possibilidade de efetuar __trocas__ de chaves e valores do dicionário. Vejamos como isso funciona:
```
>>> my_dict = {1:"dog", 2:"cat", 3:"hamster"}
>>> print( {value:key for key, value in my_dict.items()} )
```
Saída do código acima:
```
{'hamster': 3, 'dog': 1, 'cat': 2}
```
Isso só funcionará se os valores do dicionário forem de um tipo não mutável, como uma string. Caso contrário, você acabará fazendo com que uma exceção seja levantada.
- __Compreensões de Set__

As compreensões de "set" são criadas da mesma maneira que as de um dicionário. Vamos ver um exemplo usando __set__:
```
>>> my_list = [1, 2, 2, 3, 4, 5, 5, 7, 8]
>>> my_set = set(my_list)
>>> my_set
```
Saída do código acima:
```
set{1, 2, 3, 4, 5, 7, 8}
```




