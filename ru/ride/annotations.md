# Аннотации

**Аннотация** — форма метаданных, которая добавляется к функции [dApp-скрипта](/blockchain/dapp-script.md).

В настоящее время существует две аннотации: `@Callable` и `@Verifier`.

Аннотированная функция не может быть вызвана внутри dApp-скрипта.

## @Callable(inv: [Invocation](/ride/structures/common-structures.md#invocation))

Аннотация [вызываемой функции](/ride/annotations/callable-function.md).

Переменная `inv` содержит информацию о транзакции, которая вызвала функцию [dApp](/blockchain/dapp.md).

## @Verifier(tx: Transaction|[Order](/ride/structures/common-structures.md#order))

Аннотация [функции-верификатора](/ride/annotations/verifier-function.md).

Переменная `tx` содержит информацию об отправляемой транзакции или ордере.