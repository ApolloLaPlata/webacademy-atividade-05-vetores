# Atividade 5 — Estruturas de Dados Básicas: Vetores

**Curso:** Web Academy UFAC  
**Disciplina:** Algoritmos e Lógica de Programação  
**Aluno:** Vinicius Miranda de Farias

## Questão 1 — Inverter vetor sem vetor auxiliar

Gera 20 inteiros entre 100 e 200 e inverte o próprio vetor, trocando cada par de posições com uma variável escalar temporária. Nenhum vetor auxiliar é criado.

```
programa {
    inclua biblioteca Util --> u
    funcao inicio() {
        const inteiro TAM = 20
        inteiro v[TAM]
        para (inteiro i = 0; i < TAM; i++) {
            v[i] = u.sorteia(100, 200)
        }
        escreva("Vetor antes da inversao:")
        para (inteiro i = 0; i < TAM; i++) {
            escreva(v[i], " ")
        }
        para (inteiro i = 0; i < TAM / 2; i++) {
            inteiro aux = v[i]
            v[i] = v[TAM - 1 - i]
            v[TAM - 1 - i] = aux
        }
        escreva("Vetor depois da inversao:")
        para (inteiro i = 0; i < TAM; i++) {
            escreva(v[i], " ")
        }
    }
}
```

## Questão 2 — Média e números 30% maiores que a média

Gera 30 inteiros, calcula a média e imprime os elementos cujo valor é maior que 1,30 vez a média (30% acima dela).

```
programa {
    inclua biblioteca Util --> u
    funcao inicio() {
        const inteiro TAM = 30
        inteiro v[TAM]
        real soma = 0, media
        para (inteiro i = 0; i < TAM; i++) {
            v[i] = u.sorteia(0, 100)
            soma = soma + v[i]
        }
        media = soma / TAM
        escreva("Media: ", media)
        escreva("Numeros 30% maiores que a media:")
        para (inteiro i = 0; i < TAM; i++) {
            se (v[i] > media * 1.30) {
                escreva(v[i])
            }
        }
    }
}
```

## Questão 3 — Intercalação dos vetores A e B em C

Sorteia 20 números ao todo: 10 para A e 10 para B (tamanhos iguais). O vetor C intercala A[0], B[0], A[1], B[1] e assim por diante.

```
programa {
    inclua biblioteca Util --> u
    funcao inicio() {
        const inteiro TAM = 10
        inteiro A[TAM], B[TAM], C[TAM * 2]
        para (inteiro i = 0; i < TAM; i++) {
            A[i] = u.sorteia(0, 100)
            B[i] = u.sorteia(0, 100)
        }
        para (inteiro i = 0; i < TAM; i++) {
            C[2 * i] = A[i]
            C[2 * i + 1] = B[i]
        }
        escreva("Vetor A:")
        para (inteiro i = 0; i < TAM; i++) { escreva(A[i], " ") }
        escreva("Vetor B:")
        para (inteiro i = 0; i < TAM; i++) { escreva(B[i], " ") }
        escreva("Vetor C (intercalado):")
        para (inteiro i = 0; i < TAM * 2; i++) { escreva(C[i], " ") }
    }
}
```

## Questão 4 — Nomes dos dois livros mais caros

Lê 10 livros, guardando os nomes em A (cadeia) e os valores em B (real). Percorre B mantendo as posições do maior e do segundo maior valor para imprimir os nomes correspondentes.

```
programa {
    funcao inicio() {
        cadeia A[10]
        real B[10]
        para (inteiro i = 0; i < 10; i++) {
            escreva("Nome do livro: ")
            leia(A[i])
            escreva("Valor do livro: ")
            leia(B[i])
        }
        inteiro pos1 = 0, pos2 = 1
        se (B[1] < B[0]) {
            pos1 = 1
            pos2 = 0
        }
        para (inteiro i = 2; i < 10; i++) {
            se (B[i] > B[pos1]) {
                pos2 = pos1
                pos1 = i
            } senao se (B[i] > B[pos2]) {
                pos2 = i
            }
        }
        escreva("Livro mais caro: ", A[pos1])
        escreva("Segundo livro mais caro: ", A[pos2])
    }
}
```
