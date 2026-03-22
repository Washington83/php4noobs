# 4.5 - Polimorfismo

## O que é?

Polimorfismo é a capacidade de um mesmo método ter **comportamentos diferentes**, dependendo da classe que o implementa.

> Ou seja:
Você chama **o mesmo método**, mas o resultado muda.

---

## Por que usar?

Para evitar vários `if/else` e deixar o código:

* Mais organizado
* Mais fácil de manter
* Mais profissional

---

## Ideia simples !

Você tem um método chamado `emitirSom()`:

* Cachorro → **Au au**
* Gato → **Miau**

> Mesmo método, comportamentos diferentes.

---

##  Exemplo prático

```php
<?php

class Animal {

    public function emitirSom()
    {
        echo "Som genérico";
    }

}

class Cachorro extends Animal {

    public function emitirSom()
    {
        echo "Au au";
    }

}

class Gato extends Animal {

    public function emitirSom()
    {
        echo "Miau";
    }

}
```

---

## Utilizando

```php
<?php

$animal1 = new Cachorro();
$animal2 = new Gato();

echo $animal1->emitirSom() . PHP_EOL;
echo $animal2->emitirSom() . PHP_EOL;
```

---

##  Outro exemplo (mais real)

```php
<?php

class Pagamento {

    public function pagar($valor)
    {
        echo "Pagamento genérico de R$ $valor";
    }

}

class Pix extends Pagamento {

    public function pagar($valor)
    {
        echo "Pagamento via PIX de R$ $valor";
    }

}

class Cartao extends Pagamento {

    public function pagar($valor)
    {
        echo "Pagamento no cartão de R$ $valor";
    }

}
```

### Usando:

```php
<?php

$pagamentos = [
    new Pix(),
    new Cartao()
];

foreach ($pagamentos as $pagamento) {
    $pagamento->pagar(100) . PHP_EOL;
}
```

---

## Sem polimorfismo

```php
if ($tipo == 'pix') {
    echo "Pagamento via PIX";
} elseif ($tipo == 'cartao') {
    echo "Pagamento no cartão";
}
```

❌ Difícil de manter
❌ Cresce rápido demais

---

## Com polimorfismo

```php
$pagamento->pagar(100);
```

✔️ Limpo
✔️ Reutilizável
✔️ Escalável

---

## Resumão !!!

* Mesmo método (`pagar`, `emitirSom`)
* Classes diferentes
* Resultados diferentes

---

## 🧩 Frase pra guardar

> **Polimorfismo é usar o mesmo método com comportamentos diferentes em objetos diferentes.**

---
