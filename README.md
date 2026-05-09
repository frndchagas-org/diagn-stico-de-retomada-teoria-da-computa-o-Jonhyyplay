[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/zHqjFsRx)
# Diagnóstico de retomada - Teoria da Computação

 Atividade proposta para saber meu domínio referente aos seguintes conteúdos: 
 - **Linguagens Formais**
 - **Autômatos**
 - **Gramáticas**
 - **Computabilidade**

## 1. Mapa do que eu lembro

- **`Alfabeto`**: Lembro bem
- **`Cadeia`**: Lembro bem
- **`Linguagem`**: Lembro bem
- **`Gramática`**: Lembro parcialmente
- **`Autômato finito`**: Lembro bem
- **`Linguagem regular`**: Lembro bem (Tipo 3)
- **`Linguagem livre de contexto`**: Lembro bem (Tipo 2)
- **`Linguagem sensível ao contexto`**: Lembro bem (Tipo 1)
- **`Linguagem irrestrita`**: Lembro bem (Tipo 0)
- **`Hierarquia de Chomsky`**: Lembro bem
- **`Computabilidade`**: Nunca vi
- **`Máquina de Turing`**: Lembro bem

## 2. Definições com exemplo

1. **O que é um alfabeto?**
   - É o conjunto finito de símbolos básicos. Um exemplo é o alfabeto binário, podendo ser representado por `Sigma = {1, 0}`
2. **O que é uma cadeia?**
   - Ou também "Palavra", é uma sequência finita formada pelos símbolos do alfabeto. Um exemplo é o alfabeto `Sigma = {a, b}`, na qual podemos obter a cadeia `Sigma: {a, b, aa, bb, ab, baa, ababa, ...}` (uma cadeia infinita).
3. **O que é uma linguagem?**
   - É o conjunto de todas as cadeias possíveis do alfabeto de qualquer comprimento. Um exemplo é o Fecho de Kleene, que pode ser denotado por $`L^* = L^0 ∪ L^1 ∪ L^2 ∪ L^3 ∪ ...`$
4. **O que é uma gramática?**
   - Pode ser definida como  as técnicas e regras ditadas à serem utilizadas, para gerar uma linguagem específico. Toda gramática é definida por 4 elementos: `G = (V, Sigma, P, S)`

## 3. Linguagens

Considerando as linguagens:

```text
L1 = { w em {0,1}* | w termina com 01 }
L2 = { a^n b^n | n >= 0 }
L3 = { a^n b^n c^n | n >= 0 }
```

1. **Três palavras que pertencem à linguagem:**
   - L1 -> 110101, 100101, 111101
   - L2 -> ab, aabb, aaabbb
   - L3 -> abc, aabbcc, aaabbbccc
2. **Duas palavras que não pertencem:**
   - L1 -> 101010, 100111, 111111
   - L2 -> ababaa, bab, bbbaaa
   - L3 -> acaba, bacabaa, cba
3. **Qual classe ela provavelmente se encaixa:**
   - L1 -> Pertence a classe do Tipo 3, a gramática restrita.
   - L2 -> Pertence a classe do Tipo 2, a gramática livre de contexto.
   - L3 -> Pertence a classe do Tipo 1, a gramática sensível ao contexto.
4. **Explicar o motivo em linguagem simples:**
   - L1 -> Pois pode ser reconhecido como um Autômato Finito na qual não exige memorizar muitos dados, apenas ver se terminam em `01` ou não.
   - L2 -> Pois ela pode ser reconhecida como um Autômato de Pilha e exige uma correspondência de mesma quantidade de letras.
   - L3 -> Pois necessita de um modelo mais complexo e com memória de fita para verificá-la, diferente de uma Pilha.

## 4. Autômato finito

Considerando o autômato abaixo, sobre o alfabeto `{0,1}`:

```text
Estados: q0, q1, q2
Estado inicial: q0
Estado final: q2

Transições:
q0 --0--> q1
q0 --1--> q0
q1 --0--> q1
q1 --1--> q2
q2 --0--> q1
q2 --1--> q0
```

1. **Qual linguagem esse autômato parece reconhecer?**
   - A linguagem Restrita (Tipo 3)
2. **Execute manualmente as cadeias abaixo e diga se aceita ou rejeita:**
   - `01`:
     - I -> Início: `q0`;
     - II -> Lê `0`, vai para `q1´`;
     - III -> Lê `1`, vai para `q2`;
     - IV -> Fim da cadeia. Parou em `q2` (aceita)
   - `101`
     - I -> Início: `q0`;
     - II -> Lê `1`, continua em `q0´`;
     - III -> Lê `0`, vai para `q1`;
     - IV -> Lê `1`, vai para `q2`;
     - V -> Fim da cadeia. Parou em `q2` (aceita)
   - `100`
     - I -> Início: `q0`;
     - II -> Lê `1`, continua em `q0´`;
     - III -> Lê `0`, vai para `q1`;
     - IV -> Lê `0`, continua em `q2`;
     - V -> Fim da cadeia. Parou em `q1` (rejeita)
   - `1101`
     - I -> Início: `q0`;
     - II -> Lê `1`, continua em `q0´`;
     - III -> Lê `1`, continua em `q0`;
     - IV -> Lê `0`, vai para `q1`;
     - V -> Lê `1`, vai para `q2`;
     - VI -> Fim da cadeia. Parou em `q2` (aceito)
   - `111`
     - I -> Início: `q0`;
     - II -> Lê `1`, continua em `q0´`;
     - III -> Lê `1`, continua em `q0`;
     - IV -> Lê `1`, continua em `q0`;
     - V -> Fim da cadeia. Parou em `q0` (rejeita)
3. **Tabela dos estados de duas cadeias.**
**Caminho para a cadeia `101` (Aceita):**

| Estado Atual | Símbolo Lido | Próximo Estado |
| :--- | :--- | :--- |
| **q0** (Início) | 1 | q0 |
| q0 | 0 | q1 |
| q1 | 1 | **q2** (Final) |

**Caminho para a cadeia `100` (Rejeita):**

| Estado Atual | Símbolo Lido | Próximo Estado |
| :--- | :--- | :--- |
| **q0** (Início) | 1 | q0 |
| q0 | 0 | q1 |
| q1 | 0 | **q1** (Fim da leitura) |
## 5. Gramática

Considere a gramática:

```text
S -> aS
S -> b
```

Responda:

1. **Gere cinco cadeias produzidas por essa gramática.**
   - `b`, `ab`, `aab`, `aaab`, `aaaab`
2. **Descreva a linguagem em palavras.**
   - Essa linguagem é formada por uma quantidade qualquer de `a` (ou mesmo nenhuma), e terminada por um único `b` de maneira obrigatória.
3. **Essa gramática parece regular, livre de contexto ou outra classe? Justifique de forma simples.**
   - Restrita (Tipo 3), pois sua regra de produção segue um formato linear bem rígido de formação.

## 6. Ponto de dificuldade

Escolher um tópico da lista inicial e escrever:

1. **O que você entende dele:**
   - `Linguagens` -> A diferenciação entre todas elas 
   - `Máquina de Turing` -> O que ela é 
3. **onde você se confunde:**
   - `Linguagens` -> Como definir como aquela linguagem é daquele tipo (se é restrita, sensível ao contexto, etc).
   - `Máquina de Turing` -> Ainda confundo quanto as transições, mesmo entendendo um pouco.
5. **que tipo de explicação ajudaria: desenho, exemplo, exercício guiado, analogia, prova passo a passo ou lista curta.**
   -Uma explicação passo a passo de exemplos seria muito bom e suficiente.

## 7. Uso de IA, se houver

Se você usou IA depois da primeira tentativa, registre:
- `Questão 3:` Utilização apenas para saber se minhas respostas estavam corretas. Os assuntos tradados eu entendo e utilizei de minhas próprias respostas
- `Questão 4:` Verificar se minhas respostas estavam corretas (por ainda ter dúvida em definir algumas linguagens e o processo de transição). No mais, para criar o modelo da tabela no Markdown por praticidade.
- `Questão 5:` Me ajudar a corrigi as respostas dela, por: não saber como funcionava aquela geração de cadeia e por definir seu tipo de linguagem (que eu achava ser Sensível ao Contexto mas era Restrita).
