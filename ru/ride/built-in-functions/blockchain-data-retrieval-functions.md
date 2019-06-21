# Функции получения данных из блокчейна

|      | Название | Описание | Сложность |
| :--- | :--- | :--- | :--- |
|   1  | <a href="#assetInfo">assetInfo(ByteVector): Аsset&#124;Unit</a> | Получает информацию о токене | 100 |
|   2  | <a href="#blockInfoByHeight">blockInfoByHeight(Int): BlockInfo&#124;Unit</a> | Получает информацию о [блоке](blockchain/block.md) по его [высоте](blockchain/block-height.md) | 100 |
|   3  | <a href="#transactionHeightById">transactionHeightById(ByteVector): Int&#124;Unit</a> | Получает [высоту блока](blockchain/block-height.md) транзакции | 100 |
|   4  | <a href="#transferTransactionById">transferTransactionById(ByteVector): TransferTransaction&#124;Unit</a> | Получает данные транзакции перевода | 100 |

## assetInfo

Получает информацию о токене.

```
assetInfo(id: ByteVector): Аsset|Unit
```

### Параметры

#### `id`: ByteVector

ID токена.

## blockInfoByHeight

Получает информацию о [блоке](blockchain/block.md) по его [высоте](/blockchain/block-height.md).

```
blockInfoByHeight(height: Int): BlockInfo|Unit
```

### Параметры

#### `height`: Int

Высота блока.

## transactionHeightById

Получает [высоту блока](/blockchain/block-height.md) транзакции.

```
transactionHeightById(id: ByteVector): Int|Unit
```

### Параметры

#### `id`: ByteVector

ID транзакции.

## transferTransactionById

Получает данные транзакции перевода.

```
transferTransactionById(id: ByteVector): TransferTransaction|Unit
```

### Параметры

#### `id`: ByteVector

ID транзакции перевода.