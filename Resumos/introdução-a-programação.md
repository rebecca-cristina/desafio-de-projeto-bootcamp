## Introdução à Programação e Pensamento Computacional



### Definições de Lógica de Programação e os 4 pilares:

- #### Lógica de Programação

Forma de pensamento estruturada, que te auxilia a determinar a melhor sequência de ações para solucionar um problema.

Considerando que temos um problema (desvio de percurso, o qual impede de atingir um objetivo com eficiência e eficácia), precisamos solucioná-lo da melhor maneira possível, utilizando de um segmento planejado para tal, para isso, utilizaremos a:

- #### Decomposição

Dado um problema complexo, devemos quebrá-lo em problemas menores. Portanto, problemas mais fáceis e gerenciáveis (de fácil resolução).  E assim que solucionados, combinar os elementos, recompondo o problema inicial.

Para solucionar esses problemas, precisaremos definir uma gama (conjunto) de elementos que possuem alguma similaridade, coisas concretas comparáveis, ou grandezas mensuráveis, pertencentes à mesma categoria. Ou seja, ao qual podemos observar algum padrão se repetindo. Para isso, damos o nome de:

- #### Reconhecimento de padrões

Compreensão por reconhecimento de padrões (algo que se repete, seja similaridades ou diferenças).  

A importância dessa ação é para generalizar, com o objetivo de obter uma mesma resolução para problemas diferentes.

| 1. Extração de características | 2. Classificação de dados |
| ------------------------------ | ------------------------- |

Com os subproblemas definidos, partimos para a parte da:

- #### Abstração

A abstração nada mais é que um processo intelectual de isolamento de um objeto da realidade. Pegar os elementos de um determinado objeto, extrapolá-lo para um mundo abstrato, de maneira que você o torne geral.

Exemplo simples: Ao invés de medir somente uma circunferência qualquer, eu transformei esse elemento pessoal em um elemento generalista, logo, para achar a circunferência de qualquer circulo, basta eu ter em mente que c=2.pi.raio.

Através das características, é preciso concentrar em aspectos essenciais, ignorando características menos importantes, após isso, generalizar.

-Características

-Pontos Essenciais

-Generalizar x detalhar

- #### Design de Algoritmo

O design de algoritmo é a automatização dessa resolução de problemas. Nesse pilar, nós definimos o passo a passo (instrução) para chegar na solução.

Algoritmo é a sequência de passos que resolve um problema. Ele age da seguinte forma: dado uma entrada, temos uma sucessão de operações que serão executadas consequencialmente e vão me gerar um resultado.

##### Esses são os 4 pilates do _Pensamento computacional_.

"Processo de pensamento envolvido na expressão de soluções em passos computacionais ou algoritmos que podem ser implementados no computador."

​		_Aho, 2011 ; Lee, 2016_.



### Definições de assuntos variados:

#### Variáveis 

Na programação, uma variável é um objeto (uma posição, frequentemente localizada na memória) capaz de reter e representar um valor ou expressão.

Em outras palavras,  uma variável é um espaço na memória do computador destinado a um dado que é alterado durante a execução do algoritmo.

Tipos de variáveis:

| Numéricas                | Caracteres                                     | Alfanuméricas    | Lógicas             |
| ------------------------ | ---------------------------------------------- | ---------------- | ------------------- |
| Inteiro, real ou decimal | Tudo aquilo que não representamos como número. | Letras e números | Verdadeiro ou falso |

Regras para nomes de variáveis:

1. Atribuição de um ou mais caracteres
2. Primeira letra - não número (Não pode começar por número)
3. Sem espaço em branco
4. Vedado - utilização de palavras reservadas
5. Caracter e numéricos

#### Constantes

As constantes são valores imutáveis e não são alterados durante a vida útil do programa. Exemplo: π (pi) =3,14, Φ (phi) =1,618

#### Concatenação

Concatenação é um termo usado em computação para designar a operação de unir o conteúdo de duas strings*

*Strings é uma sequência de caracteres.

Isto é, agrupamento de duas ou mais células que, incluindo fórmulas, textos ou outras informações contida no seu interior, dá origem a um único resultado.

Pode ser usado o E comercial (&), o ponto (.) ou o sinal de mais (+)

Exemplo: primeiro_nome & sobrenome

Concatenei a variável nome com sobrenome, resultado: Maria Silva.

#### Estrutura de repetição

Dentro da lógica de programação, é uma estrutura que permite executar mais de uma vez o mesmo comando ou conjunto de comandos, de acordo com uma condição ou com um contador.

(Loop, laços, malhas de repetição)

Condição de paradas - número de repetições pré fixados ou condição a ser satisfeita

#### Estrutura condicional

Dado o estado de uma pessoa ou uma coisa, existe uma condição para aquilo acontecer.

| Se (condição simples)                                        | Se-Senão (condição composta)                                 | Caso (encadeada)                                             |
| ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| É utilizada a palavra reservada **se**, a condição a ser testada entre parenteses e as instruções que devem ser executados entre chaves caso o desvio seja **verdadeiro.** | Agora, vamos imaginar que se a condição for **falsa**, um outro conjunto de comandos deve ser executado. | Similar aos comandos se e senão, e reduz a complexidade na escolha de diversas opções. Neste comando não é possível o uso de operadores lógicos, ele apenas trabalha com valores definidos. |
| Exemplo: **Se** essa condição for verdadeira, execute tal função. | Exemplo: **Se** essa condição for verdadeira, execute tal função, **Senão** execute essa outra. | Exemplo: Temos as opções 1 e 2. **Caso** a opção escolhida seja a 1ª, execute tal função. **Caso** seja a segunda, execute outra função. **Caso contrário** (onde não foi escolhido uma das duas opções), volte ao menu. |

#### Matrix

Matrix é uma coleção de variáveis do mesmo tipo, acessíveis com um único nome e armazenados contiguamente na memória. 

Tabela organizada em linhas e colunas no formato MxN, onde M representa o número de linhas (horizontal), e N o número de colunas (vertical).

Os vetores são matrizes de uma só dimensão

Exemplo:

​	cadeia Vetor[5] ; //declara um vetor de 5 posições;

​	cadeia Matrix[5] [3] ; //declara uma matrix de 5 linhas e 3 colunas.

2º Exemplo:

​	Temos os alunos José [1] e Maria [2].  José tirou nota 5 na primeira prova [1] e 10 na segunda [2], já Maria tirou 7 na primeira [1] e 9 na segunda [2].

Representação em matrix:

​	**Nota [1] [1] = 5** //declara a primeira nota do aluno João (nota um do aluno um)

​	**Nota [2] [1] = 10** //declara a segunda nota do aluno João (nota dois do aluno um)

​	**Nota [1] [2] = 7 **//declara a primeira nota da aluna Maria (nota um do aluno dois)

​	**Nota [2] [2] = 9** //declara a segunda nota da aluna Maria (nota dois do aluno dois)

#### Linguagem de Programação

Conjunto de palavras com regras, usadas para gerar programas (softwares), ao qual a finalidade é de servir de um meio de comunicação entre computadores e humanos. 

Um programa é um amontoado de palavras se não for possível que o computador entenda.

Em outros termos, o que é óbvio para você, certamente não é óbvio para uma máquina. E se você quer que a máquina faça algo para você, você precisa "falar com ela".
