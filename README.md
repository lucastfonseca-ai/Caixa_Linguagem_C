# 🏧 Caixa Eletrônico em C

<p align="center">
  <strong>Uma simulação simples de saque bancário usando lógica de programação e Linguagem C.</strong>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Linguagem-C-00599C?style=for-the-badge&logo=c&logoColor=white" alt="Linguagem C">
  <img src="https://img.shields.io/badge/Status-Concluído-2EA44F?style=for-the-badge" alt="Status concluído">
  <img src="https://img.shields.io/badge/Projeto-Educacional-7B61A8?style=for-the-badge" alt="Projeto educacional">
</p>

## 📌 Sobre o projeto

Este projeto foi desenvolvido como parte de uma atividade prática de **Lógica de Programação**, com o objetivo de simular o funcionamento básico de um caixa eletrônico (ATM).

O programa solicita ao usuário o valor que deseja sacar, verifica se a operação atende às regras estabelecidas e, quando possível, calcula quantas cédulas de cada valor devem ser entregues.

A distribuição prioriza sempre as notas de maior valor, utilizando a estratégia gulosa (*greedy algorithm*).

## 🎯 Objetivos da atividade

- Receber do usuário o valor desejado para o saque.
- Verificar se o valor é múltiplo de **5**.
- Confirmar se o saque não ultrapassa o saldo disponível.
- Calcular a quantidade de cédulas de **R$ 100, R$ 50, R$ 20, R$ 10 e R$ 5**.
- Exibir a distribuição das notas ou uma mensagem de erro.

## 💡 Conceitos trabalhados

| Conceito | Como aparece no projeto |
|---|---|
| 📦 Variáveis | Armazenam o saldo, o valor do saque e a quantidade de cada cédula. |
| ⌨️ Entrada de dados | `scanf()` recebe o valor digitado pelo usuário. |
| 🖥️ Saída de dados | `printf()` apresenta as instruções e o resultado. |
| 🔀 Condicional | `if` e `else` validam o saque e tratam operações inválidas. |
| ➗ Operadores aritméticos | `/` calcula a quantidade de notas e `%` obtém o restante do valor. |
| 🔁 Sequência lógica | O valor restante é atualizado a cada tipo de cédula, da maior para a menor. |

## ⚙️ Como funciona?

1. O programa inicia com um saldo simulado de **R$ 1.000,00**.
2. O usuário informa quanto deseja sacar.
3. O sistema verifica se o valor é divisível por 5 e se não é maior que o saldo.
4. Se for válido, o algoritmo calcula as cédulas nesta ordem: **100 → 50 → 20 → 10 → 5**.
5. O programa mostra somente as cédulas cuja quantidade seja maior que zero.
6. Caso a validação falhe, uma mensagem informa que o valor é inválido.

### 🧠 Exemplo da lógica

Para um saque de **R$ 285,00**:

```text
285 ÷ 100 = 2 notas | restante: 85
 85 ÷  50 = 1 nota  | restante: 35
 35 ÷  20 = 1 nota  | restante: 15
 15 ÷  10 = 1 nota  | restante: 5
  5 ÷   5 = 1 nota  | restante: 0
```

## 🧾 Exemplo de execução

```text
Digite o valor do saque: 285
Notas entregues:
2 nota(s) de 100
1 nota(s) de 50
1 nota(s) de 20
1 nota(s) de 10
1 nota(s) de 5
```

✅ **Resultado:** o saque de R$ 285,00 é atendido com 6 cédulas, sem ultrapassar o saldo simulado.

### 🚫 Exemplo de valor inválido

Ao informar um valor que não seja múltiplo de 5 ou que ultrapasse o saldo de R$ 1.000,00, o programa apresenta uma mensagem de erro:

```text
Digite o valor do saque: 123
Erro: valor invalido. O valor deve ser multiplo de 5 e menor ou igual ao saldo disponivel (1000).
```

## 🛠️ Linguagem e ferramentas

- **💻 Linguagem:** C
- **🧰 Biblioteca utilizada:** `stdio.h`, para entrada e saída de dados.
- **⚙️ Compilador sugerido:** GCC
- **🖥️ Ambiente:** terminal, prompt de comando ou IDE compatível com C.

## ▶️ Como executar

1. Clone este repositório:

   ```bash
   git clone https://github.com/SEU-USUARIO/caixa-eletronico-c.git
   ```

2. Entre na pasta do projeto:

   ```bash
   cd caixa-eletronico-c
   ```

3. Compile o arquivo-fonte (considerando que ele se chama `main.c`):

   ```bash
   gcc main.c -o caixa
   ```

4. Execute o programa:

   **Linux / macOS:**
   ```bash
   ./caixa
   ```

   **Windows:**
   ```bash
   caixa.exe
   ```

## 📁 Estrutura sugerida do repositório

```text
caixa-eletronico-c/
├── main.c       # Código-fonte do caixa eletrônico
└── README.md    # Documentação do projeto
```

## 🔍 Observação sobre validação

Na versão atual, a condição verifica se o saque é múltiplo de 5 e se não ultrapassa o saldo. Para evitar que valores iguais a zero ou negativos sejam aceitos, uma melhoria recomendada é acrescentar `valor > 0` à condição:

```c
if (valor > 0 && valor % 5 == 0 && valor <= saldo) {
```

Também é possível evoluir o projeto verificando o retorno de `scanf()` para tratar entradas que não sejam números.

## 🚀 Possíveis melhorias futuras

- Permitir que o usuário consulte o saldo antes do saque.
- Oferecer opções para depósito e consulta de saldo.
- Atualizar o saldo após cada saque.
- Validar entradas inválidas, como letras, números negativos e valor zero.
- Organizar o código em funções para facilitar a manutenção.

## 👨‍💻 Aprendizado

Este exercício demonstra como problemas do cotidiano podem ser transformados em algoritmos. Com variáveis, operadores, condicionais e uma sequência bem definida de cálculos, é possível reproduzir a lógica básica de distribuição de dinheiro de um caixa eletrônico.

---

<p align="center">
  Feito para praticar programação em <strong>C</strong> ☕💻
</p>
