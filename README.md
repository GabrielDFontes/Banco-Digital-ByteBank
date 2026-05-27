> 💡 **Projeto desenvolvido no desafio "Programando com OO em Java na Prática" do Bootcamp NTT DATA: Backend Java com Spring AI, aplicando conceitos de Programação Orientada a Objetos (POO) em Java.**

# 💳 Sistema de Conta Bancária - ByteBank

Projeto desenvolvido em **Java** com foco em **Programação Orientada a Objetos (POO)**, aplicando os conceitos de **encapsulamento**, controle de saldo e operações bancárias básicas.

## 📌 Sobre o Projeto

O sistema simula uma conta bancária digital do **ByteBank**, permitindo:

- ✅ Criar uma conta com saldo inicial;
- ✅ Depositar valores;
- ✅ Sacar valores;
- ✅ Impedir saldo negativo;
- ✅ Ignorar saques acima do saldo disponível;
- ✅ Consultar o saldo final da conta.

O projeto foi desenvolvido utilizando **encapsulamento**, protegendo o atributo `saldo` e permitindo seu acesso apenas através de métodos específicos.

---

## 🚀 Tecnologias Utilizadas

- **Java**
- **Programação Orientada a Objetos (POO)**
- **Scanner (entrada de dados)**
- **Encapsulamento**
- **Métodos**
- **Condicionais (`if`)**

---

## 📂 Estrutura do Projeto

```text
📦 bytebank-conta
 ┣ 📜 Main.java
 ┗ 📜 Conta.java
```

### Classe `Conta`

Responsável por:

- armazenar o saldo da conta;
- realizar depósitos;
- validar saques;
- impedir saldo negativo;
- retornar saldo atual.

### Classe `Main`

Responsável por:

- ler os dados do usuário;
- processar comandos;
- executar operações de saque e depósito;
- exibir saldo final.

---

## 🔒 Encapsulamento

O atributo `saldo` é privado (`private`), garantindo maior segurança e impedindo alterações diretas.

Exemplo:

```java
private int saldo;
```

O acesso ao saldo é realizado somente pelos métodos:

```java
depositar()
sacar()
getSaldo()
```

---

## 🧠 Regras de Negócio

### Depósito
- O valor precisa ser maior que zero.

### Saque
- O saque só é realizado se houver saldo suficiente.
- Caso contrário, a operação é ignorada.

Exemplo:

Saldo: `50`

Tentativa:

```text
sacar 80
```

Resultado:

```text
Operação ignorada
Saldo continua: 50
```

---

## 💻 Exemplo de Entrada e Saída

### Entrada

```text
100
depositar 50
sacar 30
fim
```

### Processamento

```text
Saldo inicial = 100
Depósito = +50
Saldo = 150

Saque = -30
Saldo = 120
```

### Saída

```text
120
```

---

## 🧾 Código Principal

```java
import java.util.Scanner;

class Conta {
    private int saldo;

    public Conta(int saldoInicial) {
        this.saldo = saldoInicial;
    }

    public void depositar(int valor) {
        if (valor > 0) {
            saldo += valor;
        }
    }

    public void sacar(int valor) {
        if (valor <= saldo) {
            saldo -= valor;
        }
    }

    public int getSaldo() {
        return saldo;
    }
}

public class Main {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        int saldoInicial = Integer.parseInt(scanner.nextLine());
        Conta conta = new Conta(saldoInicial);

        while (true) {
            String comando = scanner.nextLine().trim();

            if (comando.equals("fim")) {
                break;
            }

            String[] partes = comando.split(" ");
            String operacao = partes[0];
            int valor = Integer.parseInt(partes[1]);

            if (operacao.equals("depositar")) {
                conta.depositar(valor);
            } else if (operacao.equals("sacar")) {
                conta.sacar(valor);
            }
        }

        System.out.println(conta.getSaldo());
    }
}
```

---

## 🎯 Conceitos Aplicados

Este projeto utiliza conceitos importantes de Java:

- **Encapsulamento**
- **Classes e Objetos**
- **Construtores**
- **Métodos**
- **Modificadores de acesso (`private`)**
- **Estruturas condicionais**
- **Manipulação de Strings**
- **Entrada de dados com Scanner**

---

## 📚 Aprendizados

Durante o desenvolvimento deste projeto foram praticados:

- proteção de atributos usando encapsulamento;
- manipulação de saldo bancário;
- validação de regras de negócio;
- lógica de programação;
- estruturação de classes em Java.