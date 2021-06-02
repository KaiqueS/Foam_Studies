# Aula 28/05

Laços aumentam o grau de cada nó em 2

Ler capítulo 1 para próxima aula

## Capítulo 1

Grafo:

    par de conjuntos ( V, A ), onde V representa os vértices e A é formado por
    
$$X \subset V, |X| = 2,$$

    exceto quando permitimos a existência de laços. Nesse caso, temos que

$$X \subset V, |X| = 1.$$

Um **subgrafo** G' de G é composto por conjuntos $V' \subseteq V$ e $A' \subseteq A$.

Dizemos que um subgrafo G' é **induzido** quando todas as arestas ligando um subconjunto dos vértices de G estão em G'.

Para $a, b \in V$, se $\{ a, b \} \in A$, dizemos que $a$ e $b$ são adjacentes, e que a aresta $\{a, b\}$ incide em $a$ e $b$

O __grau__ de $a \in V$ é igual ao número de arestas das quais $a$ faz parte. Mais formalmente, o grau de um vértice é igual ao número de subconjuntos de $V$ dos quais $a$ faz parte. I.e., deixe

$$M = \{ X \in A | a \in X \}$$ 

Temos que

$$d( a ) = |M|$$

Para um vértice v, quando $d( v ) = 0$, dizemos que v é **isolado**. Se temos que $d( v ) = 1$, chamamos v de **pendente**.

O vértice v de G é chamado de **mínimo** quando v possui o menor grau dentre todos os vértices em G, e é denotado por $\delta( G )$. Já o vértice com maior grau em G é chamado de **máximo**, o qual é denotado por $\Delta( G )$.

**Teorema 1:** Para todo grafo G,

$$\sum\limits_{v \in V(G)}{ d( v ) = 2 . m}$$

i.e., a soma dos graus dos vértices é igual ao dobro do número de arestas.

**Corolário 1:** Todo grafo G possui um número **par** de vértices com grau **ímpar**

    Dica para demonstração: usar Teorema 1

**Laço:** uma aresta ligando um nó a ele mesmo.

    sempre que um laço existir, o grau do vértice aumenta em 2

**Multigrafo:** generalização do conceito de grafo. Permite que existam múltiplas arestas entre dois vértices.

    Nota: Procurar a definição formal de multigrafo

**Grafos Simples:** grafos sem múltiplas arestas e laços.

**Caminho:** um **caminho** em um grafo $G = ( V, A )$ é um subgrafo $G' = ( V', A' )$ t.q. $V' \subset V$ e $A' \subset A$, onde $V' = \{ v_i \in V | 0 \leq i \leq n, n \leq |V| \}$, e $A' = \{ X \subset V' | \{ x_i, x_j \} \in X, 0 \leq i < j \leq n, n \leq |X| \}$. Ver Bollobas p.4.

**Grafos Conexos:** dizemos que um grafo é conexo quando, para qualquer par de vértices, existir um caminho entre tal par.

    Se um grafo G não for conexo, caso exista um subgrafo G' de G t.q. G' é conexo, chamaremos G' de componente conexo do grafo, e diremos que G é um grafo desconexo. A parte não conexa de G' é chamada de desconexa.

**Grafos Isomorfos:** dois grafos que possuem a mesma estrutura, i.e., dois grafos para os quais existe pelo menos uma função bijetiva mapeando um no outro t.q. essa função preserve as adjacências.

    A ideia é que possamos encontrar no grafo isomorfo os mesmos graus, número de arestas, e qualquer outra propriedade que o grafo original tenha

**Vizinhança:** é o conjunto de vértices adjacentes a um vértice v, denotada por N( v ) ou N( V ), i.e.,

$$N( v ) = \{ x \in V | \exist a \in A, \{ v, x \} \in a \}.$$

Se incluirmos $\{ v \}$ em $N( v )$, chamamos o conjunto resultante de **vizinhança fechada** de v, denotada por $N[ v ] = N( v ) \cup \{ v \}$.

**Sequência de graus:** sequência não crescente( i.e., fixa ou decrescente ) dos graus dos vértices de um grafo.

**Grafo Completo:** grafos onde, para cada par $a, b \in V$, temos um $x \in A$ t.q. $a, b \in x$. Denotamos um grafo completo com n vértices por $K_n$.

**Grafo Complementar:** deixemos G = ( V, A ) ser um grafo. Dizemos que $\overline{G} = ( V, \overline{A} )$ é o **grafo complementar** de G. I.e., $\overline{G}$ é composto pelos mesmos vértices de G, mas contém, como arestas, somente aquelas que não fazem parte de G. Isso nos permite dizer que:

$$A( G ) \cup A( \overline{G} ) = \{ X \subset V | |X| = 2 \}$$

**Grafo Nulo/Vazio:** temos um grafo vazio quando o conjunto de arestas é vazio.

**Grafo Regular:** um grafo onde todos os vértices possuem o mesmo grau

**Ciclo:** grafo conexo regular de grau 2. Denota-se $C_n$.

    É curiosa essa definição, totalmente não-intuitiva. Checar Bollobas

**Caminho:** ciclo do qual foi retirado uma aresta, denotado por $P_n$. O número de arestas no caminho determina o tamanho deste.

    Novamente, totalmente não-intuitivo. Talvez checar Bollobas

**Árvores:** grafos conexos sem ciclos como subgrafos. É a maneira mais econômica de conectar os vértices.

**Grafos Bipartidos:** para um grafo $G = ( V, A )$, se for possível subdividir V em $V_1$ e $V_2$, com $V_1 \cap V_2 = \empty$ t.q., para toda aresta em A, tenhamos que tais arestas tenham uma extremidade em $V_1$ e outra em $V_2$, i.e., devemos mostrar que, para um dado G, seja possível construir

$$\{ a \in A | \{ x, y \} \in A, ( x, y ) \in V_1 \times V_2 \}$$

ou

$$G' = ( V_1 \cup V_2, A' ),$$

com

$$A' = A - ( A( V_1 ) \cup A( V_2 ) )$$

Em outras palavras, não é permitido que haja arestas entre elementos exclusivamente de $V_1$ ou de $V_2$, mas é permitido que qualquer elemento em um conjunto esteja ligado a mais do que um elemento no outro conjunto. I.e., o grau não é restrito à 1.

Chamaremos $V_1$ e $V_2$ de **subconjunto independente de vértices do grafo G**

**Grafos Bipartidos Completos:** grafos bipartidos onde todos os vértices de $V_1$ são ligados a todos os vértices de $V_2$. Denota-se $K_{p, q}$

**Matriz de Adjacências:** matriz definida por

$$

x_{ij} =

\begin{cases}
      
      1, \text{ se } ij \in A( G )\\
      0, \text{ se } ij \notin A( G )

\end{cases}

$$

**Matriz de Incidência:** matriz n x m definida por

$$

x_{ij} =

\begin{cases}
      
      1, \text{ se a aresta } e_j \text{ incide em } v_i\\
      0, \text{ caso contrário }

\end{cases}

$$

# 02/06

Isomorfismos entre grafos são relações de equivalência

    Reflexivos, Simétricos e Transitivos

Automorfismo: isomorfismo de um grafo para si mesmo. Simetrias

    Automorfismos não são obrigatoriamente únicos. Podem existir vários automorfismos para um dado grafo.

    O número de automorfimos é igual à V( G )!, onde cada automorfismo é diferente

    Existe uma ligação entre Grafos e Grupos

