# PC Mania — Projeto de Programação Orientada a Objetos (POO)

Este projeto em **Java** simula uma loja de computadores (PC Mania), com foco na aplicação de conceitos de **Programação Orientada a Objetos**.

## Objetivo

Modelar o processo de venda de computadores com diferentes configurações, permitindo que um cliente selecione promoções e calcule o total da compra.

---

## Conceitos de POO aplicados

### 1) Classes e objetos
As entidades do problema foram modeladas em classes:
- `Cliente`
- `Computador`
- `HardwareBasico`
- `SistemaOperacional`
- `MemoriaUSB`
- `Main` (classe de execução)

Cada classe representa um objeto do domínio da loja.

### 2) Associação
A classe `Cliente` possui um vetor de `Computador`:
- `Computador[] computador = new Computador[10];`

Isso modela a relação de que um cliente pode comprar vários computadores.

### 3) Composição
Na classe `Computador`, os componentes internos são criados no construtor:
- `SistemaOperacional sistema`
- `HardwareBasico[] hardware`

Como são instanciados dentro do `Computador`, representam composição (parte integrante do objeto).

### 4) Agregação
Também em `Computador`, o atributo:
- `MemoriaUSB memoriaUSB`

é associado externamente via método `addMemoriaUSB(...)`, caracterizando agregação.

### 5) Encapsulamento (ponto de melhoria)
O projeto utiliza atributos públicos para simplificar o estudo inicial. Em uma evolução orientada a boas práticas, recomenda-se:
- tornar atributos `private`;
- criar métodos `get`/`set`;
- adicionar validações (ex.: preço > 0, capacidade > 0).

---

## Estrutura do projeto

```text
PCmania1/
 ├─ src/
 │   ├─ Main.java
 │   ├─ Cliente.java
 │   ├─ Computador.java
 │   ├─ HardwareBasico.java
 │   ├─ SistemaOperacional.java
 │   └─ MemoriaUSB.java
 └─ out/
```

---

## Fluxo da aplicação

1. O sistema cria 3 computadores em promoção.
2. Cada computador recebe marca, preço, hardware, sistema operacional e memória USB.
3. O usuário digita o código da promoção desejada (`1`, `2`, `3` ou `0` para sair).
4. As escolhas são adicionadas ao carrinho (`Cliente.computador`).
5. Ao final, o sistema calcula e exibe o valor total.

---
