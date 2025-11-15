GRAFO DE FLUXO

Nós (N)

N1 – Início do método
N2 – Construção da consulta SQL
N3 – Tentativa de conectar ao banco e preparar PreparedStatement
N4 – Execução da consulta 
N5 – Decisão: existe algum registro retornado?
N6 – Caminho positivo: usuário e senha válidos 
N7 – Caminho negativo: nenhum registro encontrado 
N8 – Tratamento de exceção caso ocorra erro no try
N9 – Retorno da variável result
N10 – Fim da execução

Arestas (E)

N1 → N2
N2 → N3
N3 → N4
N4 → N5
N5 → (registro encontrado) → N6
N5 → (nenhum registro) → N7
N6 → N9
N7 → N9
N3 → (exceção lançada) → N8
N8 → N9
N9 → N10


COMPLEXIDADE CICLOMÁTICA

V(G) = E − N + 2

Onde:

E = número de arestas

N = número de nós

Usando de base o grafo elaborado:

E = 11

N = 10

Aplicando a fórmula:

V(G) = 11 − 10 + 2 = 3

Complexidade ciclomática = 3



Caminho 1 — Login bem-sucedido
1 → 2 → 3 → 4 → 7

Caminho 2 — Usuário inexistente
1 → 2 → 6 → 7


Caminho 3 — Usuário válido, senha incorreta
1 → 2 → 3 → 5 → 7

Caminho 4 — Falha ao conectar ao banco
1 → (erro de conexão) → 7


Caminho 5 — Falha em preparar a query
1 → 2 → (erro na consulta) → 7








