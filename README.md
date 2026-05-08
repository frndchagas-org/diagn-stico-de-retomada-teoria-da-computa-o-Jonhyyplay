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

1. O que é um alfabeto?
   - É o conjunto finito de símbolos básicos. Um exemplo é o alfabeto binário, podendo ser representado por `Sigma = {1, 0}`
2. O que é uma cadeia?
   - Ou também "Palavra", é uma sequência finita formada pelos símbolos do alfabeto. Um exemplo é o alfabeto `Sigma = {a, b}`, na qual podemos obter a cadeia `Sigma: {a, b, aa, bb, ab, baa, ababa, ...}` (uma cadeia infinita).
3. O que é uma linguagem?
   -
4. O que é uma gramática?
   - Pode ser definida como  as técnicas e regras ditadas à serem utilizadas, para gerar uma linguagem específico.

## 3. Linguagens

Considere as linguagens:

```text
L1 = { w em {0,1}* | w termina com 01 }
L2 = { a^n b^n | n >= 0 }
L3 = { a^n b^n c^n | n >= 0 }
```

Para cada linguagem:

1. escreva três palavras que pertencem à linguagem;
2. escreva duas palavras que não pertencem;
3. diga, se souber, em qual classe ela provavelmente se encaixa;
4. explique o motivo em linguagem simples.

Não há problema em dizer "não sei". Nesse caso, escreva o que te deixou em dúvida.

## 4. Autômato finito

Considere o autômato abaixo, sobre o alfabeto `{0,1}`:

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

Responda:

1. Qual linguagem esse autômato parece reconhecer?
2. Execute manualmente as cadeias abaixo e diga se aceita ou rejeita:
   - `01`
   - `101`
   - `100`
   - `1101`
   - `111`
3. Monte uma tabela curta mostrando o caminho dos estados para pelo menos duas cadeias.

## 5. Gramática

Considere a gramática:

```text
S -> aS
S -> b
```

Responda:

1. Gere cinco cadeias produzidas por essa gramática.
2. Descreva a linguagem em palavras.
3. Essa gramática parece regular, livre de contexto ou outra classe? Justifique de forma simples.

## 6. Ponto de dificuldade

Escolha um tópico da lista inicial e escreva:

1. o que você entende dele;
2. onde você se confunde;
3. que tipo de explicação ajudaria: desenho, exemplo, exercício guiado, analogia, prova passo a passo ou lista curta.

## 7. Uso de IA, se houver

Se você usou IA depois da primeira tentativa, registre:

```text
Pergunta feita:
Resumo da resposta:
Como eu verifiquei:
O que eu alterei na minha resposta:
O que ainda não entendi:
```

## Submissão no Moodle

Depois de finalizar, copie no Moodle:

```text
Repositório:
Commit final:
Autoavaliação: nível atual, maior dificuldade e tópico que precisa ser retomado.
```
