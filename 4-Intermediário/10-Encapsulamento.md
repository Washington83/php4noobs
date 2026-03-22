# 4.6 - Encapsulamento

## O que é?

Encapsulamento é o conceito de **proteger os dados de uma classe**, controlando como eles são acessados e modificados.

 Ou seja:
Você **esconde os atributos** e permite acesso apenas através de métodos.

---

## Por que usar?

Para garantir que os dados:

* Não sejam alterados de forma errada
* Tenham regras de validação
* Fiquem mais seguros

---

## Ideia simples

Pensa em uma conta bancária:

* Você não altera o saldo direto ❌
* Você usa métodos como `depositar()` ou `sacar()` ✔️

> Isso é encapsulamento.

---

## Exemplo sem encapsulamento (errado)

```php
<?php

class ContaBancaria {
    public $saldo = 1000;
}

$conta = new ContaBancaria();
$conta->saldo = -5000; // ❌ valor inválido
```

---

##  Exemplo com encapsulamento (correto)

```php
<?php

class ContaBancaria {

    private $saldo = 1000;

    public function depositar($valor)
    {
        if ($valor > 0) {
            $this->saldo += $valor;
        }
    }

    public function sacar($valor)
    {
        if ($valor > 0 && $valor <= $this->saldo) {
            $this->saldo -= $valor;
        }
    }

    public function getSaldo()
    {
        return $this->saldo;
    }

}

$conta = new ContaBancaria();
$conta->depositar(500);
$conta->sacar(200);

echo $conta->getSaldo(); // 1300
```

---

## O que está acontecendo?

* `saldo` é **private** → não pode ser acessado diretamente
* Só pode ser alterado por métodos controlados
* Existem regras (`if`) para evitar erros

---

##  Resumão

* Encapsular = **esconder os dados**
* Acesso só por métodos (getters/setters)
* Mais segurança e controle

---

## 🧩 Frase pra guardar

> **Encapsulamento é proteger os dados e controlar como eles são acessados.**

---

## 🔗 Relação com outros conceitos

* Usa `private` e `protected` (modificadores de acesso)
* Trabalha junto com getters e setters
* Base para código seguro e profissional

---