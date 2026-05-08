[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/zHqjFsRx)
# Diagnóstico de retomada - Teoria da Computação

Esta atividade serve para mapear o que você já domina sobre linguagens formais, autômatos, gramáticas e computabilidade.

Responda individualmente. Use suas palavras. Se usar IA depois da primeira tentativa, registre o uso na seção 7.

## 1. Mapa do que eu lembro

Marque cada tópico como: lembro bem, lembro parcialmente, não lembro, nunca vi ou não tenho certeza.

- alfabeto: **Lembro bem**
- cadeia: **Lembro bem**
- linguagem: **Lembro parcialmente**
- gramática: **Não lembro**
- autômato finito: **Lembro parcialmente**
- linguagem regular: **Lembro parcialmente**
- linguagem livre de contexto: **Lembro bem**
- linguagem sensível ao contexto: **Lembro bem**
- linguagem irrestrita: **Lembro bem**
- hierarquia de Chomsky: **Não lembro**
- computabilidade: **Lembro bem**
- máquina de Turing: **Lembro parcialmente**

## 2. Definições com exemplo

Explique, com suas palavras e com um exemplo simples, usando o alfabeto `Sigma = {a, b}`.

1. O que é um alfabeto? 
> Um conjunto com todos os caracteres únicos
2. O que é uma cadeia?
> Uma sequência formado pelos caracteres não vazios do alfabeto
3. O que é uma linguagem?
> Um conjunto que contém uma ou mais regras sobre como todas as cadeias possíveis dado um alfabeto são formadas
4. O que é uma gramática?
> Não consigo diferenciar de linguagem

## 3. Linguagens

Considere as linguagens:

```text
L1 = { w em {0,1}* | w termina com 01 }
L2 = { a^n b^n | n >= 0 }
L3 = { a^n b^n c^n | n >= 0 }
```

Para cada linguagem:

1. escreva três palavras que pertencem à linguagem;
   > palavras_L1 = [ "01", "0011001101", "00001" ]
   > palavras_L2 = [ "\b ", "ab", "aaaabbbb" ]
   > palavras_L3 = [ "\b", "abc", "aaabbbccc" ]
 
2. escreva duas palavras que não pertencem;
   > not_palavras_L1 = [ "00001111", "1111110" ]
   > not_palavras_L2 = [ "bbbbaaaa", "aaab" ]
   > not_palavras_L3 = [ "cccbbbaaa", "aaabbc" ]
   
3. diga, se souber, em qual classe ela provavelmente se encaixa;
   >L1 deve pertencer às linguagens dependentes de contexto.
   > De resto, não sei ao certo.
    
4. explique o motivo em linguagem simples.
   >Já que o contexto (nesse caso, um contexto β = "01" ao final da cadeia) é o que torna ela (L1) válida, me faz pensar que pe dependente de contexto.
   >De resto, estou muito perdido quanto às formalidades dessas classificações.

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
> L = {w ϵ {0, 1}* | w termina com '01'}
2. Execute manualmente as cadeias abaixo e diga se aceita ou rejeita:
   - `01`
   - `101`
   - `100`
   - `1101`
   - `111`

> `01` aceita

> `101` aceita

> `100` rejeitada

> `1101` aceita

> `111` rejeitada

3. Monte uma tabela curta mostrando o caminho dos estados para pelo menos duas cadeias.
> `100` q0: (1)00 → q0: 1(0)0 → q1: 10(0) → q1: 100(\b) → rejeitado
> `1101` q0: (1)101 → q0: 1(1)01 → q0: 11(0)1 → q1: 110(1) → q2: 1101(\b) → aceito
> `111` q0: (1)11 → q0: 1(1)1 → q0: 11(1) → q0: 111(\b) → rejeitado

## 5. Gramática

Considere a gramática:

```text
S -> aS
S -> b
```

Responda:

1. Gere cinco cadeias produzidas por essa gramática.
> S → aS
> aS → (ab) 
>S → aS
>aS → aaS
>aaS → (aab)
>S → aS
>aS → aaS
>aaS → aaaS
>aaaS → (aaab)

2. Descreva a linguagem em palavras.
>Teremos a^n no começo da cadeia, mas ao final, sempre teremos um 'b' ao final da mesma.
3. Essa gramática parece regular, livre de contexto ou outra classe? Justifique de forma simples.
>Essa é a parte que me confundo bastante. Creio que é livre de contexto, já que a validade de uma transformação de um caractere não-terminal não está dependendo de um contexto α ou β.
Além disso, tenho a intuição de que toda linguagem livre de contexto é, também uma linguagem regular.

## 6. Ponto de dificuldade

Escolha um tópico da lista inicial e escreva: **(Escolhi 'Gramática')**

1. o que você entende dele;
>Apenas sei que está intimamente ligado aos conceitos iniciais de Alfabeto, Cadeia e Linguagem; mas não sei definir formalmente ou exemplificar, já que não fui punido didaticamente com o professor Clerton por não diferenciar uma gramática de uma linguagem.
2. onde você se confunde;
>Confundo o conceito de gramática com linguagem, usando arbitrariamente esses dois termos para ditar o conjunto de todas as cadeias possíveis ditados por uma regra.
3. que tipo de explicação ajudaria: desenho, exemplo, exercício guiado, analogia, prova passo a passo ou lista curta.
>Uma simples contextualização do uso da definição formal de "gramática" no nosso contexto ajudaria bastante. Cristalizaria-se ainda mais em minha mente caso deixássemos explícito qual problema é resolvido em nosso contexto de estudo ao termos uma partição "gramática" dessa parte teórica.
> Tenho preferência por exemplos práticos.

## 7. Uso de IA, se houver

Se você usou IA depois da primeira tentativa, registre:

>Não fiz nenhuma consulta a IAs nesse '.md'. Se muito, consultei as atividades que já fiz; atividades as quais posso assegurar que se utilizei IA, foi apenas para propósitos consultivos simples acerca de formalidades dos assuntos.

```text
Pergunta feita: 
Resumo da resposta:
Como eu verifiquei:
O que eu alterei na minha resposta:
O que ainda não entendi:
```
